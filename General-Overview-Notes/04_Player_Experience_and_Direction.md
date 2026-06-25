# 04_Player_Experience_and_Direction

## Camera Style (Locked Decision)
**2.5D Angled View** (approximately 35–40° tilt).

- Fixed angle with free **pan** and **smooth zoom** (from wide overview down to close-up details).
- Feels like a "god view" but with enough depth and height for satisfying physics and ragdolls.
- Supports pinch-to-zoom + drag on Android, mouse wheel + drag on PC.

---

## 1. Overall Player Experience

The game delivers a **satisfying loop of evil creativity → anticipation → spectacular payoff**.

### Session Flow (15–30 minutes)
- **Briefing (1–2 min)**: Read a shady corporate contract with funny objectives.
- **Setup Phase (5–8 min)**: Calm, creative sandbox. Place hazards, tweak the environment, plan combos. Feels like being an evil architect.
- **Simulation Phase (8–15 min)**: Watch your traps activate in real-time. Speed up time when you want, slow down or zoom in during big moments. Intervene with last-second drops or "repairs".
- **Debrief (2–3 min)**: Highlight reel of the funniest deaths, score breakdown, and unlock dopamine.

**Core Fantasy**: You are a brilliant, unhinged chaos engineer who keeps getting away with it. Every session should end with at least one “I can’t believe that worked” moment.

**Emotional Tone**: Mischievous glee during setup → rising tension → chaotic joy during big chain reactions → smug satisfaction in the debrief.

---

## 2. Art Direction (2.5D Tailored)

**Overall Style**: Bright, clean, cartoonish corporate aesthetic with strong contrast between "normal professional" and "total disaster".

- **Color Palette**: Professional blues/grays/teals at start → increasingly warm oranges, reds, and smoke as chaos builds.
- **Visual Contrast**: Clean, orderly environments at the beginning of a shift → messy, destroyed, smoky aftermath.
- **Character Style**: Exaggerated proportions (big heads, expressive faces) for readability and humor. Clear silhouettes even when zoomed out.
- **Animation Priority**:
  - Satisfying ragdoll physics on deaths (flailing, spinning, dramatic falls)
  - Expressive worker reactions (panic, confusion, ironic last words)
  - Dynamic destruction (falling shelves, sparks, spreading fire, collapsing scaffolding)
- **Lighting**: Dynamic — starts with clean office/factory lighting, then adds dramatic spotlights, fire glow, emergency lights during chaos.
- **Camera Feel**: Slight perspective depth so verticality (falling objects, multi-level scaffolding) looks dramatic and funny.

**Goal**: The violence should feel **cartoonish and hilarious**, never grim or realistic.

---

## 3. Core Mechanics Summary (in 2.5D View)

### Hazard Placement
- Drag & drop with visual preview and snap-to-grid option.
- Rotation support for certain objects (ladders, shelves, etc.).
- Clear feedback: green = valid, red = blocked, yellow = high suspicion.

### Simulation Interaction
- Real-time with 1x / 4x / 16x / 64x speed controls.
- Click on workers or hazards for detailed info.
- Mid-simulation “emergency intervention” drops (limited uses).

### Camera & Interaction
- Smooth zoom (overview for planning → close-up for watching specific comedy).
- Click-drag to pan.
- Focus camera button on major accidents (auto or manual).
- Highlight system automatically zooms/slows down on spectacular moments.

### Key Systems Reminder
- **Plausible Deniability Meter** (always visible, color-coded)
- **Worker Personalities** driving funny behaviors
- **Combo Detection** rewarding clever chains
- **Highlight Reel** auto-compilation at end of shift

---

**Status**: This document serves as the high-level creative anchor. Use it when returning to flesh out details in Art, Mechanics, or UI files.
