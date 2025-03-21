# UI Overview

## Design Language

Referencing the [Vibrasonix Master Reference Guide](docs/Vibrasonix_Master_Reference.md), the design language is defined by:

- **Color Palette:**
    - Primary: Deep Blue (#1A1A2E) - Base UI, depth, possibility
    - Secondary: Teal Blue (#48AAAD) - Interactive elements, highlights
    - Accent: Gold (#FFBD00) - Logo, accents, premium features
    - Text: White (#FFFFFF) and Light Gray (#E0E0E0) - Readability
    - Highlight: Teal Blue (#48AAAD) - Keywords in copy

- **Typography:**  
  - **Headers:** Montserrat Bold, 24-30pt  
  - **Body Text:** Open Sans Light, 16-18pt  
  - **Button Text:** Montserrat Medium, 18pt  
  - **Highlighted Terms:** #48AAAD color  

- **Iconography:**  
  - **Goal Category Icons:** 80x80px, line icons, #FFFFFF with glow  
  - **Navigation Icons:** 60x60px, line icons, #FFFFFF (inactive), #48AAAD (active)  
  - **Format:** SVG for scalability  

## Core Screens

- **Home Screen:**
    - **Purpose:**  The main entry point to the app, providing personalized content recommendations and quick access to core features.
    - **Key Elements:**  Personalized soundscape suggestions based on user goals, categories for browsing content, prominent search functionality, and navigation to other core screens (Session, Profile).
    - **Visual Style:**  Emphasize visual-sonic harmony with subtle animations and visualizations that reflect the sound therapy experience.

- **Session Screen:**
    - **Purpose:**  Dedicated screen for users to engage with sound therapy sessions, offering playback controls and real-time feedback.
    - **Key Elements:**  Prominent playback controls (play/pause, skip, volume), session timer, waveform visualization of the soundscape, intensity and duration adjustments, and potential integration with Vibrasonix-Cube controls.
    - **Visual Style:**  Immersive and focused, minimizing distractions and enhancing the therapeutic experience with calming visuals.
    - **Cymatics Visualization:** Dynamic cymatics patterns that respond in real-time to the audio being played, providing a visual representation of sound vibrations.
    - **Haptic Feedback Controls:** User-adjustable intensity of haptic feedback to enhance the multi-sensory experience.
    - **Purpose:**  Dedicated screen for users to engage with sound therapy sessions, offering playback controls and real-time feedback.
    - **Key Elements:**  Prominent playback controls (play/pause, skip, volume), session timer, waveform visualization of the soundscape, intensity and duration adjustments, and potential integration with Vibrasonix-Cube controls.
    - **Visual Style:**  Immersive and focused, minimizing distractions and enhancing the therapeutic experience with calming visuals.

- **Profile Screen:**
    - **Purpose:**  Allows users to manage their account, preferences, track progress, and access settings.
    - **Key Elements:**  User account information, goal settings, history of sessions, progress visualizations, subscription management, app settings (accessibility, notifications), and links to help/support resources.
    - **Visual Style:**  Clean and organized, providing a sense of personal control and progress.

## Navigation Flow

- **User Journey Map:** (To be created -  a visual map detailing the user's path through the app, from onboarding to core feature usage. This will be detailed in a separate document or section).  The user journey is designed to be linear and intuitive, guiding new users smoothly through onboarding and into the core experience. Key interaction points are designed to be clear and engaging, encouraging users to explore the app's features.

- **Interaction Points:**
    - **Touch Gestures:**  Primary interaction method, utilizing taps, swipes, and long presses for navigation and control.
    - **Visual Cues:**  Clear visual feedback for interactions, such as button highlights, animation responses, and progress indicators.
    - **Haptic Feedback:** (Optional) Subtle haptic feedback to enhance the sense of touch and interaction confirmation.
    - **Voice Control:** (Future consideration) Potential integration of voice commands for playback control and navigation for enhanced accessibility and user convenience.

## Visual Style based on Beta Version

Based on the provided images of the beta version:

- **Overall Aesthetic:** The UI maintains a dark, immersive aesthetic with teal and gold accents, aligning with the "cosmic-neural" theme.
- **Dark Mode:** The app predominantly uses a dark background, enhancing focus and reducing eye strain, especially suitable for relaxation and sleep-focused use cases.
- **Color Accents:** Teal blue is consistently used for interactive elements and highlights, while gold accents are sparingly used for key branding elements and premium features, maintaining a balance and avoiding over-stimulation.
- **Typography:** Clean, sans-serif fonts are used throughout the app, ensuring excellent readability on dark backgrounds. Font sizes are well-chosen for hierarchy and comfortable reading.
- **Iconography:** Minimalist line icons are employed for navigation and controls. These icons are clear, consistent, and contribute to the clean, modern look of the app.
- **Imagery:** Abstract and subtle background imagery is used in some screens, adding visual interest without distracting from the core content.

## UI Mockups and Beta Version References

- **General Style:** Refer to the attached images and the beta version screenshots for a comprehensive understanding of the visual style, color palette, typography, and iconography.
- **Screen Layouts:**
    - **Home Screen:**  The beta version's home screen (see "MOONGATE" screenshot) demonstrates a layout with a prominent header, categorized content presented in cards, and a bottom navigation bar for core screen access.
    - **Session Screen:** The "All My" and "Frequency Intensity" screenshots illustrate the session screen layout, featuring a waveform visualization at the top, playback controls at the bottom, and session details in the middle section.
    - **Profile Screen:** The "Settings" screenshot shows a list-based layout for the profile/settings screen, typical for account management and app preferences.
- **Component Implementation:**
    - **Buttons:**  Various button styles are visible in the screenshots, including solid colored buttons (e.g., gold "Continue" button), outlined buttons (e.g., "Try for free"), and text-based buttons (e.g., "Skip").
    - **Cards:**  Cards are used extensively to display soundscapes, categories, and options, as seen in the "We've got" and "What would you like" screenshots.
    - **Sliders:**  Volume control sliders are visible in the session screen screenshots, demonstrating their minimalist and functional design.

These observations and references to the beta version images should provide a clearer and more concrete understanding of the intended UI and visual style for the Vibrasonix app.

## UI Components

- For details on reusable UI components, refer to [V1/components.md](V1/components.md). This document outlines the core components and reusable widgets used throughout the app's UI, ensuring consistency and efficiency in development. Key components include: CrystalContainer, CrystalWaveform, CrystalControls, Buttons, Sliders, and Cards.

This overview provides a foundation for the UI design, detailing the design language, core screens, navigation flow, and components. Further detailed specifications and mockups will be elaborated in subsequent documentation.
