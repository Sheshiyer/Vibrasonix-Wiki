# Visual Style Guide

## Visual Identity

The Vibrasonix app embodies a "Cosmic-Neural" aesthetic that blends cosmic imagery with neural network visualizations, creating a unique visual language that communicates both the scientific foundation and transcendent experience of sound therapy.

### Key Visual Elements

- **Cosmic Elements:** Abstract space-like backgrounds, subtle nebula patterns, and star-like particles that create depth and wonder.
- **Neural Patterns:** Interconnected node visualizations, wave patterns, and frequency representations that suggest the app's scientific basis.
- **Crystal Metaphor:** The central visual metaphor of the app, representing clarity, transformation, and the focusing of energy.
- **Cymatics Visualization:** Dynamic patterns that visualize sound frequencies, creating a direct visual representation of the audio experience.

## Color Palette

### Primary Colors

- **Deep Blue (#1A1A2E):** Primary background color, creating depth and a sense of possibility
- **Teal Blue (#48AAAD):** Used for interactive elements, highlights, and active states
- **Gold (#FFBD00):** Used for the logo, accents, and premium features

### Secondary Colors

- **White (#FFFFFF):** Primary text color for maximum readability on dark backgrounds
- **Light Gray (#E0E0E0):** Secondary text color for less emphasis
- **Dark Gray (#2D2D3A):** Used for cards, containers, and secondary backgrounds

### Functional Colors

- **Success Green (#4CAF50):** Used for success messages and positive indicators
- **Warning Orange (#FF9800):** Used for warnings and alerts
- **Error Red (#F44336):** Used for error messages and critical alerts

### Color Usage Guidelines

- Maintain high contrast ratios (minimum 4.5:1) for text legibility
- Use the teal blue highlight color sparingly to draw attention to key interactive elements
- Reserve gold accents for premium features and important call-to-action elements
- Create depth through subtle gradients of the deep blue background color

## Typography

### Font Families

- **Headers:** Montserrat Bold
- **Body Text:** Open Sans Light
- **Button Text:** Montserrat Medium
- **Highlighted Terms:** Open Sans Medium with teal blue (#48AAAD) color

### Font Sizes

- **H1 (Screen Titles):** 30pt
- **H2 (Section Headers):** 24pt
- **H3 (Card Titles):** 20pt
- **Body Text:** 16-18pt
- **Button Text:** 18pt
- **Caption Text:** 14pt

### Typography Guidelines

- Maintain consistent line heights (1.5x font size for body text)
- Use font weight to create hierarchy rather than multiple font sizes
- Ensure adequate spacing between text elements (minimum 8px vertical spacing)
- Limit line length to 60-75 characters for optimal readability
- Use left alignment for most text (center alignment only for short, prominent text)

## Iconography

### Style Guidelines

- **Line Style:** Clean, minimalist line icons with consistent stroke width (2px)
- **Corners:** Slightly rounded corners (2px radius) for a soft, approachable feel
- **Size:** 24x24px base size, scaling to 60x60px for navigation and 80x80px for goal category icons
- **Color:** Primary white (#FFFFFF) for inactive state, teal blue (#48AAAD) for active state
- **Format:** SVG for scalability and performance

### Icon Categories

- **Navigation Icons:** Home, Session, Profile, Settings
- **Playback Controls:** Play, Pause, Skip, Volume, Timer
- **Goal Category Icons:** Sleep, Focus, Stress Relief, Meditation
- **Functional Icons:** Search, Notifications, Add, Close, Back, Menu

### Icon Usage

- Maintain consistent padding within the icon bounding box (minimum 2px)
- Use subtle glow effects for emphasis in dark UI contexts
- Pair icons with text labels for clarity when introducing new features
- Animate icons subtly to provide feedback for user interactions

## UI Element Styling

### Containers & Cards

- **Background:** Dark gray (#2D2D3A) with subtle gradient
- **Corner Radius:** 12px for cards, 16px for main containers
- **Shadow:** Subtle inner glow (1-2px) in teal blue (#48AAAD) at 10% opacity
- **Border:** Optional 1px border in teal blue (#48AAAD) at 20% opacity for emphasis

### Buttons

- **Primary Button:**
  - Background: Gold (#FFBD00)
  - Text: Deep Blue (#1A1A2E)
  - Corner Radius: 24px
  - Height: 48px
  - Padding: 16px horizontal

- **Secondary Button:**
  - Background: Teal Blue (#48AAAD)
  - Text: White (#FFFFFF)
  - Corner Radius: 24px
  - Height: 48px
  - Padding: 16px horizontal

- **Text Button:**
  - Text: White (#FFFFFF)
  - Underline: None (optional on hover)
  - Padding: 8px

### Input Fields

- **Background:** Deep Blue (#1A1A2E)
- **Border:** 1px Teal Blue (#48AAAD) at 40% opacity
- **Text:** White (#FFFFFF)
- **Corner Radius:** 8px
- **Height:** 48px
- **Padding:** 16px horizontal, 12px vertical

### Sliders & Controls

- **Track:** Deep Blue (#1A1A2E) with 1px border in white at 20% opacity
- **Thumb:** Teal Blue (#48AAAD) circle, 20px diameter
- **Active Track:** Teal Blue (#48AAAD)
- **Height:** 4px for track, 20px for touch target

## Imagery & Illustration

### Background Patterns

- **Style:** Abstract, fluid patterns inspired by cymatics and neural networks
- **Color:** Deep blue base with subtle teal and gold accents
- **Opacity:** 10-30% to maintain text legibility
- **Animation:** Subtle, slow-moving animations that respond to user interaction

### Soundscape Imagery

- **Style:** Abstract representations of sound frequencies and waveforms
- **Color:** Palette varies based on soundscape category (cool tones for sleep, warm tones for focus)
- **Composition:** Centered focal point with radiating elements
- **Format:** Vector-based for performance and scalability

### Onboarding Illustrations

- **Style:** Clean, minimalist illustrations with subtle gradients
- **Color:** Primarily teal and gold on deep blue backgrounds
- **Content:** Visual representations of app benefits and features
- **Animation:** Simple reveal animations to enhance engagement

## Animation & Motion

### Transitions

- **Screen Transitions:** Smooth fade transitions (300ms duration)
- **Element Transitions:** Subtle scale and fade effects (200-250ms duration)
- **Easing:** Ease-out for entering elements, ease-in for exiting elements

### Interactive Feedback

- **Button Press:** Subtle scale down (95%) and brightness increase
- **Ripple Effect:** Radial ripple in teal blue for touch interactions
- **Toggle States:** Smooth transitions between states (150ms duration)

### Playback Visualizations

- **Waveform:** Responsive audio visualization with smooth animation
- **Cymatics:** Physics-based particle systems that respond to audio frequencies
- **Loading States:** Pulsing animation in teal blue (subtle, not distracting)

### Animation Principles

- Prioritize performance (60fps target)
- Use animation purposefully to guide attention and provide feedback
- Maintain subtlety to avoid distraction from the core experience
- Ensure animations support the calming, therapeutic nature of the app

## Accessibility Considerations

### Color Contrast

- Maintain minimum contrast ratios:
  - 4.5:1 for normal text
  - 3:1 for large text (18pt+)
  - 3:1 for UI components and graphical objects

### Text Legibility

- Provide options for increased text size
- Maintain adequate line spacing (minimum 1.5x)
- Ensure text remains legible over background patterns

### Touch Targets

- Minimum touch target size of 44x44px
- Adequate spacing between interactive elements (minimum 8px)

### Visual Alternatives

- Provide text alternatives for visual information
- Include options to reduce motion and animation
- Support system-level accessibility features (dynamic type, VoiceOver, TalkBack)

## Implementation Guidelines

### Design System Components

The visual style should be implemented through a consistent design system with reusable components as detailed in [components.md](components.md). Key components include:

- CrystalContainer
- CrystalWaveform
- CrystalControls
- CymaticVisualizer
- HapticResonance
- Buttons (Primary, Secondary, Text)
- Sliders
- Cards (Soundscape, Goal)

### Platform Adaptations

While maintaining visual consistency across platforms, adapt to platform-specific guidelines where appropriate:

- **iOS:** Respect safe areas, adapt to Dynamic Type, support Dark Mode
- **Android:** Follow Material Design principles for motion and elevation, support system themes

### Performance Considerations

- Optimize animations and transitions for 60fps performance
- Use vector assets where possible for resolution independence
- Implement progressive loading for complex visualizations
- Consider battery impact for long-duration sessions

This visual style guide provides a comprehensive framework for creating a cohesive, engaging, and accessible user interface for the Vibrasonix app, aligned with the product requirements and brand identity.
