# Time Simulation System — Safety Code Violator

**Safety Code Violator GDD**
*Defines how real-time simulation works, speed controls, pacing, and the Working Day Timer.*

---

## Overview

The simulation runs in **real-time** with full player-controlled speed controls. Players can watch detailed chain reactions at normal speed, fast-forward through quiet periods, or pause to observe. The system is designed so players never feel like they're wasting time watching nothing happen, while also ensuring big moments feel cinematic and rewarding.

Session target: **15–30 minutes** per shift, fully achievable on Android in one sitting.

---

## Speed Controls

| Speed | Multiplier | Primary Use Case | Android Friendly? |
|-------|------------|-----------------|-------------------|
| Pause | 0x | Observing current state, reviewing map | Yes |
| 1x | Normal | Watching detailed chain reactions unfold | Yes |
| 4x | Fast | Default during quieter periods | Yes |
| 16x | Very Fast | Skipping slow build-up between incidents | Yes |
| 64x | Extreme | Burning through remaining shift time quickly | Yes |

**Speed control is entirely player-driven.** The player chooses when to speed up or slow down based on what's happening on screen. No automatic speed changes are made by the game without player input.

**Audio interaction with speed controls:**
- At 1x: All audio plays normally
- At 4x–16x: Subtle pitch elevation, still intelligible
- At 64x: Deliberate chipmunk effect — played for comedy, not realism
- At Pause: All gameplay audio fades to near-silence within 0.5 seconds

Full audio details: Sound_and_Music_Direction.md

---

## Working Day Timer

Every simulation represents one full in-game working day. The Working Day Timer is the primary mechanism that prevents softlocks from unactivated traps.

**How it works:**
- Timer is visible to the player throughout simulation
- Counts down from start of simulation to end of working day
- When timer reaches zero, shift ends automatically — debrief fires with whatever was earned
- Any unresolved traps at timer expiry become Persistent Traps carried into next shift
- Speed controls affect how quickly real time passes relative to the timer

**Timer interaction with speed controls:**
- At 1x: approximately 8–10 real minutes per full shift
- At 4x: approximately 2–3 real minutes per full shift
- At 64x: shift resolves in under a minute

**Softlock prevention:** The Working Day Timer ensures every shift ends regardless of trap state. A trap placed in a corner nobody ever walks into will simply not trigger this shift — it becomes a Persistent Trap with PD accumulation consequences for next shift.

Full Persistent Trap details: Shift_and_Level_Structure.md

---

## Simulation Architecture

**Physics engine:** Godot 2D (RigidBody2D for ragdolls and falling objects, Area2D for trigger zones)

**Event triggers:**
- **Time-based:** Some events trigger at specific points in the working day (union break, delivery arrival, manager walkthrough)
- **Worker interaction:** Worker enters trap zone, interacts with sabotaged equipment, or responds to another worker
- **Chain reaction:** One physics event directly triggers another

**Worker behavior during simulation:**
- Workers follow daily routines with natural variation per archetype
- Routines are interrupted by nearby incidents, triggering hazard reaction behavior
- Manager conducts periodic walkthroughs on semi-fixed routes
- Inspector (if spawned) patrols and responds to incidents

Full worker behavior details: Worker_Archetypes.md

---

## Cinematic Moments

The simulation automatically identifies and emphasizes spectacular moments:

- **Auto-camera focus** on major chain reactions — optional toggle in settings
- **Dramatic slow-motion** during highlight moments
- **Screen shake and bloom** on large impacts and explosions
- **Highlight recording** — game captures notable moments for debrief reel throughout simulation

These systems run automatically but all camera emphasis features can be disabled in settings for players who prefer full manual camera control.

---

## Pacing Design Goals

- **Never feel like wasted time** — fast-forward exists specifically for quiet periods
- **Peak chaos feels cinematic** — slow-motion and camera focus reward big moments
- **Player controls pacing entirely** — no automatic speed changes without player input
- **Big satisfying moments** — at least one "I can't believe that worked" moment per shift
- **Android-friendly** — a full shift at 4x-16x speed fits comfortably in a 15-minute commute

---

## Future Considerations

*The following ideas were proposed during early design and are not confirmed for v1. Captured here for future reference.*

**While-You-Were-Away (Idle) Mode:**
When the app is closed or minimized on Android, a lightweight simulation could continue in the background. On return, the player receives a "While You Were Out" highlight reel of major events that occurred. Only major events simulated — no full physics tick. This would reward longer-term setups and support casual Android play patterns. Implementation cost is non-trivial for a solo dev — post-launch consideration.

**Shift Period Structure:**
The working day could be internally divided into named periods that affect worker density and behavior:
- Morning Rush (first 30%) — workers arriving, setup payoff begins
- Mid-day Peak (middle 40%) — highest worker density, maximum chaos potential  
- Afternoon Wind-down (final 30%) — fewer workers active, final combos resolve

This structure could make shifts feel more varied without requiring different maps. To be evaluated during implementation.

**Smart Pacing Assist:**
A system that subtly suggests speed increases when nothing significant has happened for a set period — purely as a player notification, not an automatic change. Could help newer players who don't think to use fast-forward. To be evaluated during playtesting.

---

## Conflicts Resolved From Prior Draft (Grok)

| Element | Resolution |
|---------|-----------|
| Pause described as "planning interventions" | Revised — no mid-simulation intervention confirmed. Pause is for observation |
| While-You-Were-Away idle mode as confirmed feature | Moved to Future Considerations — not confirmed for v1 |
| Auto-speed-increase system | Moved to Future Considerations — conflicts with player-driven pacing philosophy |
| Morning/Mid-day/Afternoon shift structure | Moved to Future Considerations — interesting idea, not confirmed |

---

*This document covers the time simulation system. Cross-reference Shift_and_Level_Structure.md for shift end states and Persistent Trap behavior, and Sound_and_Music_Direction.md for speed control audio behavior.*
