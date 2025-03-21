# Components

## Core Components

### CrystalContainer
- **Description:** The main container component that houses the sound wave visualization and playback controls. It provides the visual context for the sound therapy session, representing a "crystal" or immersive space for sound.
- **Visual Representation:**  *(Need to add a visual - perhaps a simple box diagram or a mockup reference)*  Imagine a visually distinct container with a slightly abstract, crystal-like appearance, possibly with subtle gradients or animations to enhance the visual appeal.
- **Key Properties:**
    - `soundscape`:  The soundscape data to be visualized and played within the container.
    - `theme`:  Styling properties to customize the container's appearance (colors, backgrounds).
    - `controlsPosition`:  Property to define the placement of `CrystalControls` (e.g., bottom, overlay).

### CrystalWaveform
- **Description:**  A component responsible for visualizing the sound wave of the currently playing soundscape. It provides real-time visual feedback of the audio, enhancing the user's engagement with the sound therapy.
- **Visual Representation:** *(Need to add a visual - perhaps a waveform diagram or mockup reference)*  Visualize an animated waveform that reacts to the audio output, possibly with customizable colors and styles to match the app's design language.
- **Key Properties:**
    - `audioData`:  The audio data stream to be visualized.
    - `waveformStyle`:  Properties to customize the waveform's appearance (color, thickness, animation style).
    - `isInteractive`:  Boolean to determine if the waveform is interactive (e.g., for seeking within the soundscape).

### CrystalControls
- **Description:**  A component that provides the primary playback controls for the soundscape session. It includes buttons for play/pause, skip, volume adjustment, and potentially other session-related controls.
- **Visual Representation:** *(Need to add a visual - perhaps button mockups or a control panel diagram)*  Imagine a set of minimalist, easily recognizable control icons (play, pause, skip, volume) arranged in a user-friendly layout, possibly with touch feedback animations.
- **Key Properties:**
    - `isPlaying`:  Boolean to indicate the current playback state.
    - `onPlayPause`:  Function to handle play/pause actions.
    - `onSkip`:  Function to handle skipping to the next soundscape.
    - `onVolumeChange`: Function to handle volume adjustments.


## CymaticVisualizer
- **Description:** A dynamic visualization component that displays cymatics patterns (visible patterns created by sound vibrations) that respond in real-time to the audio being played. This would replace or complement the standard album art on the now playing screen.
- **Visual Representation:** Fluid, organic patterns that morph and evolve based on the frequency, amplitude, and characteristics of the current soundscape. The patterns would be scientifically accurate representations of how sound waves physically affect matter (like sand or water).
- **Key Properties:**
    - `audioData`: The audio data stream to visualize
    - `visualizationStyle`: Different cymatics styles (water surface, sand patterns, particle systems)
    - `colorScheme`: Color palette that can match the therapeutic intent (e.g., calming blues for sleep, energizing golds for focus)
    - `responsiveness`: How quickly the visualization responds to audio changes
    - `detailLevel`: Adjustable detail level for different device capabilities

## HapticResonance
- **Description:** A sophisticated haptic feedback system that translates sound frequencies into precise vibration patterns delivered through the phone's haptic engine. This creates a multi-sensory experience where users can "feel" the sound therapy.
- **Key Properties:**
    - `frequencyMapping`: Maps audio frequencies to specific haptic patterns
    - `intensityControl`: User-adjustable intensity of haptic feedback
    - `therapeuticPatterns`: Pre-designed haptic patterns based on research (e.g., sleep-inducing, focus-enhancing)
    - `syncMode`: Options to sync with audio peaks, specific frequencies, or therapeutic rhythms


### Buttons
- **Description:**  Standard button components used throughout the app for actions and navigation. Styles will vary based on context (primary, secondary, text-based).
- **Types:**
    - `PrimaryButton`:  Main action buttons, using the accent color (Gold) for emphasis.
    - `SecondaryButton`:  Supporting action buttons, using the secondary color (Teal Blue).
    - `TextButton`:  Text-based buttons for less prominent actions or navigation.
- **Key Properties:**
    - `label`:  Text displayed on the button.
    - `onClick`:  Function to execute when the button is pressed.
    - `styleVariant`:  To specify the button style (primary, secondary, text).

### Sliders
- **Description:**  Interactive slider components for adjusting values like volume, intensity, or session duration.
- **Visual Style:**  Clean and minimalist sliders, consistent with the app's design language, providing clear visual feedback of the current value.
- **Key Properties:**
    - `value`:  Current value of the slider.
    - `min`:  Minimum value.
    - `max`:  Maximum value.
    - `onChange`:  Function to handle value changes.

### Cards
- **Description:**  Container components for displaying information in a structured and visually appealing way. Used for soundscape previews, goal selections, and other content blocks.
- **Types:**
    - `SoundscapeCard`:  For displaying soundscape information (title, description, duration, preview image).
    - `GoalCard`:  For displaying goal options during onboarding and personalization.
- **Key Properties:**
    - `title`:  Title of the card.
    - `description`:  Descriptive text.
    - `media`:  Optional image or icon.
    - `onClick`:  Function to handle card clicks.


## Animation Elements

### Transitions
- **Description:**  Subtle transitions between screens and UI states to create a smooth and engaging user experience.  Examples include fade-in/out, slide transitions, and animated element reveals.
- **Types:**
    - `FadeTransition`:  Fades elements in or out.
    - `SlideTransition`:  Slides elements in from different directions.
    - `ScaleTransition`:  Scales elements up or down.
- **Implementation Notes:**  Prioritize performance optimization for transitions to maintain 60fps.

### Ripple Effects
- **Description:**  Visual feedback for touch interactions, providing a subtle "ripple" animation when buttons or interactive elements are pressed.
- **Purpose:**  Enhances the sense of touch and provides clear visual confirmation of user interactions.
- **Style:**  Use the secondary color (Teal Blue) for ripple effects to maintain visual consistency.
- **Implementation Notes:**  Ensure ripple effects are performant and do not introduce lag or jankiness.

This document provides a detailed overview of the core components, reusable widgets, and animation elements that will be used to build the Vibrasonix app UI.  Visual mockups and further specifications will be provided in subsequent design documentation.
