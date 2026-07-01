# Platform & Technical Considerations — Safety Code Violator

**Safety Code Violator GDD**
*Platform targets, technical requirements, performance goals, save system, and modding considerations. Reference when making technical decisions.*

---

## Target Platforms

| Platform | Priority | Session Length | Control Scheme | Notes |
|----------|----------|---------------|----------------|-------|
| Steam (Windows) | Primary | 15–45 minutes | Mouse + Keyboard | Native build |
| Steam (Linux) | Primary | 15–45 minutes | Mouse + Keyboard | Native build |
| Android | Primary | 15–30 minutes | Touch-first | Google Play |
| Steam Deck | Secondary | 15–30 minutes | Gamepad + trackpad-as-mouse | Runs Linux build natively |
| Controller (PC) | Secondary | Same as Steam | Gamepad | Deferred — to confirm once UI design is finalized |

Steam (Windows/Linux) and Android are treated as primary targets. Neither is an afterthought. Steam Deck is a confirmed secondary target — it runs the Linux build natively at no extra cost and suits the game's session length and play style well.

---

## Engine

**Godot 4.7** (current stable release)

Godot is the confirmed engine for all platforms. Key reasons:
- Single codebase exports to Windows, Linux, and Android natively
- Strong 2D physics (RigidBody2D for ragdolls, Area2D for triggers)
- Godot Audio Bus system supports adaptive music implementation
- Active development and good mobile performance on mid-range devices
- Free and open source — appropriate for solo development

---

## Platform-Specific Design

### Android (Mobile)

**UI Requirements:**
- Touch-friendly UI with large buttons and clear hit areas
- Minimum touch target size: 44x44dp across all interactive elements
- No interactive elements in bottom 15% of screen (thumb rest zone)
- One-handed play possible for key functions — important for commuting/transit use
- Pinch-to-zoom and drag-to-pan camera controls
- Large, readable text at all zoom levels

**Session Design:**
- Sessions completable in 15–30 minutes — one shift per sitting
- Auto-save every few minutes + quick resume on app close/reopen
- No penalty for interrupted sessions — Working Day Timer pauses on app background

**Performance:**
- Target: 60 FPS on mid-range Android phones during normal simulation
- Particle density scales with device performance tier
- Worker AI optimization — not every worker simulates every frame at full detail
- Texture atlases for all sprite sheets
- Compressed audio assets (OGG Vorbis for music, WAV for short SFX)
- Lower simultaneous audio channel count than PC
- LOD (Level of Detail) for distant workers — simplified sprites at zoom-out

**Distribution:**
- Google Play Store
- Free version: Construction Site only, full progression active, stars carry over on upgrade
- Paid version: All 40+ workplaces

### Steam (PC)

**UI Requirements:**
- Full mouse precision for placing small hazards and reading detailed tooltips
- Keyboard shortcuts for speed controls and common setup actions
- Higher resolution UI with more detailed information displays
- Scalable UI for different monitor resolutions and aspect ratios

**Session Design:**
- Longer sessions supported — players may run multiple shifts per sitting
- No session length pressure — players can take their time in setup phase
- Mouse wheel zoom + click-drag pan

**Performance:**
- Target: 120+ FPS on mid-range PC during normal simulation
- Higher particle density than Android
- Full audio channel count
- Higher resolution textures where appropriate

**Distribution:**
- Steam store (Windows + Linux native builds)
- Demo version: Construction Site only
- Full version: All 40+ workplaces
- Steam Workshop: See Modding section below

---

### Steam Deck

Runs the Linux build natively — no Proton required, no separate build needed.

**Input:**
- Gamepad buttons and analog sticks for navigation and simulation controls
- Right trackpad emulates mouse for hazard placement during Setup Phase (no touchscreen on Deck)
- Full native gamepad support unlocks automatically once PC controller support is implemented

**Session Design:**
- 15–30 minute shift length suits handheld play well
- No always-online requirement — plays fully offline
- Steam Cloud save sync keeps progress in line with PC sessions

**Performance:**
- Steam Deck hardware significantly exceeds mid-range Android targets — performance should be excellent on the Linux build with no Deck-specific optimization required

**Distribution:**
- Ships as part of the Steam (Linux) release — no separate SKU
- Target Valve's Steam Deck Verified or Playable certification (requires controller support and UI readability pass — see TODO)

**Pending (see TODO — Tier 4):**
- UI text readability verification at 800p on 7-inch screen
- Hazard placement feel testing with analog stick + trackpad input
- Steam Deck certification submission

---

## Camera System

**Type:** Isometric top-down
**Behavior:**
- Free pan — click-drag on PC, drag on Android
- Smooth zoom — mouse wheel on PC, pinch on Android
- Overview zoom (full map visible) → close-up zoom (individual worker detail)
- Auto-camera focus on major chain reactions — optional toggle in settings
- Manual focus — double-click/tap worker or hazard to center camera
- Slow-motion camera emphasis during highlight moments

**Isometric implementation notes:**
- All tile-based map elements constructed on isometric grid in Godot
- Consistent depth sorting for overlapping elements
- Vertical elements (scaffolding, shelving, cranes) use consistent depth cues
- Shadow casting consistent across all environmental elements

---

## Input System

**Separate input handling layers for touch vs mouse/keyboard:**

| Action | PC | Android |
|--------|-----|---------|
| Place hazard | Click drag | Tap and drag |
| Pan camera | Click drag (empty space) | Drag (empty space) |
| Zoom | Mouse wheel | Pinch |
| Focus on worker/hazard | Double-click | Double-tap |
| Speed controls | Keyboard shortcuts + buttons | On-screen buttons |
| Pause | Spacebar + button | On-screen button |
| Open loadout | Tab + button | On-screen button |
| Rotate hazard | R key + button | On-screen button |
| Undo | Ctrl+Z | On-screen button |

---

## Physics

**Godot 2D Physics:**
- RigidBody2D for ragdoll workers and falling objects
- Area2D for hazard trigger zones and detection areas
- Cartoon-style physics parameters — exaggerated bounce, spin, and velocity
- Chain reaction detection system — tracks when one physics event triggers another
- Animal hazards use navigation mesh AI rather than pure physics

---

## Save System

**PC (Steam):**
- Cloud saves via Steam — progression syncs across devices
- Local save backup in case of cloud failure
- Save points: after every debrief, after every milestone completion
- Persistent trap state saved per workplace

**Android:**
- Local saves on device
- Auto-save every 2–3 minutes during simulation
- Quick-save on app background/close
- Save points: same as PC plus auto-save intervals

**What is saved:**
- Cumulative star total
- All four progression track states
- Milestone completion per workplace
- Persistent trap state per workplace (unresolved traps and their PD accumulation)
- Cosmetic unlock states
- Settings and preferences

---

## Performance Goals Summary

| Metric | Android Target | PC Target |
|--------|---------------|-----------|
| Frame rate (normal simulation) | 60 FPS | 120+ FPS |
| Frame rate (peak chaos, many particles) | 30 FPS minimum | 60 FPS minimum |
| Load time per workplace | Under 3 seconds | Under 2 seconds |
| Worker AI update rate | Every 2–3 frames on low-end | Every frame |
| Maximum simultaneous workers | 20+ on mid-range Android | 50+ on PC |

---

## Modding (Steam Only)

Steam Workshop support is planned for the full PC version. Android mod support is limited to resource packs only due to platform restrictions.

**Planned Steam Workshop support:**
- Custom workplace maps
- Custom hazard packs (new hazard types with custom assets and behavior)
- Custom worker personality packs (new archetypes)
- Custom cosmetic packs (sound packs, visual styles)
- Resource packs (reskins of existing content)

**Modding scope note:** Modding support is a post-launch addition. Core game ships without Workshop integration. Design all systems with moddable architecture in mind (data-driven hazard definitions, scriptable archetype behaviors) but do not delay launch for modding support.

---

## Godot Architecture Notes

*High level — detailed architecture in Technical/Godot_Architecture.md*

**Key architectural decisions:**
- Hazard system is data-driven — hazard properties defined in resources, not hardcoded
- Worker archetypes implemented as behavior scripts attached to base worker node
- PD meter is a global autoload singleton accessible by all systems
- Audio uses Godot Audio Bus system with parameter-driven adaptive music
- UI uses Container nodes with proper anchors for scalable layouts
- Separate input handler autoload detects touch vs mouse/keyboard and routes accordingly
- Scene structure: one scene per workplace, hazard and worker instances spawned at runtime

---

## Open Technical Questions

*Items not yet confirmed — to be decided during implementation*

| Question | Context |
|----------|---------|
| Controller support on PC? | Mentioned in early drafts. Useful for couch play. Not confirmed |
| Godot version (4.3 vs latest stable)? | Use latest stable Godot 4.x at time of development start |
| Multiplayer / co-op? | Not planned but architecture shouldn't preclude it |
| iOS support? | Not in current plan. Could be added post-launch if Android succeeds |
| Cloud saves on Android (Google Play Games)? | **Confirmed** — Google Play Games cloud sync. See `Save_System.md` |

---

## Conflicts Resolved From Prior Drafts (Grok)

| Element | Resolution |
|---------|-----------|
| 2.5D angled view camera | Replaced — confirmed isometric top-down |
| iOS listed as platform | Removed from current plan — Android only for mobile |
| "Violator Hub" requiring its own scene | Not confirmed — flagged as open design question |
| Contract briefing screen as separate phase | Removed — no contract system |

---

*This is the canonical platform and technical reference. Cross-reference Technical/Godot_Architecture.md and Technical/Save_System.md for implementation details.*
