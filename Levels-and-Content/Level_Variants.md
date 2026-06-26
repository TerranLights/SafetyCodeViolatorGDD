# Level Variants

**Safety Code Violator GDD**
*Modifiers that change the conditions of any level without changing the underlying map. Variants can stack with each other, creating wildly different experiences on the same environment.*

---

## Design Philosophy

Level variants are the primary source of replay value, especially in the demo/free version where only the Construction Site is available. A player should be able to run the same map a dozen times and have it feel meaningfully different each time.

Variants operate as modifiers layered on top of the base level. Most variants can be combined — "Night Shift + Thunderstorm + Skeleton Crew" is a fundamentally different experience to "Day Shift + Overcrowded + VIP Visit" on the exact same map.

---

## TIME OF DAY

| Variant | Description | Gameplay Effect |
|---------|-------------|-----------------|
| Day Shift | Standard. Well-lit, full crew, normal conditions | Baseline — no modifiers |
| Early Morning | Workers have just arrived, half-asleep | Slower reactions, more coffee-related incidents, workers take longer to notice hazards |
| Night Shift | Reduced lighting, skeleton crew | Visibility reduced for workers AND inspector. Different worker routes. Eerie atmosphere |
| Overtime | Workers exhausted, end of a long shift | More natural accidents occur without player input, workers have shorter fuses, more erratic movement |

---

## WEATHER

| Variant | Description | Gameplay Effect |
|---------|-------------|-----------------|
| Clear Day | Standard. No weather effects | Baseline — no modifiers |
| Rain | Steady rainfall across the site | All surfaces slippery, electrical hazards more dangerous, visibility slightly reduced, inspector moves more carefully |
| Heatwave | Extreme heat, sun beating down | Workers distracted, take more frequent breaks, pass out near heat sources, congregate near water — which may contain things |
| Fog | Dense fog across the entire site | Map-wide visibility reduction. Inspector has much harder time spotting obvious traps. Workers walk into things they'd normally avoid |
| Thunderstorm | Heavy rain plus lightning | Lightning strikes as random wildcard hazard, wind affects falling objects and their trajectories, inspector seeks shelter periodically |
| Snow / Ice | Winter conditions | Extremely slippery surfaces everywhere, forklifts much harder to control, workers bundled up and less agile, pipes burst randomly |

---

## CREW COMPOSITION

| Variant | Description | Gameplay Effect |
|---------|-------------|-----------------|
| Skeleton Crew | 5–8 workers | Harder to cause chain reactions but easier to track individuals. Each worker feels more valuable |
| Standard Crew | 10–15 workers | Baseline |
| Full Crew | 20+ workers | Maximum chaos potential. Inspector becomes overwhelmed trying to respond to multiple incidents |
| First Day on the Job | All-new workers dominate the crew | Extremely oblivious archetype behavior across the board. Walk into everything. Cannot find the bathroom |
| Safety-Conscious Crew | Paranoid archetypes dominate | Much harder to catch anyone. Workers actively avoid suspicious areas. Requires more subtle trap placement |
| Mixed Veterans and Rookies | Half experienced, half brand new | Veterans help rookies navigate hazards, creating Hero-style chains where the veteran also gets caught |

---

## SPECIAL CONDITIONS

| Variant | Description | Gameplay Effect |
|---------|-------------|-----------------|
| Inspection Day | Official safety inspection already scheduled | Inspector on site from the very start of simulation. PD meter begins partially full. Maximum difficulty |
| Union Break | Scheduled break at a specific time | All workers congregate in one location at a known moment — enormous trap opportunity if you plan around it |
| Delivery Day | Multiple trucks arriving throughout simulation | Extra vehicles, extra materials, extra chaos potential in the perimeter zone. More falling object opportunities |
| Equipment Malfunction Day | Pre-existing failures on site | Some environmental hazards already active before setup begins. Player works with/around existing chaos |
| Budget Cuts | Management has slashed safety spending | Half the standard safety equipment already missing before you do anything. Lower baseline PD for obvious traps |
| VIP Visit | Executive, investor, or health and safety bureaucrat touring the site | Special high-value target walks through at a specific time. Worth significant bonus points. Heavily guarded by nervous foreman |
| Photo Shoot | Marketing team on site for promotional photos | Camera crew in the way, workers performing for cameras, photographer keeps wandering into dangerous zones obliviously |

---

## WILDCARD / SUPERNATURAL

| Variant | Description | Gameplay Effect |
|---------|-------------|-----------------|
| Dinosaur Migration | Prehistoric animals passing through | Dinosaurs wander randomly across the map regardless of trap placement. Unpredictable chaos added on top of your own |
| Haunted Shift | Former workers who died in "accidents" have returned | Ghosts appear and spook workers into traps. Can be placed during setup as low-suspicion hazards. Inspector cannot interact with ghosts. Safety report flatly notes "worker startled by apparition" |
| Extreme Budget Cuts | Catastrophic management decisions | Structural elements of the map are visibly failing before setup even begins. Workers aware something is wrong but continue anyway |
| Cursed Site | Something was built on something it shouldn't have been | Random supernatural events occur throughout simulation independent of player traps. Combines well with Haunted Shift |

---

## STACKING EXAMPLES

*To illustrate how variants combine:*

**"The Perfect Storm"**
Night Shift + Thunderstorm + Full Crew
- Massive workforce, zero visibility, lightning adding random chaos, inspector stumbling around in the dark. Pure mayhem.

**"The Hardest Run"**
Inspection Day + Safety-Conscious Crew + Clear Day
- Inspector present from minute one, workers actively avoiding your traps, nowhere to hide obvious hazards. Requires extremely subtle, layered setup.

**"The Funniest Run"**
Haunted Shift + First Day on the Job + Dinosaur Migration
- Brand new workers being spooked by ghosts into dinosaurs they didn't know were there. The safety report writes itself.

**"The Strategic Run"**
Union Break + VIP Visit + Delivery Day
- Three timed events to plan around. Workers congregate at break time, VIP arrives mid-simulation, delivery trucks create perimeter chaos throughout. Rewards careful pre-planning.

---

## GHOST / HAUNTED SHIFT — EXPANDED NOTES

*Given the creative potential, ghosts warrant their own section.*

Ghosts are the spirits of former workers who died in workplace "accidents" on this very site. They appear during the Haunted Shift variant and behave as follows:

- Ghosts can be **placed during setup** like regular traps, positioned near ladders, edges, machinery, or other workers
- Once placed, ghosts appear during simulation and **spook nearby workers** — causing panic movement toward whatever hazard is closest
- Ghosts have **Low suspicion** by default. How do you prove a ghost was intentional?
- The Safety Inspector **cannot interact with ghosts** and cannot disable them — ghosts are immune to inspector intervention
- Ghosts can **interact with animals** — a ghost spooking a gorilla that is already on the scaffolding is a chain reaction nobody planned for
- Worker archetypes react differently: The Paranoid One flees at maximum speed (very useful), The Oblivious One doesn't notice until it's too late (also useful, differently)
- The safety report at end of level notes all ghost-related incidents with complete clinical neutrality

**Ghost Types (TBD — to be expanded):**
- Standard ghost — spooks nearby workers
- Poltergeist — throws objects, can trigger falling hazards directly
- Phantom foreman — workers follow its instructions, which are bad instructions
- The Whistler — makes a sound that draws workers toward it from across the map

---

## NOTES FOR SOLO DEV IMPLEMENTATION

Variants are designed to be implemented incrementally:
- Time of Day and Weather variants are primarily visual/audio changes with simple stat modifiers — lowest implementation cost
- Crew Composition variants only require adjusting worker spawn counts and archetype ratios — also low cost
- Special Conditions variants require specific scripted events (VIP spawn, union break timer) — medium cost
- Wildcard/Supernatural variants require the most unique logic but are the highest replay value — implement last

*This is a living document. New variants will be added as development progresses.*
