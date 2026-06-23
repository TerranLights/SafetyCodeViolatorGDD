# Android_Considerations
This ensures the game feels excellent on phones and tablets while still shining on PC.

## Design Priorities for Android
Since Android is a primary target platform, mobile constraints and touch-first playstyle are considered from the beginning.

## Performance Targets
- **60 FPS** on mid-range devices (Snapdragon 7xx / equivalent)
- **Stable 30–45 FPS** on low-end devices during peak chaos
- Aggressive object pooling and LOD for workers/particles
- Lower physics tick rate at high time speeds (16x+)

## Touch Controls Optimizations
- Large, finger-friendly buttons
- Drag-to-place with visual preview
- Pinch-to-zoom camera
- One-handed friendly layout (important controls on bottom half of screen)
- Quick-tap favorites bar for common hazards

## UI Scaling & Readability
- Dynamic UI scaling based on screen size/resolution
- Minimum touch target size: 48dp
- High-contrast text and icons
- Simplified HUD during high-speed simulation

## Battery & Heat Management
- Reduced particle count and effects at very high speeds
- Optional "Battery Saver" mode (lower simulation fidelity)
- Pause simulation automatically when app loses focus (with background idle calc)

## Technical Setup
- Godot Android export with **ARM64** + **ARM32** support
- Optimized assets (texture compression: ASTC / ETC2)
- Separate export preset with mobile-specific performance settings
- Permissions: Only storage (for saves/mods) — no unnecessary permissions

## Session-Friendly Features
- Auto-save every 30 seconds + on phase change
- Quick resume from last shift
- Background "While You Were Out" simulation summary
- Compact highlight reels (shorter videos for mobile)

## Testing Strategy
- Test on real devices (not just emulators) at various performance tiers
- Focus testing on:
  - Long sessions (30+ minutes)
  - Peak chaos moments
  - Touch precision during fast time speeds
