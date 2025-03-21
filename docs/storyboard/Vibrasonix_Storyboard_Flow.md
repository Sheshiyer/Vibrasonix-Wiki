# Vibrasonix Storyboard Flow

## Introduction

This document provides a detailed storyboard of the Vibrasonix app user flow, outlining specific interactions, transitions, and feedback mechanisms. It serves as a blueprint for implementation, detailing the user's journey through each screen.

## User Flow Map

```
App Launch → Splash Screen → Welcome Hook → Problem Statement → Value Proposition →
Drug Metaphor → Solution Reveal → Science Explanation → Goal Selection → 
Personalized Response → Tech Familiarity → Experience Customization → 
Usage Recommendation → Account Creation → Subscription → Main Experience
```

## Detailed Storyboard

### 1. App Launch & Splash Screen

**Initial State:**
- App icon is tapped on user's device
- System displays standard OS loading mechanism

**Transition:**
- Fade from black (500ms)
- Gold atom logo appears in center of screen
- Logo particles animate into final formation (2s)
- App name "Vibrasonix" fades in below logo
- Subtle sound wave animation plays in background

**Loading State:**
- If loading content takes >2s, display subtle loading indicator
- Progress indicator at bottom of screen (optional)

**Exit Transition:**
- Logo pulses once
- Cross-fade to Welcome Hook screen (800ms)

**Edge Cases:**
- First-time load may take longer: show extended animation
- Network error: Display retry option
- App update required: Show update prompt

### 2. Welcome Hook Screen

**Initial State:**
- Person with headphones image fills most of screen
- Copy "Sound can literally change your mind" prominently displayed
- Supporting copy "Experience the power of vibroacoustic therapy and PEMF technology"
- Continue button at bottom with subtle pulsing effect

**User Interactions:**
- Tap Continue button: Proceed to Problem Statement screen
- Swipe left: Same as tapping Continue

**Visual Feedback:**
- Button scaling effect on press (95% → 100%)
- Button color brightens slightly on press

**Transition Out:**
- Slide left transition (300ms)
- Slight fade effect during slide

**Accessibility:**
- Screen readable by screen readers
- Tap anywhere on bottom half of screen as alternative to button

### 3. Problem Statement Screen

**Initial State:**
- Dark background with subtle visual noise pattern
- Copy "In a world full of digital noise, finding mental clarity feels impossible"
- Continue button at bottom
- Visual representation of mental chaos (particles/noise)

**User Interactions:**
- Tap Continue: Proceed to Value Proposition screen
- Swipe left: Same as tapping Continue

**Animation:**
- Subtle transition of chaos particles to more ordered state as user stays on screen

**Transition Out:**
- Slide left transition (300ms)
- Particle effect transitions into next screen

**Edge Cases:**
- Include back button/gesture for returning to previous screen

### 4. Value Proposition Screen

**Initial State:**
- Minimalist design with subtle background pattern
- Copy "Take control of your mental state with science-backed soundscapes"
- Supporting copy "NASA-inspired PEMF technology combined with vibroacoustic therapy for whole-body transformation"
- Continue button at bottom
- "Already a Vibrasonix User?" link at bottom

**User Interactions:**
- Tap Continue: Proceed to Drug Metaphor screen
- Tap "Already a Vibrasonix User?": Skip to Account Login screen
- Swipe left: Same as tapping Continue

**Transition Out:**
- Continue button: Slide left transition (300ms)
- "Already a User": Fade transition to Login screen (500ms)

**Visual Feedback:**
- Both buttons/links have press states with subtle color change

### 5. Drug Metaphor Screen

**Initial State:**
- Dark background
- Copy "Imagine a drug that could help you enhance focus & attention"
- Supporting copy "The Vibrasonix-Cube delivers therapeutic vibrations directly to your body through your bed"
- Key words "drug" and "enhance focus & attention" highlighted in brand colors
- Skip option in corner (subtle, not prominent)

**User Interactions:**
- Tap Skip: Go directly to Goal Selection screen
- Tap anywhere else/Continue: Proceed to Solution Reveal screen
- Swipe left: Proceed to Solution Reveal

**Edge Cases:**
- If user taps Skip, show brief toast message: "Skipping intro screens"

**Transition Out:**
- Standard slide left transition (300ms)
- Highlight colors briefly pulse before transition

### 6. Solution Reveal Screen

**Initial State:**
- Bold, centered text "That drug is sound"
- Word "sound" highlighted in brand color
- Visualization of sound waves (animated subtly)
- Continue button at bottom

**User Interactions:**
- Tap Continue: Proceed to Science Explanation
- Swipe left: Same as Continue

**Animation:**
- Sound wave visualization subtly pulses
- Word "sound" has slight glow effect

**Transition Out:**
- Slide left with sound wave visualization extending into next screen

### 7. Science Explanation Screen

**Initial State:**
- Copy "Binaural beats and PEMF technology synchronize your brainwaves to specific frequencies"
- Visual representation of brain synchronization with PEMF pulses
- Simple animation showing the concept
- Continue button at bottom

**User Interactions:**
- Tap Continue: Proceed to Goal Selection
- Tap animation: Animation replays with slightly enhanced effect
- Swipe left: Same as Continue

**Animation:**
- Brain wave synchronization effect (3-5s loop)
- Subtle particle effects connecting to next screen

**Transition Out:**
- Slide left with particles following

### 8. Goal Selection Screen

**Initial State:**
- Header "What would you like to achieve?"
- Subtitle "Select all that apply"
- 6 selectable cards with icons and text:
  - Get better sleep - Delta wave entrainment (0.5-4 Hz) for deep restorative sleep
  - Improve focus - Alpha and Gamma frequencies (8-12 Hz, 30-50 Hz) for enhanced cognition
  - Reduce stress & anxiety - Reduce cortisol levels and increase endorphins
  - Enhance meditation - Theta frequencies (4-7 Hz) for hypnagogic states
  - Sound healing - Vibroacoustic therapy across the 30-120 Hz therapeutic range
  - Spiritual exploration - Access expanded states of consciousness
- Continue button (disabled initially)

**User Interactions:**
- Tap on cards to select/deselect (multiple selection allowed)
- Selected cards show visual selected state
- Continue button enables after at least one selection
- Tap Continue: Proceed to Personalized Response

**Visual Feedback:**
- Cards have subtle hover/press state
- Selected cards have highlight border and slightly elevated appearance
- Continue button changes from disabled to enabled state once selections made

**Validation:**
- Error state if user taps Continue without selection
- Subtle shake animation + tooltip: "Please select at least one goal"

**Transition Out:**
- Selected cards briefly pulse before transition
- Standard slide left transition

### 9. Personalized Response Screen

**Initial State:**
- Copy "Vibrasonix can help with that"
- Supporting text "Our soundscapes use binaural beats that work with your Vibrasonix-Cube to create a complete therapeutic experience"
- Image of person with headphones
- Sound wave animation around head
- Continue button at bottom

**User Interactions:**
- Tap Continue: Proceed to Technology Familiarity
- Swipe left: Same as Continue

**Dynamic Content:**
- Text subtly references user's selected goals
- If user selected "focus", text includes "...effective for improving focus"
- If multiple goals selected, text mentions "...your selected goals"

**Animation:**
- Sound waves pulse around headphone image
- Subtle particle effects throughout screen

**Transition Out:**
- Standard slide left transition
- Particles follow through to next screen

### 10. Technology Familiarity Screen

**Initial State:**
- Copy "How familiar are you with binaural beats and PEMF technology?"
- 3 selection options:
  - "I'm new to this"
  - "I have some experience"
  - "I use them regularly"
- Each option has brief explanation text below
- Continue button at bottom (disabled initially)

**User Interactions:**
- Tap option to select (single selection only)
- Continue button enables after selection
- Tap Continue: Proceed to Experience Customization

**Visual Feedback:**
- Selected option has highlighted state
- Options have subtle hover/press state
- Continue button transitions from disabled to enabled

**Transition Out:**
- Selected option briefly pulses
- Standard slide left transition

### 11. Experience Customization Screen

**Initial State:**
- Copy "We'll customize your experience based on:"
- List of factors with icons:
  - "Your goals" (shows icons of selected goals)
  - "Science-backed frequencies" (frequency icon)
  - "PEMF intensity levels" (electromagnetic pulse icon)
  - "Optimal listening times" (clock icon)
- Continue button at bottom

**User Interactions:**
- Tap Continue: Proceed to Usage Recommendation
- Tap on factors: Shows subtle tooltip with more info
- Swipe left: Same as Continue

**Dynamic Content:**
- "Your goals" section shows miniature versions of user's selected goal icons

**Animation:**
- Subtle particle effects connecting the three factors
- Icons have very subtle floating animation

**Transition Out:**
- Standard slide left transition

### 12. Usage Recommendation Screen

**Initial State:**
- Copy "For best results, use Vibrasonix:"
- List with icons:
  - "With headphones" (headphone icon)
  - "With your Vibrasonix-Cube" (device icon)
  - "In a quiet space" (silence icon)
  - "For at least 15 minutes" (timer icon)
- Continue button at bottom

**User Interactions:**
- Tap Continue: Proceed to Account Creation
- Tap on recommendations: Shows subtle tooltip with more info
- Swipe left: Same as Continue

**Animation:**
- Icons have subtle highlight animation sequentially

**Transition Out:**
- Standard slide left transition

### 13. Account Creation / Login Screen

**Initial State:**
- Copy "Create your sonic journey"
- Email input field
- Password input field (if email selected)
- Social login options (Apple, Google, etc.)
- "Continue as guest" option at bottom
- Continue button (disabled until valid input)

**User Interactions:**
- Enter email: Standard email validation
- Enter password: Standard password requirements
- Tap social login: Proceed to OAuth flow
- Tap "Continue as guest": Skip to Subscription screen
- Tap Continue (after valid input): Create account and proceed

**Validation States:**
- Invalid email: Red outline + error message
- Weak password: Yellow outline + strength indicator
- Valid input: Green checkmark

**Transition States:**
- Loading spinner during account creation
- Success animation upon account creation

**Transition Out:**
- Success checkmark animation
- Fade transition to next screen

**Edge Cases:**
- Account already exists: Offer login option
- Failed account creation: Error message + retry
- Network error: Offline message + retry option

### 14. Subscription Screen

**Initial State:**
- Copy "Unlock the full power of sound"
- Free tier features (with checkmarks)
- Premium tier features (with checkmarks)
- Price options (monthly/yearly)
- 7-day free trial highlighted
- "Start Trial" button
- "Maybe Later" option in smaller text

**User Interactions:**
- Tap "Start Trial": Begin trial signup flow
- Tap "Maybe Later": Proceed to Main Experience with free tier
- Tap pricing toggle: Switch between monthly/yearly

**Visual Feedback:**
- Selected pricing option has highlighted state
- Yearly option shows savings percentage
- Trial button has prominent styling

**Transition Out:**
- Confetti animation for trial signup
- Standard transition for "Maybe Later"

**Edge Cases:**
- Payment method required: Show payment flow
- Previous subscription: Show renewal options
- Promo code: Add field for code entry

### 15. Main Experience / Home Screen

**Initial State:**
- Header "Your personalized soundscapes"
- Recommended tracks based on goals (horizontal scroll)
- Categories section (Sleep, Focus, etc.) (horizontal scroll)
- Recently played section if returning user
- Bottom navigation bar:
  - Home (selected)
  - Library
  - Search
  - Profile

**User Interactions:**
- Tap track: Go to playback screen
- Tap category: Go to category detail screen
- Scroll vertically: View more content
- Scroll horizontally: View more in each section
- Tap nav icons: Switch between main sections

**Dynamic Content:**
- Recommendations based on selected goals
- Time-of-day appropriate content (e.g., sleep content in evening)
- New content badges for fresh content

**Animation:**
- Subtle parallax effect on scrolling
- Track artwork has subtle hover state
- Currently playing track has animation indicator

## Transition Specifications

### Standard Transitions

**Screen to Screen:**
- Direction: Left to right for forward navigation
- Duration: 300ms
- Timing function: Ease-in-out
- Type: Slide with 10% fade blend

**Modal Popups:**
- Direction: Bottom up
- Duration: 400ms
- Timing function: Ease-out
- Type: Slide with subtle fade

**Dismissal:**
- Direction: Reverse of entry
- Duration: 250ms
- Timing function: Ease-in
- Type: Slide with fade

### Interactive Feedback

**Button Press:**
- Scale: 95% → 100%
- Duration: 200ms
- Color: Slight brightening (5-10%)

**Selection Change:**
- Highlight: Border pulse + color shift
- Duration: 300ms
- Additional: Subtle glow effect

**Success Actions:**
- Animation: Checkmark or success icon
- Duration: 500ms
- Sound: Subtle success tone (if sound enabled)

**Error States:**
- Animation: Gentle shake (3 oscillations)
- Duration: 300ms
- Visual: Red highlight + error icon
- Message: Appears below input with 200ms delay

## Edge Cases & Error Handling

### Network Issues

**Poor Connection:**
- Loading skeleton screens instead of blank states
- Retry buttons for failed content loads
- Offline mode for previously loaded content

**Authentication Errors:**
- Clear error messages with specific problems
- Account recovery options prominently displayed
- Guest mode fallback option

### User Path Variations

**Returning Users:**
- Skip onboarding flow
- "Welcome back" screen with personalized greeting
- Resume previous session option

**Subscription Lapsed:**
- Gentle reminder about benefits lost
- Easy renewal process
- Limited functionality clearly indicated

### Accessibility Considerations

**Vision Impairments:**
- All screens compatible with screen readers
- Text scaling without breaking layouts
- High contrast mode option

**Motor Limitations:**
- Touch targets minimum 44x44pt
- Alternative input methods supported
- Reduced motion option for animations

## Implementation Notes

- Ensure all transitions maintain 60fps performance
- Cache heavy animations for smoother playback
- Preload next screen assets for seamless transitions
- Implement proper error boundary handling for all screens
- Track analytics events at key interaction points
- Consider memory usage for older devices
