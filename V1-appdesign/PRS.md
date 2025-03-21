# Product Requirements Specification - Vibrasonix Mobile App  
**Version:** 2.0  
**Effective Date:** March 22, 2025  
**Author:** Product Team  

## 1. Introduction
### 1.1 Document Purpose  
Formalizes requirements for Vibrasonix v1 mobile app implementing core wellness technology stack (binaural beats, PEMF, vibroacoustic therapy) as defined in PRD v3.1.

### 1.2 Scope
Covers iOS/Android app development for:
- User onboarding & personalization engine
- Bioadaptive soundscape delivery system
- Therapy session management
- Basic user profile/authentication

Excludes:  
- Hardware integration (covered in HRS-22)  
- AI recommendation engine (Q3 roadmap)  

## 2. Functional Requirements

### 2.1 Authentication Gateway
#### 2.1.1 Secure Access System
- [FR-101] Multi-factor authentication (email + 6-digit SMS)  
- [FR-102] Session management:  
  - 15min inactivity timeout  
  - Simultaneous sessions per device type (mobile:1, tablet:2)  
- [FR-103] Password requirements:  
  - 12+ chars with 1 symbol/number  
  - bcrypt hashing (work factor 12)  

#### 2.1.2 Profile Management
- [FR-104] Biometric authentication toggle (TouchID/FaceID)  
- [FR-105] Session history view with device/location metadata  
- [FR-106] Email verification workflow (OTP confirmation)

### 2.3 Soundscape Playback and Control
    - **Robust Audio Playback Engine**: Provide a robust and reliable audio playback engine capable of seamlessly handling:
        - Binaural beats: Generate and decode binaural beat frequencies accurately.
        - PEMF frequencies: Integrate PEMF signals into the soundscapes (if audio representation is applicable).
        - Vibroacoustic therapy soundscapes: Support playback of complex soundscapes designed for vibroacoustic therapy.
        - Support various audio formats (e.g., MP3, WAV, FLAC) for content flexibility.
    - **Intuitive Playback Controls**: Implement a set of intuitive and easily accessible playback controls, including:
        - Play/Pause: Start and interrupt soundscape playback.
        - Stop: Fully stop playback and reset session.
        - Skip (Next/Previous): Navigate between soundscapes in a playlist or curated journey.
        - Volume Adjustment: Precise volume control for comfortable listening levels.
        - Session Timer: Allow users to set a timer for sessions, with optional fade-out at the end.
        - Intensity Control: Implement controls for adjusting the intensity or level of therapy (if technically feasible and relevant to soundscape design).
    - **Background Playback Support**: Ensure continuous soundscape playback even when the app is minimized or the device screen is locked.
        - Maintain playback state and controls in background mode.
        - Provide clear user notification when app is playing in the background.
    - **Error Handling**: Implement robust error handling for playback issues.
        - Display user-friendly error messages for common issues (e.g., file not found, unsupported format).
        - Log errors for further analysis and debugging.
    - **Performance Optimization**: Ensure smooth playback and minimal resource usage.
        - Optimize audio decoding and playback to prevent stuttering.
        - Minimize CPU and memory usage during playback.
        - Implement efficient buffering strategies to handle network latency.
    - **Cymatics Visualization**: Implement high-performance rendering for real-time cymatics patterns that respond to audio data.
        - Use WebGL or Metal for high-performance rendering.
        - Implement frequency analysis using FFT (Fast Fourier Transform).
        - Create physics-based simulations that accurately represent how different frequencies affect physical media.
        - Include presets based on therapeutic goals (sleep, focus, meditation).
        - Allow users to swipe between album art and cymatics visualization.
    - **Haptic Feedback**: Leverage advanced haptic engines in modern smartphones to deliver precise vibration patterns that correspond to audio frequencies.
        - Create frequency-specific haptic patterns based on research into which vibrations are most therapeutic.
        - Implement battery-saving modes for extended sessions.
        - Design haptic patterns that complement the Vibrasonix-Cube hardware for a unified experience.
        - Include accessibility options for users with different sensory sensitivities.

### 2.2 User Onboarding System
#### 2.2.1 Progressive Personalization Flow
        - Utilize visual cues, animations, and progress indicators to enhance user engagement.
        - Keep the tutorial concise and focused on essential features for first-time use.
        - **Implementation Priorities:**
            - **Onboarding Flow:** Smooth transitions, compelling visuals, clear value proposition.
            - **Personalization:** Goal selection, dynamic content, clear feedback.
            - **Conversion Points:** Minimal friction for account creation, clear premium value.
            - **Core Experience:** Personalized content display, intuitive navigation, seamless playback.
    - **Value Proposition Communication**: Clearly communicate the unique value and benefits of Vibrasonix early in the onboarding flow.
        - Highlight the science-backed approach, integrated hardware-software solution, and personalized journey.
        - **Key Differentiators:**
            - **Science-Backed Approach:** Research-based soundscapes and PEMF patterns.
            - **Integrated Hardware-Software Solution:** Vibrasonix-Cube enhances therapy.
            - **Personalized Journey:** User goals drive content recommendations.
            - **Visual-Sonic Harmony:** UI elements reinforce the sonic experience.
            - **Cosmic-Neural Aesthetic:** Unique blend of cosmic and neural visuals.
    - **Goal Selection**: Integrate a goal selection screen early in onboarding to personalize the app experience.
        -  Offer a predefined list of wellness goals (sleep, focus, stress reduction, meditation) as outlined in the PRD.
        -  Consider incorporating a "rank goals" feature as suggested in `docs/improvements.md` for enhanced personalization.
    - **Personalization Introduction**: Introduce the concept of personalized soundscapes and content recommendations based on user goals.
        -  Show a preview of how selected goals will tailor the app experience.
        -  Potentially integrate a brief (15-second) audio sample during onboarding to provide immediate value and demonstrate the app's core functionality.
        - **Onboarding Content Preview:**
            - **Issue:** Users can't experience the value until completing onboarding.
            - **Solution:** Integrate brief (15-second) audio samples during onboarding.
                - Add "Try Now" buttons on key screens that play sample content.
                - Include visualization of sound/PEMF effects to create anticipation.
                - Allow users to feel immediate benefit before completing the full flow.

### 2.3 Soundscape Playback and Control
    - **Robust Audio Playback Engine**: Provide a robust and reliable audio playback engine capable of seamlessly handling:
        - Binaural beats: Generate and decode binaural beat frequencies accurately.
        - PEMF frequencies: Integrate PEMF signals into the soundscapes (if audio representation is applicable).
        - Vibroacoustic therapy soundscapes: Support playback of complex soundscapes designed for vibroacoustic therapy.
        - Support various audio formats (e.g., MP3, WAV, FLAC) for content flexibility.
    - **Intuitive Playback Controls**: Implement a set of intuitive and easily accessible playback controls, including:
        - Play/Pause: Start and interrupt soundscape playback.
        - Stop: Fully stop playback and reset session.
        - Skip (Next/Previous): Navigate between soundscapes in a playlist or curated journey.
        - Volume Adjustment: Precise volume control for comfortable listening levels.
        - Session Timer: Allow users to set a timer for sessions, with optional fade-out at the end.
        - Intensity Control: Implement controls for adjusting the intensity or level of therapy (if technically feasible and relevant to soundscape design).
    - **Background Playback Support**: Ensure continuous soundscape playback even when the app is minimized or the device screen is locked.
        - Maintain playback state and controls in background mode.
        - Provide clear user notification when app is playing in the background.
    - **Error Handling**: Implement robust error handling for playback issues.
        - Display user-friendly error messages for common issues (e.g., file not found, unsupported format).
        - Log errors for further analysis and debugging.
    - **Performance Optimization**: Ensure smooth playback and minimal resource usage.
        - Optimize audio decoding and playback to prevent stuttering.
        - Minimize CPU and memory usage during playback.
        - Implement efficient buffering strategies to handle network latency.

### 2.4 User Analytics and Insights
    - **Usage Tracking**: Implement tracking of user interactions and session data.
        - Track play/pause, skip, and volume adjustments.
        - Record session duration and frequency of use.
    - **Progress Monitoring**: Provide users with insights into their progress and usage patterns.
        - Display usage statistics and trends over time.
        - Offer personalized recommendations based on usage data.
    - **Data Privacy**: Ensure user data is handled securely and transparently.
        - Implement data anonymization and encryption.
        - Provide users with control over their data and privacy settings.

## 3. Non-Functional Requirements

### 3.1 Performance
    - **Responsiveness**: Ensure the app responds to user interactions within 100ms.
    - **Scalability**: Design the app to handle a growing number of users and content without performance degradation.
    - **Reliability**: Ensure the app operates reliably under various conditions, including poor network connectivity.

### 3.2 Security
    - **Data Protection**: Implement encryption for sensitive user data both in transit and at rest.
    - **Authentication**: Use secure authentication mechanisms, including multi-factor authentication.
    - **Authorization**: Ensure proper access controls are in place to protect user data and app functionality.

### 3.3 Usability
    - **Accessibility**: Ensure the app is accessible to users with disabilities, following WCAG 2.1 guidelines.
    - **User Experience**: Design the app to be intuitive and user-friendly, with a focus on smooth navigation and interaction.

## 4. Appendices

### 4.1 Glossary
    - **Binaural Beats**: Auditory illusions created by playing slightly different frequencies in each ear.
    - **PEMF**: Pulsed Electromagnetic Field, a type of therapy that uses electromagnetic fields to promote healing.
    - **Vibroacoustic Therapy**: A therapy that uses sound vibrations to promote physical and mental well-being.

### 4.2 References
    - **PRD v3.1**: Product Requirements Document version 3.1.
    - **HRS-22**: Hardware Requirements Specification for Vibrasonix-Cube.
    - **WCAG 2.1**: Web Content Accessibility Guidelines version 2.1.
