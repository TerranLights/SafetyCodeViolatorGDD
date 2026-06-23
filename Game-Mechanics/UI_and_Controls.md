# UI_and_Controls
This file defines how the game will actually *feel* to play on both platforms.

## Design Philosophy
- Clean, corporate-looking UI that contrasts with the chaos
- Highly readable even during fast-forward and big explosions
- Mobile-first (Android) design with large touch targets
- PC version gets extra precision and shortcuts

## Core Screens

### 1. Hub / Violator Office
- Contract board
- Stats dashboard (career rank, total victims, reputation)
- Unlock shop
- Highlight reel archive

### 2. Briefing Screen
- Contract details, objectives, budget
- Location preview image
- "Accept Contract" button

### 3. Setup Phase UI
- Hazard palette (categorized tabs)
- Budget counter (top right)
- Plausibility preview meter
- Drag & drop placement with snap-to-grid option
- Undo / Redo system

### 4. Simulation Phase UI
- **Top Bar**:
  - Plausible Deniability Meter (prominent, color-coded)
  - Time control (1x / 4x / 16x / 64x + Pause)
  - Current shift timer
- **Bottom Bar**:
  - Quick hazard drop buttons (favorites)
  - Intervention tools
- **Mini-map / Floor Overview** (toggleable)

### 5. Debrief Screen
- Big score breakdown
- Highlight reel (playable video clips)
- Top 5 funniest moments with worker names
- Unlock notifications
- "Next Shift" / "Replay" buttons

## Control Schemes

### Android (Touch)
- Tap to select hazard → Tap to place
- Drag to move/rotate objects
- Pinch to zoom / drag to pan camera
- Swipe up on meter for detailed suspicion breakdown
- Speed control via large on-screen buttons

### PC (Mouse + Keyboard)
- Click + drag placement
- Mouse wheel zoom
- Keyboard shortcuts:
  - Space = Pause/Play
  - 1–4 = Speed presets
  - Ctrl+Z = Undo
  - F = Focus on last major accident

## Accessibility
- Color-blind modes for the deniability meter
- Scalable UI
- Optional reduced visual clutter during high chaos
- Screen reader friendly text for contracts and objectives
