# Time_Simulation
This system directly solves the earlier concern about boredom vs missing the fun.

## Overview
The simulation runs in **real-time** with multiple speed controls so players can enjoy the chaos at their preferred pace while still supporting 15–30 minute sessions.

## Time Controls

| Speed   | Multiplier | Use Case                              | Android Friendly? |
|---------|------------|---------------------------------------|-------------------|
| 1x      | Normal     | Watching detailed chain reactions     | Yes               |
| 4x      | Fast       | Default during quiet periods          | Yes               |
| 16x     | Very Fast  | Skipping slow build-up                | Yes               |
| 64x     | Extreme    | Quick testing or idle-like play       | Yes               |
| Pause   | 0x         | Planning interventions                | Yes               |

## Simulation Architecture

- **Continuous real-time physics** (Godot 2D physics)
- Workers follow daily routines with natural variation
- Events are triggered by time, worker interaction, or chain reactions
- Smart pacing system:
  - Automatically increases speed slightly if nothing interesting has happened for ~45 seconds
  - Slows down or triggers dramatic camera focus during major accidents

## Session Time Structure (One Shift)

- **Morning Rush** (first 30% of shift) – Setup payoff begins
- **Mid-day Peak** (middle 40%) – Highest chaos potential
- **Afternoon Wind-down** (final 30%) – Final combos and cleanup

## While-You-Were-Away (Idle) Mode

- When the game is closed/minimized, a **lightweight simulation** continues in the background
- On return, player gets a **“While You Were Out”** highlight reel
- Only major events are simulated (no full physics tick)
- Prevents boredom while still rewarding longer-term setups

## Design Goals
- Never feel like you’re wasting time watching nothing happen
- Give players full control over pacing
- Make big satisfying moments feel cinematic and rewarding
- Support both active “I want to see everything” play and more casual check-in play on Android
