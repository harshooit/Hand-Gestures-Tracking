# Hand-Gestures-Tracking
# HARSHIT TEST SUBJECT 42 – Gesture-Controlled Particle Experiment

A cyberpunk-themed, browser-based experiment where hand gestures control a 3D particle construct rendered with Three.js and tracked using MediaPipe Hands.

## Project Overview

This project simulates a **neural-sync** console for “Harshit TS-42”, where the user:
- Lands on a SYSTEM BOOT screen and connects as “SUBJECT 42”.
- Initiates an experiment that visualizes gesture-controlled particle shapes in 3D (sphere, heart, Saturn-like ring, flower, DNA helix, etc.).
- Views an in-universe “mission log” describing the subject profile and tech stack in a stylized terminal UI.

The UI uses a retro green-on-black CRT look with scanlines, glitch text effects, and hacker-style buttons.

## Tech Stack

- **Three.js** – WebGL renderer for the particle system and 3D camera.
- **Google MediaPipe Hands** – Real-time hand landmark detection and tracking from the webcam feed.
- **Vanilla JavaScript** – Core logic for particles, shape morphing, gesture interpretation, and HUD updates.
- **HTML/CSS** – Multi-page layout (index, experiment, mission) with CRT, glitch, and HUD styling.

External libraries are loaded via CDN in `experiment.html` (Three.js, MediaPipe camera/control/drawing utils, and Hands).

## Features

- **Landing / Mainframe (`index.html`)**  
  - “SYSTEM BOOT” screen with animated typewriter text and status panel.  
  - Navigation buttons: “INITIATE EXPERIMENT” → `experiment.html`, “VIEW MISSION LOGS” → `mission.html`.  

- **Gesture Experiment (`experiment.html`)**  
  - Full-screen WebGL canvas with a 15,000-particle system that morphs into different constructs (SPHERE, HEART, SATURN, FLOWER, DNA HELIX).  
  - HUD overlay showing system status, current construct name, and hand tracking state.  
  - Gestures:
    - Hand movement: rotates the particle construct based on normalized hand position.  
    - Pinch (thumb–index distance): controls expansion/intensity and triggers color shifts.  
    - Fist: cycles through the available shapes with cooldown logic.  

- **Mission Logs (`mission.html`)**  
  - In-universe “CLASSIFIED MISSION LOGS” page with subject ID, objective, and system warning.  
  - Technology stack listed diegetically as part of the mission briefing.  

- **Styling (`style.css`)**  
  - Global CRT scanline overlay using `body::before` and RGB stripe gradients.  
  - Retro terminal typography via the VT323 font from Google Fonts.  
  - Glitch animation keyframes, blinking status indicators, and hacker-style buttons (`.btn-hack`).  
  - Reusable `.panel`, `.redacted`, `.blink`, and HUD-specific layout (`#hud-overlay`, `#canvas-container`).  

## File Structure

```text
.
├── index.html        # SYSTEM BOOT / mainframe landing page
├── experiment.html   # Gesture-controlled 3D particle experiment
├── mission.html      # In-universe mission logs / lore page
└── style.css         # Shared CRT / glitch / HUD styling
