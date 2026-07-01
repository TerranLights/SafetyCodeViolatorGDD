# Hazard System — Overview

**Safety Code Violator GDD**
*High-level overview of the hazard system. For the full hazard library see `Master_Hazards.md`. For the class architecture and inheritance structure see `Hazard_Inheritance_System.md`.*

---

## Overview

The Hazard System is the creative core of *Safety Code Violator*. Players combine hundreds of individual hazards into complex, interlocking chains — the goal being maximum chaos with minimum suspicion. Subtlety is rewarded over brute force.

---

## Hazard Tiers

Every hazard belongs to one of three availability tiers based on how widely it appears across workplace environments:

| Tier | Name | Description |
|------|------|-------------|
| 1 | **Universal** | Available in every workplace environment — the baseline toolkit |
| 2 | **Cross-Environment** | Available to a tagged group of environments (e.g. Industrial, Food Service, Office/Corporate) |
| 3 | **Environment-Specific** | Unique to one workplace setting — unlocked when that environment is played |

Full tier structure and environment category tags: `Hazard_Inheritance_System.md`

---

## Suspicion Tiers

Every hazard also has a suspicion tier that determines how much each incident contributes to the Plausible Deniability meter:

| Suspicion | PD Contribution | Design Intent |
|-----------|----------------|---------------|
| **Low** | Minimal | Looks like a genuine workplace accident. Safe to use freely |
| **Medium** | Moderate | Deniable but will accumulate. Use deliberately |
| **High** | Significant | Obviously intentional. Use sparingly or as a chain reaction endpoint |

The core tension: the most satisfying hazards are High Suspicion. The highest-scoring runs use Low Suspicion hazards chained together cleverly rather than reaching for the obvious big hit.

Full PD meter behavior: `Plausible_Deniability.md`

---

## Hazard Properties

Every hazard has the following attributes:

| Property | Description |
|----------|-------------|
| **Suspicion Tier** | Low / Medium / High — drives PD meter contribution per incident |
| **Trigger Type** | Immediate / Worker-interaction / Timed / Chain — how and when the hazard activates |
| **Combo Potential** | Whether and how this hazard chains into or enables other hazards |
| **Active vs. Passive** | Passive hazards wait to be triggered. Active hazards (all animals) move semi-randomly and can trigger other traps on their own |

---

## Placement Rules

- Hazards are placed during the **Setup Phase only** — no placement or intervention once simulation begins
- Placement is limited by the player's current **loadout size** (how many hazard types) and **placement budget** (total instances)
- A **per-type limit** prevents spamming any single hazard type
- All three limits expand as cumulative stars are earned through the progression system
- Previously placed unresolved traps from prior shifts remain on the map and cannot be repositioned

Full placement budget and loadout progression: `Progression_and_Scoring.md`
Full shift structure and persistent trap rules: `Shift_and_Level_Structure.md`

---

## Combo System

The highest-scoring plays chain multiple lower-suspicion hazards together rather than using one large obvious trap. A five-link chain of Low Suspicion hazards scores better, contributes less PD, and is more satisfying than a single High Suspicion hazard used alone.

Chain reaction bonuses apply when one hazard directly triggers another — longer unbroken chains earn multipliers on the Chaos Score.

Full combo design rules and examples: `Combo_Ideas_and_Design_Rules.md`

---

## Hazard Pool Progression

Players begin with access to Low Suspicion Universal hazards only. Higher-tier and environment-specific hazards unlock as cumulative stars are earned:

- Medium Suspicion hazards unlock early — teaching the PD system before obvious chaos tools are available
- High Suspicion hazards unlock in stages
- Environment-Specific hazards unlock per workplace as it is played
- Dinosaurs are a late-game unlock — a veteran reward

Full unlock table: `Progression_and_Scoring.md`

---

## Key Reference Documents

| Topic | Document |
|-------|----------|
| Full hazard list by category | `Master_Hazards.md` |
| Tier structure and environment inheritance | `Hazard_Inheritance_System.md` |
| PD meter and suspicion system | `Plausible_Deniability.md` |
| Placement budget and hazard pool progression | `Progression_and_Scoring.md` |
| Combo design rules and chain reaction examples | `Combo_Ideas_and_Design_Rules.md` |
| Shift structure and placement rules | `Shift_and_Level_Structure.md` |

---

## Conflicts Resolved From Prior Draft

| Element | Resolution |
|---------|-----------|
| Hazard categories (Environmental, Equipment Sabotage, Workflow, Psychological) | Replaced — hazards are now organised by availability tier (Universal / Cross-Environment / Environment-Specific) and suspicion tier (Low / Medium / High) |
| "Some can be dropped mid-simulation as emergency interventions" | Removed — Setup Phase only. No mid-simulation placement confirmed |
| "Unlock tools as you complete contracts" | Replaced — hazard pool unlocks via cumulative star progression, no contract system |
| "Lethality" and "Cover Story Strength" as hazard properties | Replaced — confirmed properties are Suspicion Tier, Trigger Type, Combo Potential, and Active/Passive |
| "Signature Traps" as a named feature | Removed — not in current GDD. Style/Irony Bonus in the scoring system covers thematic trap rewards |
