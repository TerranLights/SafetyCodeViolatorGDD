# Save System — Safety Code Violator

**Safety Code Violator GDD**
*Cross-platform save system for Steam (Windows/Linux) and Android. Designed to feel robust and polished across both platforms.*

---

## Overview

A robust cross-platform save system that works seamlessly on both Steam and Android. The save system must handle the game's persistent state correctly — particularly the Persistent Trap system where unresolved traps carry forward between shifts and accumulate PD passively.

**Primary goals:**
- Never lose player progress
- Resume instantly on Android after app close
- Sync seamlessly across PC sessions via Steam Cloud
- Support modding via readable JSON format

---

## Save Types

### 1. Player Profile Save
Permanent career-wide data. Written after every debrief and after every milestone completion.

**Contents:**
- Cumulative star total
- All four progression track states (Loadout Size, Placement Budget, Per-Type Limit, Hazard Pool)
- Milestone completion state per workplace (which milestones done, which remaining)
- Cosmetic unlock states
- Total career stats (total incidents, total shifts completed, total chain reactions, longest chain, best PD rating achieved)
- Settings and preferences

**File:** `saves/profile.json`

### 2. Workplace State Save
Per-workplace persistent data. Written after every debrief for that workplace.

**Contents:**
- Persistent trap state — which traps remain unresolved on the map
- Accumulated PD per persistent trap (for calculating starting PD next shift)
- Milestone Tree progress for this workplace
- Best star rating achieved in this workplace
- Total shifts completed in this workplace

**File:** `saves/workplaces/[workplace_id].json` (one file per workplace)

### 3. Active Shift Save
Current in-progress shift state. Written via auto-save during setup and simulation phases. Allows resuming an interrupted shift exactly where it left off.

**Contents:**
- Current workplace ID
- All placed hazards — positions, types, states (neutral/armed/triggered)
- Worker positions, current archetype states, and routine progress
- PD meter current value
- Working Day Timer current value
- Manager escalation ladder current stage
- Inspector spawn state and current position (if spawned)
- Current simulation speed setting
- Shift star progress (incidents caused, milestones triggered this shift)

**File:** `saves/active_shift.json` (single file, overwritten on each auto-save)

### 4. Highlight Reel Metadata
Replay data for debrief highlight moments. Stores event metadata rather than full video to keep file sizes manageable.

**Contents:**
- Timestamp of each notable moment during simulation
- Hazard types and worker archetypes involved
- Chain reaction step data for Best Combo reconstruction
- Camera position and zoom at time of event
- Star rating and scoring axis results for this shift

**File:** `saves/highlights/[workplace_id]_[timestamp].json`

---

## File Structure

```
saves/
├── profile.json                          ← Career-wide player data
├── active_shift.json                     ← Current in-progress shift
├── workplaces/
│   ├── construction_site.json            ← Persistent trap state + milestone progress
│   ├── office_building.json
│   └── [workplace_id].json              ← One per workplace visited
├── highlights/
│   ├── construction_site_20260101.json   ← Highlight reel metadata per shift
│   └── office_building_20260102.json
└── backups/
    ├── profile_backup_1.json             ← Last 3 successful profile saves
    ├── profile_backup_2.json
    └── profile_backup_3.json
```

---

## Technical Implementation

**Primary format:** JSON — human readable, easy to mod, easy to debug

**Godot implementation:**
- `FileAccess` + `JSON` class for all local saves
- `user://` directory for all platforms (Godot's cross-platform user data path)
- Separate save/load functions per save type for clean architecture
- JSON schema validation on load — detect and handle corruption gracefully

**Steam (PC):**
- Steam Cloud via Steam Remote Storage for profile.json and workplace saves
- Local saves as primary, Steam Cloud as sync layer
- Conflict resolution: most recent timestamp wins, with local taking priority if timestamps match

**Android:**
- Standard app data directory (`user://` in Godot)
- Compressed JSON where possible to reduce file sizes
- Automatic backup to device storage for corruption recovery
- Resume from active_shift.json on app reopen

---

## Auto-Save Behavior

| Phase | Auto-Save Frequency | What Gets Saved |
|-------|--------------------|-----------------| 
| Setup Phase | Every 60 seconds + on each hazard placement | active_shift.json |
| Simulation Phase | Every 30–45 seconds | active_shift.json |
| Debrief | Immediately on debrief load | profile.json + workplace save |
| Milestone completion | Immediately | profile.json + workplace save |
| App background (Android) | Immediately on background | active_shift.json |

---

## Corruption Recovery

- Last **3 successful profile saves** kept in `backups/` directory
- On profile load failure, attempt backups in reverse order
- On active shift load failure, discard corrupted shift — player returns to workplace select with no penalty
- On workplace state load failure, treat as fresh start for that workplace — persistent traps and milestone progress lost for that workplace only, profile and other workplaces unaffected
- Player notified of any recovery event with clear message — no silent failures

---

## Additional Features

**Multiple Profiles**
Support for multiple save profiles on the same device — useful for household sharing or trying different playstyles. Each profile is a separate `saves/` directory instance.

**Export / Import**
JSON format enables export and import of save files. Primarily useful for:
- Steam Workshop mod sharing (custom workplace states)
- Backup and restore
- Community sharing of notable highlight reel metadata

**Cloud Sync (Steam)**
- Syncs profile.json and workplace saves automatically
- Does not sync active_shift.json — in-progress shifts are local only
- Does not sync highlights — these can be large and are not progression-critical

---

## Persistent Trap State — Special Handling

The Persistent Trap system (unresolved traps carrying forward between shifts with PD accumulation) requires careful save handling:

- Trap positions and types saved per workplace in `workplaces/[id].json`
- PD accumulation value per trap saved alongside trap data
- On shift start, game reads workplace save to determine starting PD meter value
- On shift end (any end state), game updates workplace save with new persistent trap state
- If player upgrades from demo to full version, construction site workplace save carries over

Full persistent trap system details: Shift_and_Level_Structure.md

---

## Android-Specific Notes

- Compress JSON saves where file size is a concern — workplaces directory can grow large with 40+ environments
- Auto-save on app background is non-negotiable — Android can kill apps without warning
- Resume from active_shift.json on reopen — player should never lose an in-progress shift on Android
- Highlight reel metadata kept lightweight — no full replay data, event timestamps and types only
- Clear storage usage display in settings — let players see and manage save file sizes

---

## Conflicts Resolved From Prior Draft (Grok)

| Element | Resolution |
|---------|-----------|
| Player rank in profile save | Removed — no rank system. Replaced with cumulative stars and progression track states |
| "Victims" as career stat | Replaced with "total incidents" — consistent with corporate deadpan framing |
| "Reputation" as career stat | Removed — not confirmed. Stars and progression tracks cover this |
| Contract state in active shift save | Replaced with shift state — no contract system |
| contracts/ directory in file structure | Replaced with workplaces/ directory |
| Everything technical | Kept and expanded |

---

*Cross-reference Shift_and_Level_Structure.md for Persistent Trap system details, Progression_and_Scoring.md for progression track definitions, and Technical/Godot_Architecture.md for implementation architecture.*
