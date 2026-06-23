# Godot_Architecture

## Engine Version
**Godot 4.3+ (stable)** — Excellent 2D performance, strong mobile support, and great GDExtension/C++ options if needed.

## Overall Architecture

### Scene Structure
- **Main Hub Scene** (`ViolatorHub.tscn`) — Menu, contract board, unlocks
- **Level Template** (`LevelTemplate.tscn`) — Reusable base for every workplace
- **Worker Scene** (`Worker.tscn`) — Instanced + customized via scripts
- **Hazard System** (`HazardManager.tscn` + `Hazard.tscn`)

### Core Systems (Autoload Singletons)
- `GameManager.gd` — Global state, save/load, progression
- `HazardSystem.gd` — Placement, combo detection, simulation
- `WorkerManager.gd` — Spawning, AI, personalities, routines
- `PlausibilityManager.gd` — Meter logic, suspicion calculation
- `SimulationController.gd` — Time scaling, pause, idle mode
- `HighlightReel.gd` — Recording and playback of funny moments
- `ScoreCalculator.gd`

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
│   └── contracts/
├── audio/
└── assets/


