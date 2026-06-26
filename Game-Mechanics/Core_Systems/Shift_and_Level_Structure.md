# Shift & Level Structure

**Safety Code Violator GDD**
*Defines the relationship between levels and shifts, how shifts begin and end, and how unresolved traps carry consequences across multiple shifts.*

---

## Core Terminology

These terms are used precisely throughout the GDD:

| Term | Definition |
|------|-----------|
| **Level** | A single workplace environment (e.g. Construction Site, Casino, Hospital). Contains unlimited shifts. Persists permanently in the player's record. |
| **Shift** | A single playthrough of a level. One setup phase, one simulation phase, one debrief. The atomic unit of gameplay. |
| **Complete a Level** | Earn at least 1 star on your first shift in that workplace. One-time. |
| **Master a Level** | Complete all milestones in that level's Milestone Tree. Ongoing. |
| **Complete a Shift** | Reach any valid end state during simulation. Awards stars, checks milestones, updates record. |

---

## Level Structure

```
Game
└── Levels (workplace environments — 40+)
    ├── First Shift — completes the level (1 star minimum)
    ├── Milestone Tree (15 per level, completed across any number of shifts)
    └── Shifts (unlimited, repeatable, each awards stars toward cumulative total)
        └── Debrief (star rating, milestones checked, stars awarded, record updated)
```

Every level is available from the start in the full version. Completing a level simply means visiting it and causing at least one incident. Mastering it is the long-term challenge.

---

## Shift Structure

Every shift follows the same three-phase structure:

### Phase 1 — Briefing
- Player views the workplace map
- Current state is shown — including any unresolved traps left from previous shifts (see Persistent Traps below)
- Current PD meter starting value is shown — may be above zero if leftover traps are accumulating suspicion
- Player selects their loadout from available hazard pool (up to loadout size limit)
- Player can review worker roster for this shift (archetypes, crew size, any special conditions)
- Level variant conditions shown if active (weather, time of day, etc.)

### Phase 2 — Setup Phase
- Workers are frozen
- Player places hazards from their loadout up to their placement budget
- Per-type placement limit applies
- No time limit on setup — player takes as long as needed
- Previously placed unresolved traps from prior shifts are visible and occupy their positions
- Player cannot remove or reposition traps from previous shifts — only new placements this shift

### Phase 3 — Simulation Phase
- Workers unfreeze and begin their shift
- Player observes in real time with speed controls:
  - Pause
  - 1x (normal speed)
  - Fast-forward (up to 64x)
- The Working Day Timer counts down (see below)
- PD meter fills as incidents occur
- Manager and Inspector behave per their respective systems
- Player cannot place new traps during simulation
- Player can end the shift manually at any time

---

## Shift End States

A shift ends — and debrief triggers — when any of the following occur:

| End State | Description | Stars Impact |
|-----------|-------------|-------------|
| **Natural resolution** | All traps resolved, chain reactions complete, simulation quiet | Full stars earned — ideal outcome |
| **Inspector clears site** | PD meter maxed, inspector arrived and disabled all remaining traps | Stars earned up to that point kept |
| **Authorities arrive** | Manager escalation Stage 3 triggered — hard stop | Stars earned up to that point kept |
| **Working Day ends** | In-game timer reaches end of shift — see below | Stars earned up to that point kept |
| **Player ends shift manually** | Player chooses to end early via menu | Stars earned up to that point kept |

Stars are never lost at end of shift — whatever was earned during simulation is kept regardless of how the shift ended.

---

## The Working Day Timer

Every simulation represents one full in-game working day. The timer prevents softlocks caused by unactivated traps that workers never reach.

**How it works:**
- The simulation represents an 8-hour working day
- The Working Day Timer is visible to the player during simulation
- When the timer reaches zero, the shift ends automatically — debrief fires with whatever was earned
- Any unresolved traps remain on the map as Persistent Traps (see below)
- Speed controls affect how quickly real time passes relative to in-game time:
  - At 1x speed: approximately 8–10 real minutes per shift
  - At 64x speed: shifts resolve in under a minute
- The player controls pacing entirely through speed controls

**Tone note:** The shift ending because the working day is over fits the game's corporate satire perfectly. The safety report simply notes that the day concluded with an unusually high number of incidents. Unresolved traps are noted as "equipment anomalies pending review."

---

## Persistent Traps

Unresolved traps that remain at the end of a shift **stay on the map** and carry forward into subsequent shifts at the same workplace. This creates a strategic consequence for inefficient trap placement without hard-punishing the player.

### Passive Suspicion Accumulation

Each unresolved trap accumulates PD passively between shifts. The rate depends on suspicion tier:

| Trap Tier | PD Accumulation Per Subsequent Shift |
|-----------|-------------------------------------|
| Low Suspicion | +2% starting PD per shift |
| Medium Suspicion | +5% starting PD per shift |
| High Suspicion | +10% starting PD per shift |

This means:
- One leftover Low Suspicion trap from last shift: +2% starting PD — barely noticeable
- Three leftover High Suspicion traps from two shifts ago: potentially +30% starting PD before you've placed anything — significant disadvantage
- A pile of accumulated unresolved traps from multiple shifts: could start a new shift with the inspector already on-site

### Inspector Pre-Spawn Threshold

If accumulated starting PD reaches or exceeds **75%** at the beginning of a new shift, the Safety Inspector spawns on-site immediately at simulation start — without waiting for the PD meter to fill during play. This is the organic version of the "Inspection Day" level variant, triggered by the player's own carelessness rather than a preset condition.

### Loadout and Budget Refresh

Despite persistent traps, the player's loadout and placement budget **fully refresh** at the start of every shift:
- Full hazard type allotment restored
- Full placement budget restored
- Per-type placement limit restored
- Previously placed traps do NOT count against the new shift's budget

This means the player always has their full toolkit available — the penalty for leftovers is purely the PD accumulation, not a reduced ability to place new hazards.

### Strategic Implications

Persistent traps create several interesting strategic decisions:

**Trap efficiency pressure:**
Placing a full loadout knowing some traps might not trigger leaves a suspicion burden for next shift. Fewer, more targeted placements that guarantee resolution may score better long-term across multiple shifts.

**Using leftovers as assets:**
A veteran player can deliberately design new traps to trigger old unresolved ones as part of a chain reaction — converting a liability into a scoring opportunity. A leftover Medium Suspicion trap from last shift becomes the first link in a new chain reaction this shift.

**Archetype interactions:**
The Paranoid One's tendency to avoid suspicious areas means certain trap placements may never trigger against them, accumulating across multiple shifts. Knowing your worker roster before setup matters more than ever.

**Cleanup runs:**
A player might occasionally run a shift with the specific goal of triggering all remaining persistent traps and clearing the map — accepting lower star potential this shift in exchange for a clean starting position next shift.

**Snowball risk:**
Ignoring persistent traps across many shifts creates an escalating PD disadvantage that compounds — three mediocre shifts can make the fourth shift start with the inspector already waiting. Managing this risk is a long-term skill.

---

## Between-Shift State Summary

When a shift ends and before the next one begins, the following is preserved and carried forward:

| Element | Carries Over? | Notes |
|---------|--------------|-------|
| Unresolved traps | Yes | Remain on map, accumulate PD passively |
| PD meter value | Partially | Resets to zero but immediately refills based on persistent trap accumulation |
| Worker roster | No | New crew each shift — fresh archetypes |
| Level variant conditions | No | New conditions each shift unless manually set |
| Loadout and budget | No | Fully refreshes each shift |
| Stars earned | Yes | Cumulative total carries forward permanently |
| Milestones completed | Yes | Permanent — never reset |

---

## Debrief Screen

After every shift end state, the debrief screen presents results with full corporate deadpan:

- **Star rating** (1–5) with breakdown of which requirements were and weren't met
- **Top 5 moments** from the simulation — highlighted for review and replay
- **"Most Valuable Victim" award** — worker who contributed most to the chaos score
- **"Best Combo" breakdown** — highest-scoring chain reaction of the shift, step by step
- **Total Insurance Money "Saved"** for the company — presented as a positive corporate metric
- **Scoring axes display** — all axes shown with performance indicators
- **Viral Impact rating** — how shareable this shift was
- **Milestones completed this shift** — any newly ticked milestones highlighted
- **Persistent trap warning** — if unresolved traps remain, their accumulated PD impact for next shift is shown clearly so the player can make an informed decision
- **Replay / Continue prompt** — replay this shift, try another workplace, or return to menu

### First Shift Special Treatment

A player's very first shift in any new workplace receives a special debrief header — a corporate "Welcome to Your New Assignment" briefing presented before the usual stats. Fits the corporate satire tone and makes each new environment feel like an occasion.

---

## Level Completion vs. Level Mastery

| State | Condition | What It Unlocks |
|-------|-----------|----------------|
| **Visited** | Workplace selected for first time | Briefing screen, map visible |
| **Completed** | 1 star earned on first shift | Workplace entry in permanent record, Milestone Tree activated, Environment-Specific hazard tracking begins |
| **In Progress** | Some milestones completed | Ongoing — no specific state change |
| **Mastered** | All milestones completed | Mastery Badge displayed on workplace selection screen |

---

## Milestone Tree

Every level has a Milestone Tree of 15 achievements completable across any number of shifts in any order. Completing milestones awards bonus stars toward cumulative progression total.

**Universal milestone template (applies to every workplace):**

| Milestone | Description | Stars Awarded |
|-----------|-------------|--------------|
| First Incident | Cause your first incident in this workplace | 1 |
| Chain Reaction | Trigger a chain reaction of 2 or more | 1 |
| Clean Hands | Complete a shift with PD never exceeding 50% | 1 |
| Animal Instinct | Cause an incident using an animal hazard | 1 |
| Caught the Inspector | Inspector triggers one of your traps | 2 |
| Caught the Manager | Manager caught during a shift | 2 |
| Perfect Shift | Achieve 5 stars in this workplace | 3 |
| Variety Pack | Use at least 5 different hazard types in one shift | 1 |
| Domino Effect | Trigger a chain reaction of 4 or more | 2 |
| Untouchable | Complete a shift with PD never exceeding 25% and authorities never called | 3 |
| Environment Specialist | Cause an incident using an Environment-Specific hazard | 2 |
| Prehistoric Problem | Cause an incident using a dinosaur hazard | 1 |
| Wrong Place Wrong Time | Catch Inspector AND Manager in the same shift | 3 |
| Style Points | Trigger the Style/Irony Bonus in this workplace | 1 |
| Clean Slate | Complete a shift with zero persistent traps remaining | 2 |

**Total milestone stars per workplace: 26**
**Total milestone stars across all 40+ workplaces: 1,040+**

This means milestone hunting alone can drive a significant portion of the 200+ star progression target — a player who focuses on milestones will progress substantially even without chasing perfect star ratings on every shift.

---

*This is a living document. Shift timing values and milestone star awards will be refined during playtesting.*
