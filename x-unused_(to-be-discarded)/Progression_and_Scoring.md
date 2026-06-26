# Progression & Scoring System

**Safety Code Violator GDD**
*Performance-based progression across three independent tracks. Stars earned per shift drive all unlocks. Numbers are design targets — playtesting will require tuning.*

---

## Overview

Safety Code Violator uses a **star-based performance progression system**. There are no level gates or mandatory sequences — in the full version, all workplaces are available from the start. Instead, cumulative stars earned across all shifts drive three independent progression tracks that make each shift more capable than the last.

This means:
- A player who masters the restaurant earns stars that unlock better loadouts for the casino
- Replaying any shift for a better star rating always contributes to progression
- No shift is ever "wasted" — even a 1-star run contributes

---

## Star Rating System

Each shift is rated 1-5 stars at debrief based on **minimum threshold requirements per tier.** Players always know exactly what they need to do to improve their rating.

| Rating | Requirements |
|--------|-------------|
| ⭐ | At least one incident occurred during simulation |
| ⭐⭐ | Multiple incidents occurred AND authorities were never called |
| ⭐⭐⭐ | Multiple incidents + PD meter never exceeded 75% + at least one chain reaction of 2 or more hazards |
| ⭐⭐⭐⭐ | All ⭐⭐⭐ requirements + Inspector and/or Manager caught in a trap |
| ⭐⭐⭐⭐⭐ | All ⭐⭐⭐⭐ requirements + PD meter never exceeded 50% + chain reaction of 3 or more + Manager caught + Inspector caught |

### Design Notes

- The 50% PD ceiling for 5 stars is the core mastery challenge — catching the Manager and Inspector generates PD, so doing both while staying under 50% requires extremely subtle, layered trap placement
- Star requirements are **cumulative upward** — earning ⭐⭐⭐⭐ automatically means all lower requirements were also met
- Stars are awarded at the end of simulation regardless of how the shift ended — even if authorities arrived, stars already earned are kept
- Each shift can be replayed for a better rating at any time — improved ratings retroactively add the difference to the cumulative total (e.g. improving from 3 to 5 stars adds 2 stars to the pool)

### Scoring Axes (Debrief Display)

The debrief screen shows performance across all axes so players understand exactly what contributed to their rating and what to improve:

| Axis | What It Measures |
|------|-----------------|
| Incident Count | Total number of workers caught by hazards |
| Chain Reaction Length | Longest unbroken chain of one hazard triggering another |
| Hazard Efficiency | Workers caught per hazard placed — rewards clever placement over spam |
| PD Rating | Final PD meter percentage at end of shift — lower is better |
| Inspector Outcome | Caught in trap (bonus) / disabled all traps (note) / never triggered (perfect) |
| Manager Outcome | Caught (bonus) / retreated (note) / called authorities (flag) |
| Variety Bonus | Whether multiple hazard types were used rather than spamming one |
| Creativity Bonus | Chain reactions involving animals, falling objects, and environmental hazards all in one chain |

---

## Progression Tracks

Stars accumulate permanently across all shifts in all workplaces. All three tracks unlock simultaneously based on the same cumulative star total.

Approximate total shifts in a full playthrough: **200+**
Pacing intention:
- **Early game (shifts 1–30):** Unlocks every 3–5 shifts. Frequent rewards, teaching systems
- **Mid game (shifts 31–100):** Unlocks every 8–12 shifts. Experimentation and combination
- **Late game (shifts 101–200+):** Unlocks every 15–25 shifts. Mastery rewards

---

### TRACK 1 — LOADOUT SIZE
*How many hazard types the player can bring into a single shift*

| Cumulative Stars | Loadout Size |
|-----------------|--------------|
| 0 (start) | 3 types |
| 5 | 4 types |
| 10 | 5 types |
| 18 | 6 types |
| 28 | 7 types |
| 40 | 8 types |
| 55 | 9 types |
| 72 | 10 types |
| 92 | 12 types |
| 115 | 14 types |
| 140 | 16 types |
| 170 | 18 types |
| 200+ | 20 types (cap) |

**Design rationale:**
Starting at 3 forces real decisions in early play. Reaching 20 at 200+ stars gives veterans a generous but not unlimited toolkit. The jump from 10 to 12 at 92 stars (rather than increments of 1) marks the transition into late game and feels like a meaningful reward.

---

### TRACK 2 — PLACEMENT BUDGET
*Total number of individual hazard instances placeable per shift*

| Cumulative Stars | Placement Budget |
|-----------------|-----------------|
| 0 (start) | 5 placements |
| 5 | 7 placements |
| 10 | 9 placements |
| 18 | 12 placements |
| 28 | 15 placements |
| 40 | 18 placements |
| 55 | 22 placements |
| 72 | 26 placements |
| 92 | 30 placements |
| 115 | 35 placements |
| 140 | 40 placements |
| 170 | 46 placements |
| 200+ | 50 placements (cap) |

**Design rationale:**
Starting at 5 is deliberately tight — forces careful placement rather than coverage. 50 at the cap feels powerful without being unlimited. The budget grows faster than loadout size in the mid game, meaning players have more placements before they have more types — rewarding depth over breadth early on.

---

### TRACK 2B — PER-TYPE PLACEMENT LIMIT
*Maximum instances of any single hazard type per shift, regardless of total budget*

| Cumulative Stars | Per-Type Limit |
|-----------------|---------------|
| 0 (start) | 2 of any single type |
| 55 | 3 of any single type |
| 140 | 4 of any single type |
| 200+ | 4 of any single type (cap — does not increase further) |

**Design rationale:**
Prevents players from finding one effective hazard and spamming it exclusively. Encourages genuine variety. Ties directly into the Variety Bonus scoring axis. Cap at 4 means even late-game veterans must diversify their loadout meaningfully.

---

### TRACK 3 — HAZARD POOL
*Which specific hazards are available to select for your loadout*

Unlocks in batches by suspicion tier and environment category. Low Suspicion hazards unlock first — teaching subtlety before handing players obvious chaos tools. High Suspicion hazards come later because they are powerful but PD-costly, so players need PD system fluency before using them effectively.

| Cumulative Stars | Hazards Unlocked |
|-----------------|-----------------|
| 0 (start) | All Low Suspicion hazards — Universal pool + current environment |
| 8 | Medium Suspicion hazards — Universal pool |
| 15 | Medium Suspicion hazards — Cross-Environment pool for current environment's category |
| 25 | High Suspicion hazards — Universal pool |
| 38 | Medium Suspicion hazards — ALL Cross-Environment category pools |
| 55 | High Suspicion hazards — Cross-Environment pool for current environment's category |
| 75 | Environment-Specific hazards — first workplace completed |
| 100 | High Suspicion hazards — ALL Cross-Environment category pools |
| 130 | Environment-Specific hazards — all workplaces |
| 160 | Full Dinosaur roster |
| 200+ | Everything unlocked |

**Design rationale:**
- Low Suspicion first teaches players that subtlety is rewarded before they discover how fun obvious chaos is
- High Suspicion hazards unlocking in stages (Universal first, then Cross-Environment by category, then all) means players encounter them gradually rather than all at once
- Dinosaurs as a late unlock makes them feel genuinely special — a veteran reward
- Environment-Specific hazards unlocking per workplace gives players a reason to explore new environments even if they're comfortable with familiar ones

---

## Demo / Free Version Progression

The demo version contains only the Construction Site. Progression still functions normally:

- Stars earned on the Construction Site accumulate and unlock all three tracks
- Since only one environment exists in the demo, hazard pool unlocks only apply to Construction Site hazards
- If the player upgrades to the full version, all accumulated stars and unlocks carry over
- This means a player who mastered the demo arrives at the full version with a meaningful head start — a deliberate incentive to upgrade

---

## Progression Summary Table

*Quick reference showing what a player has access to at key milestones*

| Stars | Loadout | Budget | Per-Type Limit | Hazard Pool Status |
|-------|---------|--------|---------------|-------------------|
| 0 | 3 types | 5 | 2 | Low Suspicion Universal + environment |
| 10 | 5 types | 9 | 2 | + Medium Universal + Cross-Environment |
| 25 | 7 types | 15 | 2 | + High Suspicion Universal |
| 55 | 9 types | 22 | 3 | + High Suspicion Cross-Environment (current) |
| 100 | 12 types | 35 | 3 | + High Suspicion all Cross-Environment |
| 140 | 16 types | 40 | 4 | + Environment-Specific all workplaces |
| 160 | 18 types | 46 | 4 | + Full Dinosaur roster |
| 200+ | 20 types | 50 | 4 | Everything |

---

## Playtesting Notes

All numbers in this document are **design targets**. The following should be evaluated during playtesting:

- Is 5 placements at the start too restrictive or appropriately challenging?
- Does the PD 50% ceiling for 5 stars feel achievable with skill, or frustratingly tight?
- Is the gap between loadout size and placement budget growth rate correct in mid game?
- Does the per-type cap of 4 feel restrictive or freeing at late game?
- Are dinosaurs unlocking at a satisfying moment or too late?
- Does the star rating system produce consistent, readable results across different playstyles?

---

*This is a living document. Numbers will be revised based on playtesting feedback.*
