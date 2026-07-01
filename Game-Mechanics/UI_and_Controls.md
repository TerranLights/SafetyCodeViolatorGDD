# UI & Controls — Safety Code Violator

**Safety Code Violator GDD**
*Defines all core screens, HUD elements, and control schemes for both platforms. Cross-reference Art_Bible.md for visual style and Platform_and_Technical.md for input implementation details.*

---

## Design Philosophy

- Clean, corporate-looking UI that contrasts with the chaos on screen
- Highly readable even during fast-forward and simultaneous incidents
- Mobile-first (Android) design with large touch targets — minimum 44x44dp
- PC version gets extra precision, tooltips, and keyboard shortcuts
- Minimal clutter during simulation — the chaos is the main event, not the UI

---

## Core Screens

### 1. Main Menu / Workplace Select

The primary between-shifts screen. Player returns here after every debrief. No hub space — no player character sprite.

**Persistent top bar (always visible):**
- Cumulative star total — drives all four progression tracks
- Progression track display — current loadout size, placement budget, per-type limit, hazard pool status
- Access to cosmetics and highlight reel archive

**Category view (top level):**
- Workplace categories listed (Office, Construction Site, Theme Park, etc.)
- Per-category indicator — how many configurations visited, completed, mastered
- All categories available from the start in the full version

**Configuration sub-menu (on selecting a category):**
- All configurations within that category listed with individual status — Visited / Completed / In Progress / Mastered
- Best star rating and milestone progress per configuration
- Select a configuration to proceed to Shift Briefing

---

### 2. Shift Briefing

Shown when the player selects a workplace and before setup begins. No time limit.

- **Workplace overview** — environment name, map preview image, zone summary
- **Persistent trap state** — any unresolved traps from previous shifts are shown on the map with their accumulated PD values
- **Starting PD meter value** — shown clearly before setup begins so the player knows what they're working with
- **Loadout selection** — player picks from available hazard pool up to current loadout size limit. Per-type limits shown per hazard
- **Worker roster preview** — archetypes active this shift, crew size
- **Active level variant conditions** — time of day, weather, crew composition, or special conditions if active
- **"Begin Setup" button** — confirms loadout and moves to setup phase

---

### 3. Setup Phase UI

Workers are frozen. Player places hazards. No time limit.

- **Hazard palette** — categorized tabs showing available loadout selections
- **Budget counter** — total placements remaining, always visible
- **Per-type counter** — instances remaining for each selected hazard type
- **Snap-to-grid toggle** — on by default, togglable for free placement
- **Placement preview** — ghosted real-time preview showing exact position and validity:
  - Green = valid placement
  - Yellow = valid but high suspicion risk
  - Red = invalid or obstructed
- **Undo / Redo** — full stack for setup phase placement iteration
- **Persistent trap overlay** — previously placed unresolved traps visible on map but not repositionable
- **"Begin Simulation" button** — locks placement and starts the working day

---

### 4. Simulation Phase UI

Workers unfreeze and the shift plays out. **No hazard placement or intervention during simulation** — the player observes only.

**Top Bar:**
- Plausible Deniability Meter — prominent, color-coded Green → Yellow → Orange → Red
- Working Day Timer — counts down from shift start to end of working day
- Speed controls — Pause / 1x / 4x / 16x / 64x

**Overlays (toggleable):**
- Mini-map / Floor Overview — bird's-eye map of full workplace with incident markers
- Auto-camera toggle — enables/disables automatic camera focus on chain reactions

**Manual shift end:**
- Player can end the shift early at any time via a clearly accessible menu option — triggers debrief immediately with stars earned to that point

---

### 5. Debrief Screen

Fires after any valid shift end state. Full corporate deadpan presentation.

- **Star rating** (1–5) with breakdown of which requirements were and weren't met
- **Top 5 moments** from the simulation — highlighted incidents for review and replay
- **"Most Valuable Victim" award** — worker archetype that contributed most to the chaos score
- **"Best Combo" breakdown** — highest-scoring chain reaction of the shift, step by step
- **Total Insurance Money "Saved"** — presented as a positive corporate metric
- **Scoring axes display** — all ten axes shown with performance indicators
- **Viral Impact rating** — how shareable this shift was
- **Milestones completed this shift** — newly completed milestones highlighted
- **Persistent trap warning** — if unresolved traps remain, their accumulated PD impact for next shift is displayed clearly
- **Replay / Continue prompt** — replay this shift, **restart with same setup** (same trap layout pre-loaded, plays as a normal shift), try a different workplace, or return to Main Menu

---

## Control Schemes

### Android (Touch)

- Tap to select hazard from palette → tap or drag to place
- Drag to move/rotate placed hazard during setup
- Pinch to zoom / drag to pan camera
- Swipe up on PD meter for detailed suspicion breakdown
- Speed controls via large on-screen buttons — thumb-reachable zone
- All interactive elements minimum 44x44dp

### PC (Mouse + Keyboard)

- Click hazard in palette → click or drag to place
- Mouse wheel zoom / middle-click drag to pan camera
- Right-click to cancel placement or deselect
- Keyboard shortcuts:
  - `Space` — Pause / Resume
  - `1` / `2` / `3` / `4` — Speed presets (1x / 4x / 16x / 64x)
  - `Ctrl+Z` / `Ctrl+Y` — Undo / Redo (setup phase only)
  - `R` — Rotate hazard during placement
  - `Tab` — Open/close hazard palette
  - `F` — Focus camera on last major incident
  - `M` — Toggle mini-map overlay
  - `Escape` — Open shift menu (manual end shift / settings)

---

## Accessibility

- Color-blind modes for the Plausible Deniability Meter — shape and pattern indicators supplement color coding
- Scalable UI across all screen sizes and resolutions
- Optional reduced visual clutter mode during high chaos — simplifies particle density without removing gameplay information
- High-contrast text and icon options
- Screen reader support for all menu text, progression displays, and debrief information

---

## Conflicts Resolved From Prior Draft

| Element | Resolution |
|---------|-----------|
| "Hub / Violator Office" with contract board | Removed — no contract system, no hub space, no player sprite. Replaced with category-based workplace select (category → configuration sub-menu) |
| Career rank in stats dashboard | Removed — no rank system. Cumulative stars and progression tracks shown instead |
| "Total victims" in career stats | Replaced with "total incidents" — consistent with confirmed corporate deadpan framing and Save_System.md |
| Reputation in stats dashboard | Removed — no reputation system |
| Briefing screen showing contract details and objectives | Replaced — briefing now shows persistent trap state, starting PD, loadout selection, worker roster, variant conditions |
| "Accept Contract" button | Replaced with "Begin Setup" button |
| Simulation Phase bottom bar with hazard drop buttons and intervention tools | **Removed entirely** — no mid-simulation placement or intervention confirmed. Setup phase only. Simulation UI is observation-only |
| "Screen reader friendly text for contracts and objectives" | Updated — contracts and objectives removed from accessibility notes |
