# AI Playlist Generator for Vibrasonix

This document outlines a straightforward implementation of an AI middle layer that generates custom playlists based on user selections in the existing Vibrasonix onboarding flow.

## Overview

Rather than redesigning the entire onboarding experience, this approach uses OpenAI's API as a middleware component that takes the user's goal selections and preferences from the current onboarding flow and transforms them into personalized playlist recommendations from the extensive Vibrasonix content library.

## Implementation Approach

### 1. Data Collection from Existing Onboarding

The current onboarding flow already collects key information:
- Primary wellness goals (sleep, focus, stress reduction, meditation, etc.)
- Experience level with binaural beats and PEMF technology
- Time of day preferences
- Session duration preferences

This data will be used as input for the AI playlist generator without modifying the existing UI.

### 2. Simple Prompt Wrapper

The core of this implementation is a straightforward prompt wrapper that formats the user's selections into an effective prompt for the OpenAI API:

```javascript
function generatePlaylistPrompt(userSelections) {
  return `
    Generate a personalized playlist of 5 tracks from the Vibrasonix content library for a user with the following preferences:
    
    Primary Goals: ${userSelections.goals.join(', ')}
    Experience Level: ${userSelections.experienceLevel}
    Preferred Time: ${userSelections.timePreference}
    Session Duration: ${userSelections.sessionDuration}
    
    The Vibrasonix library includes content in these categories:
    - Planetary Tones (frequencies associated with planetary movements)
    - Organs (frequencies that resonate with specific body organs)
    - Metals (frequencies that correspond to metallic elements)
    - Chakras (frequencies aligned with the 7 chakra centers)
    - Sleep (delta wave entrainment for deep sleep)
    - Meditation (theta frequencies for meditative states)
    - Focus (alpha and gamma frequencies for concentration)
    - Noise (specialized noise patterns for various purposes)
    
    For each recommended track, include:
    1. Track name
    2. Category
    3. Duration
    4. Brief explanation of why it's suitable for this user
    5. Suggested time of day to listen
    
    Format the response as a JSON object.
  `;
}
```

### 3. API Integration

The API call is simple and focused:

```javascript
async function generateCustomPlaylist(userSelections) {
  try {
    const prompt = generatePlaylistPrompt(userSelections);
    
    const response = await openai.chat.completions.create({
      model: "gpt-4",
      messages: [
        {
          role: "system",
          content: "You are a sound therapy expert who creates personalized playlists from the Vibrasonix content library."
        },
        {
          role: "user",
          content: prompt
        }
      ],
      response_format: { type: "json_object" }
    });
    
    return JSON.parse(response.choices[0].message.content);
  } catch (error) {
    console.error("Error generating playlist:", error);
    return getFallbackPlaylist(userSelections); // Return curated fallback recommendations
  }
}
```

### 4. Playlist Presentation

After the onboarding flow completes, present the user with their custom playlist:

```javascript
function displayCustomPlaylist(playlist) {
  // Create a visually appealing playlist display
  const playlistContainer = document.createElement('div');
  playlistContainer.className = 'custom-playlist-container';
  
  const header = document.createElement('h2');
  header.textContent = 'Your Personalized Sound Journey';
  playlistContainer.appendChild(header);
  
  const subheader = document.createElement('p');
  subheader.textContent = 'Based on your goals and preferences, we\'ve created this custom playlist to start your journey';
  playlistContainer.appendChild(subheader);
  
  // Add each track with explanation
  playlist.tracks.forEach((track, index) => {
    const trackCard = createTrackCard(track, index);
    playlistContainer.appendChild(trackCard);
  });
  
  // Add a "Start Journey" button
  const startButton = document.createElement('button');
  startButton.className = 'primary-button';
  startButton.textContent = 'Begin Your Journey';
  startButton.addEventListener('click', () => startPlaylist(playlist));
  playlistContainer.appendChild(startButton);
  
  // Add to the main container
  document.getElementById('onboarding-completion-screen').appendChild(playlistContainer);
}
```

## Example Playlist Generation

### User Selections (from existing onboarding)
- **Goals**: Improve sleep, Reduce stress
- **Experience Level**: Beginner
- **Time Preference**: Evening
- **Session Duration**: 30 minutes

### Generated Playlist

```json
{
  "playlist_name": "Tranquil Night Journey",
  "tracks": [
    {
      "name": "Delta Dreamscape",
      "category": "Sleep",
      "duration": "10:00",
      "explanation": "This track uses gentle delta wave entrainment (0.5-4 Hz) to help transition your brain to sleep states. Perfect for beginners as it starts with a familiar ambient sound that gradually introduces the therapeutic frequencies.",
      "recommended_time": "Right before bed"
    },
    {
      "name": "Heart Chakra Harmony",
      "category": "Chakras",
      "duration": "8:30",
      "explanation": "This heart chakra (Anahata) focused track helps release stress and anxiety stored in the chest area. The 639 Hz frequency promotes balance and harmony, ideal for your stress reduction goal.",
      "recommended_time": "Early evening"
    },
    {
      "name": "Lunar Lullaby",
      "category": "Planetary Tones",
      "duration": "12:00",
      "explanation": "Based on the frequency of the moon's orbit, this track promotes natural circadian rhythm alignment. The gentle pulsing helps quiet an active mind, addressing both sleep and stress goals.",
      "recommended_time": "1-2 hours before sleep"
    },
    {
      "name": "Magnesium Resonance",
      "category": "Metals",
      "duration": "7:45",
      "explanation": "This track resonates at frequencies associated with magnesium, a mineral known for its relaxation properties. The gentle PEMF patterns help release physical tension, supporting both stress reduction and sleep preparation.",
      "recommended_time": "Evening relaxation time"
    },
    {
      "name": "Theta Threshold",
      "category": "Meditation",
      "duration": "9:15",
      "explanation": "An introductory track to theta frequencies (4-7 Hz) that helps transition from active thinking to a relaxed, meditative state. Excellent for beginners as it creates a bridge between wakefulness and sleep.",
      "recommended_time": "Evening wind-down"
    }
  ],
  "total_duration": "47:30",
  "recommended_sequence": "Start with Heart Chakra Harmony early in the evening, followed by Magnesium Resonance, then Theta Threshold as you begin your bedtime routine, Lunar Lullaby as you get into bed, and finally Delta Dreamscape as you're ready to fall asleep."
}
```

## Technical Implementation

### 1. Middleware Function

Add a simple middleware function to the existing onboarding completion handler:

```javascript
// In the onboarding completion handler
async function handleOnboardingCompletion(userSelections) {
  // Show loading state
  showLoadingState("Creating your personalized sound journey...");
  
  try {
    // Generate custom playlist
    const customPlaylist = await generateCustomPlaylist(userSelections);
    
    // Save to user profile
    await saveToUserProfile(userSelections, customPlaylist);
    
    // Display the custom playlist
    displayCustomPlaylist(customPlaylist);
    
    // Hide loading state
    hideLoadingState();
    
    // Analytics
    trackEvent("playlist_generated", {
      goals: userSelections.goals,
      playlist_name: customPlaylist.playlist_name,
      track_count: customPlaylist.tracks.length
    });
  } catch (error) {
    // Handle errors
    console.error("Error in onboarding completion:", error);
    hideLoadingState();
    showFallbackPlaylist(userSelections);
  }
}
```

### 2. Content Library Mapping

Create a simple mapping of the content library for the AI to reference:

```javascript
const contentLibraryMap = {
  "Sleep": [
    "Delta Dreamscape", "Nocturnal Neurosymphony", "Deep Sleep Descent", 
    "REM Resonance", "Slumber Sanctuary", "Night Wave Nebula"
  ],
  "Meditation": [
    "Theta Threshold", "Mindful Moments", "Zen Zenith", 
    "Awareness Ascension", "Present Pulse", "Conscious Cosmos"
  ],
  "Planetary Tones": [
    "Solar Flare Symphony", "Lunar Lullaby", "Martian Meditation", 
    "Venus Vibrations", "Jupiter Jubilation", "Saturn's Rings"
  ],
  "Organs": [
    "Heart Harmony", "Liver Liberation", "Kidney Cadence", 
    "Lung Lightness", "Brain Balance", "Digestive Dynamics"
  ],
  "Metals": [
    "Gold Resonance", "Silver Soundscape", "Copper Cadence", 
    "Magnesium Resonance", "Zinc Zenith", "Iron Immersion"
  ],
  "Chakras": [
    "Root Restoration", "Sacral Sanctuary", "Solar Plexus Power", 
    "Heart Chakra Harmony", "Throat Threshold", "Third Eye Transcendence", 
    "Crown Connection"
  ],
  "Focus": [
    "Alpha Attention", "Gamma Gateway", "Concentration Cadence", 
    "Productivity Pulse", "Mental Clarity", "Focus Flow"
  ],
  "Noise": [
    "Pink Noise Palette", "Brown Noise Basin", "White Noise Whisper", 
    "Blue Noise Breeze", "Violet Vibrations", "Green Noise Garden"
  ]
};
```

### 3. Fallback System

Implement a simple fallback system for when the API is unavailable:

```javascript
function getFallbackPlaylist(userSelections) {
  // Map goals to recommended tracks
  const goalToTracks = {
    "Sleep": ["Delta Dreamscape", "Nocturnal Neurosymphony"],
    "Focus": ["Alpha Attention", "Gamma Gateway"],
    "Stress": ["Heart Chakra Harmony", "Magnesium Resonance"],
    "Meditation": ["Theta Threshold", "Mindful Moments"],
    "Healing": ["Root Restoration", "Liver Liberation"],
    "Spiritual": ["Crown Connection", "Third Eye Transcendence"]
  };
  
  // Get tracks based on user goals
  const recommendedTracks = [];
  userSelections.goals.forEach(goal => {
    if (goalToTracks[goal]) {
      recommendedTracks.push(...goalToTracks[goal]);
    }
  });
  
  // Limit to 5 tracks
  const selectedTracks = recommendedTracks.slice(0, 5);
  
  // Create a basic playlist structure
  return {
    playlist_name: "Your Personalized Journey",
    tracks: selectedTracks.map(trackName => {
      // Find category for this track
      let category = "";
      for (const [cat, tracks] of Object.entries(contentLibraryMap)) {
        if (tracks.includes(trackName)) {
          category = cat;
          break;
        }
      }
      
      return {
        name: trackName,
        category: category,
        duration: "10:00", // Default duration
        explanation: "This track is recommended based on your selected goals.",
        recommended_time: userSelections.timePreference || "Any time"
      };
    }),
    total_duration: `${selectedTracks.length * 10}:00`,
    recommended_sequence: "Listen to these tracks in the order presented for optimal benefit."
  };
}
```

## Benefits of This Approach

1. **Minimal Changes to Existing UI**: Leverages the current onboarding flow without redesign
2. **Simple Integration**: Requires only a middleware component, not a complete system overhaul
3. **Personalized Experience**: Creates a custom starting point for each user
4. **Fallback Safety**: Includes a non-AI fallback system for reliability
5. **Immediate Value**: Delivers tangible value to users immediately after onboarding
6. **Content Discovery**: Introduces users to the breadth of the content library
7. **Low API Usage**: Requires only one API call per user onboarding

## Implementation Timeline

This streamlined approach can be implemented quickly:

1. **Week 1**: Set up OpenAI API integration and prompt engineering
2. **Week 2**: Implement playlist generation and fallback system
3. **Week 3**: Design and implement playlist presentation UI
4. **Week 4**: Testing, optimization, and deployment

## Future Enhancements

While keeping the initial implementation simple, these enhancements could be added later:

1. **Feedback Loop**: Add simple thumbs up/down on playlist tracks to refine future recommendations
2. **Progressive Playlists**: Generate follow-up playlists based on user progress
3. **Session Sequencing**: Suggest optimal order and timing for playlist tracks
4. **Content Filtering**: Allow users to exclude certain categories or frequencies
5. **Sharing**: Enable users to share their generated playlists with others

## Conclusion

This approach provides a simple yet effective way to enhance the Vibrasonix user experience by leveraging AI to create personalized playlists based on the existing onboarding flow. It delivers immediate value to users without requiring significant changes to the current system, while still providing a foundation for more advanced personalization features in the future.
