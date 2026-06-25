## 3. Core Mechanics (in 2.5D Angled View)

### Placement & Setup Phase
- **Drag & Drop** with real-time visual preview (ghosted object shows exact position and rotation).
- **Snap-to-Grid** option (toggleable) + free placement for certain items.
- **Rotation** support for directional hazards (ladders, shelves, conveyor belts, etc.).
- **Validity Feedback**: Green = safe/valid, Yellow = high suspicion risk, Red = invalid/obstructed.
- **Undo/Redo** stack (very important for creative iteration).
- **Budget Counter** always visible with live cost preview.

**Feel**: Calm, creative, and empowering — like digital LEGO with evil intent.

### Simulation Phase
- **Real-time physics** using Godot 2D (RigidBody2D for ragdolls, Area2D for triggers).
- **Time Controls**: 1x / 4x / 16x / 64x + Pause. Smooth transitions.
- **Camera Interaction**:
  - Click-drag to pan
  - Mouse wheel / pinch to zoom
  - Double-click or hotkey to focus on a worker or hazard
  - Auto-camera focus on major chain reactions (optional toggle)
- **Mid-simulation Interventions**:
  - Quick-drop hazards from a favorites bar
  - "Emergency Repair" actions (lowers suspicion but costs budget)
  - Distract workers (e.g. fake phone call, spilled coffee)

**Feel**: Tense anticipation mixed with bursts of chaotic joy.

### Key Systems & How They Feel

**Plausible Deniability Meter**
- Always visible in top-right, color-coded (Green → Yellow → Orange → Red).
- Live feedback when placing hazards or as events unfold.
- Tension mechanic: You are constantly balancing “this is funny” vs “this is too obvious”.

**Worker Personalities**
- Each worker has visible (or discoverable) traits.
- You learn their routines and quirks over time.
- Targeting specific workers for ironic deaths feels extremely satisfying.

**Combo & Chain Reaction System**
- The game automatically detects and scores combos.
- Visual + audio rewards when a good chain starts (screen shake, dramatic sound, particles).
- In 2.5D, vertical and multi-object interactions look especially good (falling shelves, cascading conveyor failures, etc.).

**Highlight Reel System**
- Automatically records the best moments.
- At end of shift you get an editable/playable montage with slow-motion, zooms, and funny captions.

### Progression of Mechanical Depth
- **Early Game**: Simple placement + basic combos.
- **Mid Game**: Timing, worker targeting, and multi-stage setups.
- **Late Game**: Complex trigger systems, vertical chaos, and extreme plausibility management.

### Failure & Replayability
- Failing a contract (meter hits 100%) is funny and forgiving — you still get partial rewards and a comedic “you got caught” cutscene.
- Quick “Restart Shift” with same setup or full reset.
- High replay incentive through star ratings, achievements, and “perfect plausibility” challenges.

---

**Status**: This completes the high-level overview of how the core mechanics will feel with the 2.5D camera.

---

Now we have a solid creative anchor document with all three areas (Player Experience, Art Direction, and Core Mechanics) summarized in one place.
