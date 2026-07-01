# Core Design Document — Safety Code Violator

**Safety Code Violator GDD**
*Confirmed design decisions, core loop summary, tone and humor guidelines, and content boundaries. Reference this document when making any new design decision to ensure it fits the game.*

---

## Confirmed Design Decisions

These are locked. Any new feature or mechanic must be compatible with all of the following:

| Decision | What It Means |
|----------|--------------|
| Pure sandbox — no prescribed goals | Score emerges from how well you play, not whether you completed an objective. No contracts, no required targets |
| All workplaces available from start (full version) | No location gates or unlock sequences. Progression makes you better, not merely allowed |
| Setup phase only — no mid-simulation intervention | Players place hazards during setup. Simulation plays out without player control. Speed controls available |
| Performance-based progression | Stars earned per shift drive all unlocks across four tracks |
| Isometric top-down camera | Fixed isometric perspective with pan and zoom |
| Standard cartoon proportions | No big heads. Silhouette clarity prioritized |
| Slapstick tone — no gore | Cartoonish violence only. Never grim or photorealistic |
| Godot engine | Steam (Windows + Linux) + Android from one codebase |
| Solo development | Scope decisions must account for single-developer production |
| Single standalone game — no DLC | Everything planned is in the full version. No post-launch paid content planned |

---

## Core Loop

Every shift follows the same three-phase structure. There are no contracts, no briefings with objectives, and no prescribed goals — the shift is a pure sandbox.

### Phase 1 — Setup Phase
- Player views the workplace map
- Current state shown — including any unresolved persistent traps from previous shifts
- Starting PD meter shown — may be above zero if leftover traps are accumulating suspicion
- Player selects loadout from available hazard pool (limited by progression track)
- Player places hazards within placement budget and per-type limits
- No time limit on setup — player takes as long as needed
- Workers are frozen during setup

### Phase 2 — Simulation Phase
- Workers unfreeze and begin their shift routines
- Player observes — no further placement or intervention
- Speed controls available: Pause / 1x / fast-forward up to 64x
- Working Day Timer counts down — shift ends when timer reaches zero
- PD meter fills as incidents occur
- Inspector spawns if PD meter maxes out
- Manager escalation ladder runs independently

### Phase 3 — Debrief
- Fires on any valid shift end state
- Star rating awarded (1–5)
- Milestones checked
- Stars added to cumulative progression total
- Highlight reel, scoring axes, Most Valuable Victim, Best Combo, Insurance Money Saved displayed
- Player chooses: replay, try different workplace, or return to menu

**Full shift structure details:** Shift_and_Level_Structure.md

---

## Emotional Journey

The intended player emotional arc per session:

| Phase | Player Feels |
|-------|-------------|
| Setup | Clever, focused, mischievous — evil architect energy |
| Simulation start | Anticipation — will the plan work? |
| First incident | Rising excitement |
| Chain reaction peak | Chaotic joy, giddy triumph |
| PD meter spiking | Tension — staying under the radar |
| Inspector/Manager | Heightened stakes, strategic thinking |
| Debrief | Smug satisfaction, already planning next run |

**Target experience per session:** At least one "I can't believe that actually worked" moment.

**Emotional loop:** Anticipation → Creation → Chaos → Catharsis → Reflection

This loop should feel highly replayable. Players should want "just one more shift."

---

## Session Design

- **Target session length:** 15–30 minutes real time
- **Fast-forward exists specifically** to let players skip slow periods — no boring stretches
- **One shift = one sitting** on Android — completable during a commute or short break
- **No long boring stretches** — the simulation should always have something happening or be fast-forwardable past quiet periods

---

## Tone & Humor Guidelines

### The Core Tone
Darkly comedic, satirical, and absurd. The game is gloriously, unapologetically silly about something that would be horrifying in reality. The gap between the corporate presentation and the actual events is where all the humor lives.

**The game should feel like:** *Untitled Goose Game* meets *Happy Tree Friends* in a corporate training video that has gone catastrophically wrong.

### Humor Styles

**1. Corporate Satire**
- Over-the-top buzzwords and corporate doublespeak ("rightsizing," "synergizing," "improving workplace wellness")
- Absurd performance metrics presented earnestly ("Insurance Claim Denial Rate," "Team Spirit Index")
- The debrief screen treats devastating incidents as productivity data
- The safety report uses language like "workstation-related incident" and "equipment anomaly"
- Management communications that completely ignore the rising incident count

**2. Slapstick & Irony**
- A worker slipping on a wet floor placed directly under a shelf of heavy objects
- Someone proudly using the "ergonomic" chair that has been sabotaged
- The Health and Safety Rep who keeps narrowly avoiding every trap until the final chain reaction
- Workers yelling "Watch out!" right before walking into exactly what they were warned about

**3. Black Comedy**
- Creative incident descriptions in the debrief ("Crushed by quarterly reports," "Defeated by stapler")
- The safety report noting "worker startled by apparition" with complete clinical neutrality
- The inspector filing paperwork about the incident that also caught the inspector

**4. Archetype-Driven Humor**
- Workers have distinct personalities that make their incidents funnier
- The Hero rushing to help and triggering the same trap
- The Oblivious One walking past the crocodile moat four times
- The Conspiracy Theorist investigating the wrong hazard entirely
- Full archetype roster: Worker_Archetypes.md

**5. Deadpan Escalation**
- Absurd hazards presented with complete seriousness
- The safety report flatly noting "worker injured by pterodactyl" and moving on
- Increasingly unhinged situations treated as routine corporate matters

### Content Guidelines

**Allowed:**
- Cartoonish / slapstick violence
- Dark humor about workplace incidents and injury
- Corporate evil, greed, and bureaucratic absurdity
- Absurd and fantastical situations (dinosaurs, crocodile moats, dragons)
- Animals of all kinds causing workplace chaos

**Avoided:**
- Realistic gore or graphic depictions of suffering
- Sexual content
- Real-world political commentary — keep satire general corporate rather than specific
- Targeting real companies, real people, or real events
- Content that would prevent Google Play or Steam store listing

---

## Key Systems Summary

*Brief overview only — each system has its own full document*

| System | Summary | Document |
|--------|---------|----------|
| Hazard placement | Three-tier suspicion system, loadout and budget limits | Hazard_Inheritance_System.md |
| PD meter | Fills with incidents, triggers inspector at max | Manager_Behavior.md |
| Inspector | Random patrol + accident-attracted, can trigger traps | Manager_Behavior.md |
| Manager/Foreman | Three-stage escalation ladder, retreat behavior | Manager_Behavior.md |
| Worker archetypes | 25 archetypes across four categories, daily routines, fix-it behavior | Worker_Archetypes.md |
| Scoring | Five-star system, ten scoring axes, debrief screen | Progression_and_Scoring.md |
| Progression | Four tracks driven by cumulative stars | Progression_and_Scoring.md |
| Persistent traps | Unresolved traps carry forward, accumulate PD | Shift_and_Level_Structure.md |
| Level variants | Time of day, weather, crew composition, special conditions | Level_Variants.md |
| Milestone trees | 15 milestones per workplace, 26 stars available each | Shift_and_Level_Structure.md |

---

## Placement System Quick Reference

- **Drag and drop** with ghosted real-time preview of exact position
- **Snap-to-grid** toggle — on by default, toggleable for free placement
- **Rotation support** for directional hazards (conveyor belts, ladders, shelves, etc.)
- **Validity feedback:** Green = valid placement / Yellow = high suspicion risk / Red = invalid or obstructed
- **Undo/Redo stack** — full undo/redo for all hazard placement during setup phase
- **Budget counter** always visible with live remaining count
- **Per-type counter** visible showing remaining instances of each selected hazard type

---

## Open Design Questions

*Items flagged during GDD review that have not been confirmed either way. To be decided during implementation phase.*

| Question | Context |
|----------|---------|
| Controller support on PC? | Deferred — to be decided once game interface design is finalized |

---

## Conflicts Resolved From Prior Drafts (Grok)

| Element | Resolution |
|---------|-----------|
| Contract system throughout | Removed — sandbox only, no prescribed goals |
| Mid-simulation intervention (drop hazards, emergency repairs) | Removed — setup phase only, confirmed |
| "Violator Hub" central location | **Resolved** — no hub space, no player sprite. Workplace select is a category-based menu (category → configuration sub-menu). See `UI_and_Controls.md` |
| Undo/Redo during setup | **Confirmed** — full undo/redo stack for all setup phase placement |
| "Restart Shift with same setup" | **Confirmed** — available from the debrief screen. Same trap layout pre-loaded, plays as a normal shift |
| Worker health/resilience for v1 | **Confirmed** — per-worker Health/Resilience attribute added to Worker Archetypes |
| New Game+ | **Cut** — not in scope for v1 |
| Android cloud saves | **Confirmed** — Google Play Games cloud sync. See `Save_System.md` |
| Named specific workers (Kevin, Karen, Chad) | Archetype flavor only, not persistent named characters |
| Rank progression (Junior/Skilled/Master Violator) | Removed — no rank system |
| 2.5D angled view camera | Replaced — confirmed isometric top-down |
| Big heads character proportions | Removed — standard cartoon proportions |
| Failure = partial rewards + cutscene | Revised — stars earned are kept, level restarts, no special cutscene confirmed |
| Early/mid/late game location gating | Removed — all workplaces available from start |

---

*This is the canonical core design reference. When in doubt about whether a new feature fits the game, check it against the Confirmed Design Decisions table at the top of this document.*
