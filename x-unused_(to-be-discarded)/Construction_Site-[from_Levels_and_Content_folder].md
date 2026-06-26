# Construction Site — Level Design Document

**Safety Code Violator GDD**
*First environment. Demo/free version. Serves as the template for all subsequent workplaces.*

---

## Overview

A mid-sized urban construction site building a commercial tower. Multiple distinct zones connected by pathways workers travel throughout their shift. The player sets up traps during the Setup Phase while workers are frozen, then watches chaos unfold during the Simulation Phase.

**Tone:** Deadpan cartoon slapstick. Absurd hazards presented completely straight.

---

## Zones

### 1. Perimeter / Entrance
*Where the inspector spawns. Workers and deliveries enter and exit here.*

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
*On-site headquarters. A beat-up portable office trailer parked on the edge of the ground level. Where the foreman runs things from, where paperwork gets done, and where workers go to check in, get yelled at, or grab lunch.*

**Worker Activities:**
- Checking in with the foreman
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

**Strategic Note:** The foreman is a special worker type — potentially harder to catch than regular workers or worth bonus points. The trailer is also a natural gathering point, meaning a single well-placed trap can catch multiple workers at once.

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

Variable crew size depending on level. Workers have named personality archetypes that affect movement and hazard reactions.

**Confirmed Archetypes (full list TBD):**

| Archetype | Behavior |
|-----------|----------|
| The Oblivious One | Walks straight into obvious traps without hesitation |
| The Paranoid One | Avoids suspicious areas, harder to catch |
| The Clumsy One | Occasionally triggers traps accidentally on their own |
| The Hero | Rushes to help injured coworkers — and often triggers the same trap |

---

## The Safety Inspector

Spawns at the Perimeter/Entrance when the Plausible Deniability meter maxes out.

**Behavior:**
- Patrols randomly across the site
- Gets pulled toward the location of the most recent accident
- Can trigger traps themselves (intentional — very funny)
- Disables active traps they encounter
- Does NOT hard-fail the level — simulation winds down naturally as traps are cleared

---

## Plausible Deniability Meter

- Fills as accidents occur during simulation
- Low-suspicion traps contribute less PD per accident
- High-suspicion traps contribute more PD per accident
- Clever chain reactions involving multiple low-suspicion traps are rewarded with lower PD gain
- Maxing the meter triggers inspector arrival
- PD level at end of simulation affects final score/rating

---

## Simulation Controls

Player can adjust simulation speed during the Simulation Phase:
- Pause
- 1x (normal)
- Fast-forward (speed TBD)

---

---

## What This Document Still Needs

- [ ] Worker archetypes — full list beyond the four confirmed (TBD in separate session)
- [ ] Level variants — different crew sizes, time of day, weather conditions
- [ ] Scoring breakdown — how exactly PD level translates to end rating
- [ ] Zone interconnections — specific pathways and triggers between zones
- [ ] Foreman as special worker type — behavior and stats
- [ ] Audio/visual notes for construction site specific gags

*Zones complete. Document actively expanding.*
