# Level Progression — Quick Reference

**Safety Code Violator GDD**
*High-level overview of how progression works across the full game. For detailed systems see referenced documents.*

---

## Core Principles

- **All workplaces available from the start** in the full version — no location gates, no unlock sequences
- **Progression makes you better, not merely allowed** — stars earned drive loadout, budget, and hazard pool expansion
- **No prescribed goals** — sandbox only. Score emerges from how well you play, not whether you completed an objective
- **Every shift contributes** — even a 1-star run adds to cumulative star total

---

## Demo / Free Version

| Property | Value |
|----------|-------|
| Available workplace | Construction Site only |
| Shift structure | Full system active |
| Progression | Stars accumulate normally, unlocks apply to Construction Site hazards only |
| Upgrade incentive | All stars and unlocks carry over to full version on upgrade |

---

## Full / Paid Version

| Property | Value |
|----------|-------|
| Available workplaces | All 40+ from the start |
| Default first workplace | Construction Site |
| After first shift | Player chooses freely what to do next |
| Progression | Cumulative stars across all workplaces drive all four tracks |

---

## What Progression Actually Unlocks

Three gameplay tracks plus one cosmetic track, all driven by cumulative stars. Full tables in **Progression_and_Scoring.md**.

| Track | What It Controls | Cap |
|-------|-----------------|-----|
| Loadout Size | How many hazard types per shift | 20 types at 200+ stars |
| Placement Budget | Total hazard instances per shift | 50 placements at 200+ stars |
| Per-Type Limit | Max instances of any single hazard | 4 at 140+ stars |
| Hazard Pool | Which specific hazards are available | Everything at 200+ stars |
| Cosmetics | Visual and audio flair | Ongoing |

---

## How a Typical Play Session Works

```
Player opens game
└── Selects a workplace from the full roster
    └── Reviews current state (persistent traps, starting PD if any)
        └── Selects loadout from available hazard pool
            └── Setup Phase — places hazards, no time limit
                └── Simulation Phase — watches shift unfold
                    └── Working Day Timer counts down
                        └── Shift ends via any valid end state
                            └── Debrief screen
                                ├── Star rating awarded
                                ├── Milestones checked
                                ├── Stars added to cumulative total
                                ├── Progression tracks updated
                                └── Player chooses next action
```

---

## Shift End States

| End State | Description |
|-----------|-------------|
| Natural resolution | All traps resolved, simulation quiet |
| Inspector clears site | Inspector disabled all remaining traps |
| Authorities arrive | Manager escalation Stage 3 — hard stop |
| Working Day ends | In-game timer reaches zero |
| Player ends manually | Player chooses to stop early |

Full details in **Shift_and_Level_Structure.md**.

---

## Level Completion vs. Mastery

| State | Condition |
|-------|-----------|
| Visited | Workplace selected for first time |
| Completed | 1 star earned on first shift |
| In Progress | Some milestones completed |
| Mastered | All 15 milestones completed — Mastery Badge awarded |

Full milestone list template in **Shift_and_Level_Structure.md**. Each workplace has 26 milestone stars available.

---

## Star Rating Quick Reference

| Stars | Requirements |
|-------|-------------|
| ⭐ | At least one incident |
| ⭐⭐ | Multiple incidents, authorities never called |
| ⭐⭐⭐ | Multiple incidents + PD never exceeded 75% + chain reaction of 2+ |
| ⭐⭐⭐⭐ | All above + Inspector and/or Manager caught |
| ⭐⭐⭐⭐⭐ | All above + PD never exceeded 50% + chain reaction of 3+ + Manager caught + Inspector caught |

Full scoring system in **Progression_and_Scoring.md**.

---

## Approximate Progression Timeline

| Milestone | Approx. Cumulative Stars |
|-----------|------------------------|
| Loadout grows to 5 types | 10 stars |
| Medium Suspicion hazards unlocked | 8–15 stars |
| High Suspicion Universal hazards unlocked | 25 stars |
| Per-type limit increases to 3 | 55 stars |
| All High Suspicion hazards unlocked | 100 stars |
| All Environment-Specific hazards unlocked | 130 stars |
| Full Dinosaur roster unlocked | 160 stars |
| Everything unlocked | 200+ stars |

---

## Replayability Features

- **Star rating improvement** — any shift can be replayed for a better rating, with the difference added to cumulative total retroactively
- **Milestone Tree** — 10–15 milestones per workplace, completable across any number of shifts in any order
- **Persistent traps** — unresolved traps carry forward between shifts, creating ongoing strategic consequences
- **Level variants** — time of day, weather, crew composition, and special conditions create meaningfully different experiences on the same map. Full list in **Level_Variants.md**
- **Weekly Challenge Shifts** — optional curated scenarios with preset conditions. Never required. Earn bonus stars
- **Infinite shifts** — any workplace can be played indefinitely. No caps on replays
- **Steam Leaderboards** — per-location and global. Chaos Score, Plausibility Rating, Viral Impact

---

## Planned Workplaces

Full list in **PlannedWorkplaces.md**. 40+ environments across seven category tags:
Industrial, Food Service, Office/Corporate, Medical/Science, Retail/Warehouse, Entertainment, Extreme/Wildcard.

---

## Cross-References

| Topic | Document |
|-------|----------|
| Full progression track tables | Progression_and_Scoring.md |
| Shift structure and end states | Shift_and_Level_Structure.md |
| Level variants | Level_Variants.md |
| All planned workplaces | PlannedWorkplaces.md |
| Hazard inheritance system | Hazard_Inheritance_System.md |
| Worker archetypes | Worker_Archetypes.md |
| Manager behavior and escalation | Manager_Behavior.md |

---

## Conflicts Resolved From Prior Draft (Grok)

| Element | Resolution |
|---------|-----------|
| Chapter-based unlock structure | Removed — all workplaces available from start |
| Named rank tiers (Junior/Skilled/Master Violator) | Removed — no rank system |
| Contract system throughout | Removed — sandbox only |
| Location unlock sequences | Removed — all locations available from start |
| Difficulty scaling via budget/objective strictness | Removed — budget driven by progression tracks only |
| Milestone Contracts as bosses | Removed — no contract system |
| New Game+ | Not confirmed — flagged for future consideration |
| Infinite mode | Kept — noted under Replayability Features |
| Per-location leaderboards | Kept — noted under Replayability Features |
| Weekly challenge contracts | Kept as optional Weekly Challenge Shifts — not contracts |
| Random modifiers concept | Absorbed into Level Variants system |

---

*This is a quick-reference overview document. All systems referenced here are fully detailed in their respective documents.*
