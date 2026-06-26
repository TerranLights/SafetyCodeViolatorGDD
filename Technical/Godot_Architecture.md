# Godot_Architecture

## Engine Version
**Godot 4.3+ (stable)** — Excellent 2D performance, strong mobile support, and great GDExtension/C++ options if needed.

## Overall Architecture

### Scene Structure
- **Main Menu / Workplace Select** (`MainMenu.tscn`) — Workplace selection screen, progression display, unlocks. *Note: whether a dedicated "Violator Hub" exists as a between-shifts space is an open design question — see `Core_Design.md`. At minimum this scene covers the workplace select screen.*
- **Level Template** (`LevelTemplate.tscn`) — Reusable base for every workplace
- **Worker Scene** (`Worker.tscn`) — Instanced + customized via scripts
- **Hazard System** (`HazardManager.tscn` + `Hazard.tscn`)

### Core Systems (Autoload Singletons)
- `GameManager.gd` — Global state, save/load, progression
- `ShiftManager.gd` — Three-phase shift lifecycle (briefing → setup → simulation → debrief), shift end state detection, persistent trap handoff between shifts
- `HazardSystem.gd` — Placement, combo detection, simulation
- `WorkerManager.gd` — Spawning, AI, personalities, routines — includes Manager/Foreman and Safety Inspector as special-case behaviors
- `PlausibilityManager.gd` — Meter logic, suspicion calculation, persistent trap PD accumulation on shift start
- `SimulationController.gd` — Time scaling, pause, Working Day Timer
- `HighlightReel.gd` — Recording and playback of notable moments for debrief
- `ScoreCalculator.gd` — Scoring axes, star rating calculation, debrief data assembly

## Key Technical Decisions

### Physics
- Godot 2D Physics (RigidBody2D + Area2D)
- Custom collision layers for workers, hazards, environment
- Ragdoll system for deaths (Skeleton2D or simple pin joints)

### Performance (Especially Android)
- Object pooling for particles, debris, and minor effects
- Worker LOD (reduce AI ticks when far from camera or during high speed)
- Smart update rates based on time multiplier
- Target: 60 FPS on mid-range Android devices

### Save System
- JSON-based local saves (easy for Android)
- Steam Cloud support on PC
- Quick-save during simulation

### Modding Readiness
- Data-driven hazards (JSON or `.tres` resource files)
- Worker personality definitions in external files
- Scene instancing system that easily accepts modded content

## Input Handling
- Separate `InputHandler.gd` with Touch vs Mouse/Keyboard modes
- Context-sensitive controls (Setup vs Simulation phase)

---

## Conflicts Resolved From Prior Draft

| Element | Resolution |
|---------|-----------|
| `ViolatorHub.tscn` — "Menu, contract board, unlocks" | Renamed to `MainMenu.tscn`. "Contract board" removed — no contract system. Violator Hub as a concept is an open design question; see `Core_Design.md` |
| `resources/contracts/` in folder structure | Renamed to `resources/workplaces/` — consistent with save system structure and confirmed design |
| No shift lifecycle singleton | Added `ShiftManager.gd` to cover the three-phase shift structure, end state detection, and persistent trap handoff |
| Singletons underdescribed | Expanded all singleton descriptions to reflect confirmed system responsibilities |

## Folder Structure (inside project)

SafetyCodeViolator/
├── scenes/
├── scripts/
│   ├── core/           ← Singletons & managers
│   ├── hazards/
│   ├── workers/
│   └── ui/
├── resources/
│   ├── hazards/
│   ├── workers/
│   └── workplaces/
├── audio/
└── assets/


