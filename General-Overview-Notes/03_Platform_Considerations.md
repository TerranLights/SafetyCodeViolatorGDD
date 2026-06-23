# 03_Platform_Considerations

## Target Platforms

| Platform       | Priority | Session Length | Control Scheme              | Notes |
|----------------|----------|----------------|-----------------------------|-------|
| **Android**    | High     | 15–30 minutes  | Touch-first                 | Primary mobile platform |
| **Steam**      | High     | 15–45 minutes  | Mouse + Keyboard            | Windows + Linux Native |
| **Linux**      | Medium   | Same as Steam  | Mouse + Keyboard            | Native builds |

## Platform-Specific Design Decisions

### Android (Mobile-First)
- Touch-friendly UI with large buttons and clear hit areas
- One-handed play possible (important for commuting/lying in bed)
- Auto-save every few minutes + quick resume
- Simplified camera controls (pinch to zoom, drag to pan)
- Performance-friendly: clear visual feedback even on mid-range phones
- Session-based design so players can finish a full shift in one sitting

### Steam (PC)
- Full mouse precision for placing small hazards
- Keyboard shortcuts for speed control and common actions
- Higher resolution UI and more detailed tooltips
- Controller support planned (for couch chaos)
- Better support for long sessions and multiple shifts

## Technical Considerations

**Godot Engine**
- Using Godot 4.3+ for best mobile + desktop performance
- 2D physics (Godot’s built-in) for chain reactions
- Separate input handling layers for touch vs mouse/keyboard
- Scalable UI (Container nodes + proper anchors)

**Performance Goals**
- 60 FPS on mid-range Android phones during normal simulation
- 120+ FPS on PC
- Efficient worker AI (not every worker simulates every frame)

**Save System**
- Cloud saves via Steam
- Local saves on Android
- Quick-save during simulation

**Modding Potential**
- Steam Workshop support for custom levels, hazards, and worker personalities
- Android mod support will be limited (resource packs only)
