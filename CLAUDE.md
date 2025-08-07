# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is the "Uranus Universe" interactive web application - a space-themed clicker game where users can click on a 3D Uranus planet. The project is built as a single HTML file with embedded JavaScript and uses Three.js for 3D graphics.

## Project Structure

- `index.html` - Main application file containing all HTML, CSS, and JavaScript
- `Assets/` - Contains planet sprite animation frames (First.png, second.png, third.png, fourth.png)
- `sound_effects/` - Audio files for fart sounds and other effects
- `contextt.md` - Detailed project documentation and development plan

## Architecture

The application is built around a single `UranusUniverse` class that manages:
- **3D Scene**: Three.js scene with camera, renderer, and lighting
- **Planet Animation**: 4-frame sprite animation using HTML5 Canvas and Three.js textures
- **Audio System**: Web Audio API and HTML5 Audio for sound effects
- **Particle Systems**: Fart particles and explosion effects
- **Flying Objects**: Procedurally spawned rockets, UFOs, asteroids, and satellites
- **Game State**: Click counting, progress saving via localStorage
- **Easter Eggs**: Special animations and sounds at milestone click counts

## Key Classes and Components

### UranusUniverse Class
Main application controller located in `index.html:119-864`

Key methods:
- `createUranus()` - Sets up the 2D plane with sprite animation
- `loadCustomImageSequence()` - Loads 4-frame planet animation
- `playClickAnimation()` - Cycles through animation frames on click
- `touchUranus()` - Handles planet click events
- `spawnFlyingObject()` - Creates random space objects
- `checkEasterEggs()` - Triggers special events at milestone counts

### Animation System
- Uses HTML5 Canvas for sprite rendering with transparency
- 4-frame sequence: First.png (idle) → second.png → third.png → fourth.png → First.png
- Frame timing: 100ms per frame for click animation

### Audio System
- Primary fart sound: `sound_effects/proud-fart-288263.mp3`
- Fallback synthetic sounds using Web Audio API
- Mute toggle functionality

## Development Commands

This project has no build system - it's a static HTML file that can be:
- Opened directly in a browser
- Served via any HTTP server (e.g., `python -m http.server`)
- No compilation, linting, or testing commands available

## Key Features

1. **Interactive 3D Planet**: Click the Uranus planet to trigger animations and sounds
2. **Flying Objects**: Random space objects that can be clicked for explosions
3. **Easter Eggs**:
   - 69 clicks: Special celebration
   - 100 clicks: "Enter Uranus Mode" with camera zoom
   - 420 clicks: Rainbow color effect
4. **Particle Effects**: Animated particles for interactions and explosions
5. **Progress Persistence**: Click count saved in localStorage
6. **Mobile Support**: Touch-friendly design with responsive layout

## Asset Requirements

- Planet sprites must be in `Assets/` folder with exact filenames:
  - `First.png` (normal state)
  - `second.png`, `third.png`, `fourth.png` (animation frames)
- Audio files in `sound_effects/` folder
- All assets use case-sensitive filenames

## Libraries Used

- **Three.js v0.128.0**: 3D graphics and rendering
- **Motion.js v10**: Animation library for camera effects and UI animations
- **Native Web APIs**: Canvas, Audio, LocalStorage

## Browser Compatibility

- Requires modern browsers with WebGL support
- Mobile Safari and Chrome tested
- Audio requires user interaction to start (handled automatically on first click)

## Testing

No formal testing framework. Manual testing recommended for:
- Cross-browser compatibility (Chrome, Firefox, Safari)
- Mobile device testing (touch events, performance)
- Audio playback on different platforms
- Asset loading and animation timing