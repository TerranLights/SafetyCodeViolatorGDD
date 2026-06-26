# Construction Site — Level Design Document

**Safety Code Violator GDD**
*First environment. Demo/free version. Serves as the template for all subsequent workplaces.*

---

## Overview

A mid-sized urban construction site building a commercial tower. A large outdoor/indoor hybrid site with tall scaffolding, heavy equipment, and workers operating at dangerous heights. Multiple distinct zones connected by pathways workers travel throughout their shift.

This location excels at delivering **big, cinematic, screen-filling chaos** and will produce some of the most shareable highlight reels in the game. Heavy machinery and gravity are your best friends here.

**Tone:** Deadpan cartoon slapstick. Absurd hazards presented completely straight. Workers yell "Watch out!" right before ironically walking into the thing they were warned about. Glorious slow-motion falls from great heights. "It's not safety regulations, it's just common sense" — presented without irony.

**Chain reaction potential:** Extremely high. One falling beam can take out many. The scale and number of workers makes plausible deniability harder to maintain, which rewards subtle, layered trap placement over brute force.

---

## Crew

Variable crew size depending on shift conditions and level variants:
- **Small crew:** 5–8 workers
- **Standard crew:** 10–15 workers
- **Large crew:** 20+ workers

Worker types include builders, welders, crane operators, and supervisors. See WorkerArchetypes.md for full roster. See LevelVariants.md for crew composition variants.

---

## Zones

### 1. Perimeter / Entrance
*Where the Safety Inspector spawns. Workers and deliveries enter and exit here.*

**Worker Activities:**
- Arriving and leaving at shift start/end
- Signing in at a security checkpoint
- Receiving and unloading deliveries
- Standing around doing nothing (it's a construction site)

**Existing Environmental Hazards:**
- Delivery trucks reversing with poor visibility
- Heavy materials being unloaded from trucks
- Loose gravel and uneven ground
- Temporary fencing and barriers near drops

**Trap Slots:**

| Trap | Suspicion Tier | Description |
|------|---------------|-------------|
| Tampered truck brakes | Low | Delivery truck rolls unexpectedly when driver steps out |
| Mislabeled/unstable crates | Low | Improperly stacked delivery crates topple onto workers |
| Loose gravel patch | Low | Strategically placed near entrance, causes slips |
| Removed fencing section | Medium | Gap in temporary fencing near a drop or hazard |
| Faulty security barrier | Medium | Swings outward unexpectedly into arriving workers |
| Puddle near electrical terminal | Medium | Workers signing in get a nasty surprise |
| Crocodile moat | High | Surrounds the entrance gate. Crocodiles. |
| Absurd delivery load | High | Truck loaded with bowling balls, anvils, or similar |
| Fake entrance | High | Second gate that leads somewhere terrible |

**Strategic Note:** Since the Safety Inspector spawns here, trapping this zone early can slow or neutralize the inspector before they reach the rest of the site. High-risk, high-reward plays.

---

### 2. Site Trailer / Foreman's Office
*On-site headquarters. A beat-up portable office trailer parked on the edge of the ground level. Where the Foreman runs things from, where paperwork gets done, and where workers go to check in, get yelled at, or grab lunch.*

**Worker Activities:**
- Checking in with the Foreman
- Taking lunch and coffee breaks
- Filing paperwork and timesheets
- Complaining about working conditions (ironic given the circumstances)
- Sheltering from bad weather

**Existing Environmental Hazards:**
- Ancient, overloaded electrical wiring
- Rickety trailer steps and entrance
- Precariously stacked filing cabinets and paperwork
- Ancient coffee maker that is definitely a fire hazard
- Structural instability of the trailer itself

**Trap Slots:**

| Trap | Suspicion Tier | Description |
|------|---------------|-------------|
| Tampered coffee maker | Low | Electrocutes or explodes on use |
| Loose trailer steps | Low | Collapses when stepped on |
| Overloaded power strip | Low | Causes electrical fire when enough devices are running |
| Unstable filing cabinet | Medium | Tips over onto whoever opens the bottom drawer |
| Rigged office chair | Medium | Collapses or launches occupant across the room |
| Gas leak near break room microwave | Medium | Microwave spark triggers explosion |
| Foreman's desk rigged to collapse | High | Takes out anyone sitting across from it |
| Trailer tipped off its supports | High | Entire trailer lists sideways, chaos ensues |
| Bear in the bathroom | High | Self explanatory |

**Strategic Note:** The Foreman is a special worker type — worth significant bonus points and harder to catch than regular workers. The trailer is also a natural gathering point, meaning a single well-placed trap can catch multiple workers at once. See ManagerBehavior.md for full Foreman/Manager behavior system.

---

### 3. Ground Level Work Area
*The heart of the construction site. The busiest zone, the most workers at any given time, and the heaviest machinery. Maximum chain reaction potential.*

**Worker Activities:**
- Operating forklifts and heavy machinery
- Mixing and pouring concrete
- Cutting and welding materials
- Transporting materials across the site
- Shouting at each other over loud machinery

**Existing Environmental Hazards:**
- Forklifts with poor visibility
- Open concrete mixer
- Welding sparks near fuel canisters
- Exposed rebar sticking out of surfaces
- Heavy suspended loads from the site crane
- Deep foundation pit on one edge of the zone

**Trap Slots:**

| Trap | Suspicion Tier | Description |
|------|---------------|-------------|
| Tampered forklift steering | Low | Forklift veers unpredictably during operation |
| Mislabeled fuel/chemical barrels | Low | Workers mix the wrong things together |
| Loosened rebar coverings | Low | Exposed ends catch anyone walking past |
| Rigged concrete mixer | Medium | Launches concrete at high speed when opened |
| Removed crane load safety pin | Medium | Suspended load drops at worst possible moment |
| Welding tank valve tampered | Medium | Causes uncontrolled flame burst |
| Foundation pit fencing removed | Medium | Workers walk off the edge |
| Runaway forklift | High | Forklift drives itself across the entire zone |
| Crane goes full spin mode | High | Suspended load swings in full circles across the zone |
| Crocodiles in the foundation pit | High | They were already in the moat. They got around |

**Strategic Note:** This zone has the highest chain reaction potential on the entire site. A forklift hitting a barrel that ignites near a crane load that drops into the foundation pit is exactly the kind of sequence that maximizes your score multiplier. Patient, layered trap placement pays off most here.

---

### 4. Building Frame / Scaffolding
*The most vertical zone on the site and the most dangerous by nature. Multiple levels of scaffolding, exposed floors, elevation drops everywhere, and workers constantly moving up and down. Falling hazards reach their full potential here.*

**Worker Activities:**
- Climbing ladders and scaffolding between levels
- Laying flooring and walls on upper levels
- Operating the site crane
- Welding and cutting at height
- Carrying heavy materials up and down
- Leaning over edges because apparently that's fine

**Existing Environmental Hazards:**
- Multiple elevation drops at every level
- Ladders that see heavy daily use
- Crane operating overhead constantly
- Welding sparks near wooden framing
- Loose planks and unsecured flooring
- Materials constantly being hoisted up and down

**Trap Slots:**

| Trap | Suspicion Tier | Description |
|------|---------------|-------------|
| Loosened ladder rungs | Low | Rung snaps partway up, worker falls |
| Unsecured scaffolding plank | Low | Collapses when stepped on |
| Fraying crane hoist rope | Low | Load drops at worst possible moment |
| Welding tank near wooden framing | Low | Sparks cause fire that spreads upward through levels |
| Removed safety railing | Medium | Workers lean where railing should be |
| Rigged pulley system | Medium | Reverses direction unexpectedly, sends load the wrong way |
| Greased ladder | Medium | Worker makes it halfway before sliding straight back down into something |
| Crane full spin mode | High | Suspended load swings in full circles across multiple levels |
| Grand piano on top floor | High | Inexplicably present. Inevitably descends |
| Pterodactyl nest on upper level | High | Disturbed when workers reach the top floor |
| Gorilla on scaffolding | High | Has climbed up. Will not come down. Throws things |
| Entire scaffolding section collapse | High | One pin removed, dominoes from there |

**Strategic Note:** This zone has the most vertical chain reaction potential — a falling worker from the top level can trigger a trap on a middle level which sends something into the ground level below. Three-layer chains are achievable here. The crane overlaps with every level simultaneously making it a linchpin hazard worth prioritizing. The inspector must climb to reach upper-level hazards, meaning a rigged ladder can neutralize them before they get there.

---

## Workers

Variable crew size per shift. Full archetype roster in WorkerArchetypes.md. Full level variant conditions (crew composition, time of day, weather) in LevelVariants.md.

**Construction Site specific archetypes to prioritize in crew generation:**
- Crane operators — spend time at height, high chain reaction value
- Welders — near heat and fuel sources, natural accident potential
- Supervisors — act as secondary Manager-adjacent figures, worth bonus points
- Labourers — bulk of crew, fill Oblivious/Clumsy/Hero roles

---

## The Safety Inspector

Spawns at the Perimeter/Entrance when the Plausible Deniability meter maxes out. Full behavior documented in ManagerBehavior.md.

**Construction Site specific notes:**
- Must climb scaffolding to reach Zone 4 hazards — rigged ladders can stop them before they get there
- Crane full spin mode affects the inspector if they're in range — intentional and very funny
- Perimeter/Entrance trap placement can neutralize the inspector before they even enter the site

---

## Plausible Deniability Meter

Full system documented in ProgressionAndScoring_FINAL.md. Construction Site specific notes:

- Scale of the site and number of workers makes witnesses more likely — obvious traps generate more PD here than in smaller environments
- Chain reactions involving heavy machinery generate significant PD even at Low Suspicion tier due to scale
- Clever multi-zone chains that look like cascading accidents rather than deliberate sabotage are the path to low PD on this map

---

## Simulation Controls

- Pause
- 1x normal speed
- Fast-forward up to 64x
- Working Day Timer visible throughout — shift ends when timer reaches zero regardless of trap state

---

## Milestone Tree

| Milestone | Description | Stars |
|-----------|-------------|-------|
| First Incident | Cause your first incident on the Construction Site | 1 |
| Chain Reaction | Trigger a chain reaction of 2 or more | 1 |
| Clean Hands | Complete a shift with PD never exceeding 50% | 1 |
| Animal Instinct | Cause an incident using an animal hazard | 1 |
| Caught the Inspector | Inspector triggers one of your traps | 2 |
| Caught the Foreman | Foreman caught during a shift | 2 |
| Perfect Shift | Achieve 5 stars on the Construction Site | 3 |
| Variety Pack | Use at least 5 different hazard types in one shift | 1 |
| Domino Effect | Trigger a chain reaction of 4 or more | 2 |
| Untouchable | Complete a shift with PD never exceeding 25% and authorities never called | 3 |
| Environment Specialist | Cause an incident using a Construction Site specific hazard | 2 |
| Prehistoric Problem | Cause an incident using a dinosaur hazard | 1 |
| Wrong Place Wrong Time | Catch Inspector AND Foreman in the same shift | 3 |
| Style Points | Trigger the Style/Irony Bonus on the Construction Site | 1 |
| Clean Slate | Complete a shift with zero persistent traps remaining | 2 |

**Total milestone stars available: 26**

---

## Cross-References

| Topic | Document |
|-------|----------|
| Full hazard list | HazardInheritanceSystem.md |
| Master hazard reference | MasterHazards.md |
| Worker archetypes | WorkerArchetypes.md |
| Manager/Foreman behavior | ManagerBehavior.md |
| Level variants | LevelVariants.md |
| Scoring and star ratings | ProgressionAndScoring_FINAL.md |
| Shift structure and persistent traps | ShiftAndLevelStructure.md |
| All planned workplaces | PlannedWorkplaces.md |

---

## Conflicts Resolved From Prior Draft (Grok)

| Element | Resolution |
|---------|-----------|
| Worker count 60–100 | Replaced with variable crew size system (5–8 / 10–15 / 20+) |
| Contract Objectives | Removed — sandbox design, no prescribed goals |
| Unlock sequence (after Restaurant and Factory) | Removed — all workplaces available from start |
| Skyscraper/Demolition/Luxury variants as sub-levels | Reclassified — these are independent workplaces in PlannedWorkplaces.md |
| Difficulty rating (High) | Removed — no difficulty rating system confirmed |
| Flavor text and tone descriptions | Kept and integrated into Overview section |
| Outdoor/indoor hybrid site description | Kept |

---

*This document is the canonical Construction Site reference. The files previously located at Game-Mechanics/Locations/Construction_Site.md and Levels-and-Content/Construction_Site.md have been consolidated here. Both originals can be discarded.*
