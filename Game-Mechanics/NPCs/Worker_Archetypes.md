# Worker Archetypes & AI Behavior

**Safety Code Violator GDD**
*Full roster of worker personality types plus core AI behavior systems. Each archetype affects movement, hazard reactions, and interactions with other workers. Mix and match across levels for emergent comedy.*

---

## Design Philosophy

Workers are not just generic NPCs — they are the stars of the chaos. The best archetypes create unscripted comedy just by existing near each other — a Gossip following a Paranoid One who is fleeing a ghost that startled a Clumsy One who accidentally triggered a trap meant for someone else is exactly the kind of moment this game exists to produce.

Every worker incident should feel **personal and funny**, not generic. Players should start recognizing and anticipating specific archetype behaviors across multiple shifts.

Each archetype is defined by three things:
- **How they move** around the map normally
- **How they react** when something goes wrong nearby
- **How they interact** with other worker archetypes

Implementation note: Not all archetypes need to be in v1. This is the full intended roster. Prioritize during development based on complexity and comedic value.

---

## Core Worker Attributes

Every worker has the following base attributes regardless of archetype:

| Attribute | Description |
|-----------|-------------|
| **Archetype** | Primary personality type from roster below. Defines movement, reaction, and interaction behavior |
| **Job Role** | Workplace-flavored role label (e.g. Intern, Crane Operator, Sous Chef). Cosmetic but affects daily routine |
| **Suspicion Sensitivity** | How quickly this worker notices sabotage. Varies by archetype — Paranoid One is highest, Oblivious One is lowest |
| **Daily Routine** | Preset sequence of activities this worker follows during a shift — see Daily Routines section below |

*Note: A health/resilience system has not been confirmed for v1. To be decided during implementation phase.*

---

## Daily Routines

Workers follow **daily routines** rather than wandering randomly. Each routine is a loose sequence of activities tied to their job role and the time of the in-game working day. This makes worker movement somewhat predictable — a strategic tool for the player.

**Example routine — Office Worker:**
Arrive → Sign in → Go to desk → Coffee break (break room) → Meeting → Back to desk → Lunch (break room) → Back to desk → Afternoon coffee → Depart

**Example routine — Construction Labourer:**
Arrive → Sign in → Collect equipment → Ground level work → Break (site trailer) → Scaffolding work → Lunch (site trailer) → Ground level work → Depart

Routines are influenced by:
- Worker archetype (Slacker deviates toward breaks, Overachiever skips them)
- Time of day within the shift
- Events — a nearby incident interrupts routine and triggers hazard reaction behavior
- Manager instructions — workers follow the Manager's directions, overriding routine temporarily

---

## Fix-It Behavior

Workers will attempt to "fix" or investigate things that look wrong — a sabotaged piece of equipment, an unusual sound, a coworker acting strangely. This is both a threat and an opportunity.

**How it works:**
- A worker notices something suspicious (based on their Suspicion Sensitivity)
- They approach and attempt to interact with it
- If the trap is triggered during their fix attempt, they catch the full effect
- If they successfully "fix" it before it triggers, the trap is disabled for this shift

**Archetype modifiers:**
- Paranoid One — notices quickly, does NOT attempt to fix. Alerts others instead
- Health and Safety Rep — notices and actively attempts to fix. High risk to your setup
- Oblivious One — never notices. Ever
- Daredevil — notices and approaches but doesn't fix. Just wants a closer look
- Investigator — always investigates suspicious things. Most reliable fix-it worker

**Strategic implication:** A worker attempting to fix a trap is a tense moment — if you've placed a trigger nearby, their investigation can itself set off the trap. The coffee machine fix attempt is the classic example: a worker trying to fix the tampered machine right before it explodes is one of the most reliable and funniest moments in the game.

---

## Highlight System

The game automatically detects and records notable moments involving specific workers during simulation. These feed into the debrief screen's "Top 5 Moments" section.

**What triggers a highlight:**
- A worker triggering a trap in an unexpected way
- A worker surviving something they shouldn't have
- A worker attempting to fix something and making it worse
- Chain reactions that pass through multiple named archetypes in sequence
- The same worker having multiple incidents in one shift
- A worker triggering a trap that was meant for someone else entirely

**Debrief display:**
Highlights are shown with brief descriptive captions in the game's corporate deadpan tone:
- "The Health and Safety Rep attempted to address the coffee machine situation. They did not succeed."
- "The Oblivious One walked past the crocodile moat four times before the fifth visit proved decisive."
- "The Hero rushed to assist a colleague. This was their second attempt at this today."

---

## REACTIVE ARCHETYPES
*Defined primarily by how they respond to danger*

| Archetype | Movement | Hazard Reaction | Interaction with Others |
|-----------|----------|-----------------|------------------------|
| **The Screamer** | Normal | Screams loudly, drawing ALL nearby workers toward the incident | Massive chain reaction amplifier — their panic response pulls others into the same hazard |
| **The Denier** | Normal | Refuses to believe anything is wrong. Returns to hazard zones after near misses | Warns others to stop overreacting, sometimes dragging them back into danger |
| **The Freezer** | Normal | Locks up completely. Stands perfectly still in the worst possible spot | Other workers trip over or run into them while fleeing |
| **The Runner** | Normal | Sprints away from danger at full speed | Almost always runs directly into something worse. Interacts badly with The Screamer |
| **The Investigator** | Curious, wanders toward unusual things | Actively approaches hazards to get a closer look | Leads other curious workers toward danger. Pairs lethally with The Crowd Follower. High fix-it behavior |

---

## SOCIAL ARCHETYPES
*Defined primarily by how they interact with other workers*

| Archetype | Movement | Hazard Reaction | Interaction with Others |
|-----------|----------|-----------------|------------------------|
| **The Hero** | Normal | Rushes toward injured coworkers to help | Almost always triggers the same trap as the person they're rescuing. The most reliable chain reaction archetype |
| **The Gossip** | Follows other workers constantly | Panics and spreads misinformation about what happened | Always nearby when something goes wrong. Ensures clusters of workers near trap zones |
| **The Loner** | Stays away from other workers, predictable solo routes | Quietly removes themselves from danger without alerting others | Hard to catch in group traps but isolated routes make them targetable individually |
| **The Supervisor** | Rarely moves far from their station | Sends other workers into dangerous areas on their behalf | Never goes anywhere themselves. Catch them by trapping their station or the workers they send |
| **The Crowd Follower** | Goes wherever the majority of workers are | Panics in whatever direction the crowd panics | Extremely useful for funneling large groups. If you catch one crowd, you catch them all |

---

## PERSONALITY ARCHETYPES
*Defined by general day-to-day behavior*

| Archetype | Movement | Hazard Reaction | Interaction with Others |
|-----------|----------|-----------------|------------------------|
| **The Oblivious One** | Walks in straight lines regardless of what's ahead | Doesn't notice until it's too late | Does not warn others. Does not react to others' panic. Just keeps walking. Zero fix-it behavior |
| **The Paranoid One** | Actively avoids suspicious-looking areas | Flees at first sign of anything unusual | Warns nearby workers, can inadvertently save others from your traps. High suspicion sensitivity. Does not fix — alerts |
| **The Clumsy One** | Bumps into things, takes irregular paths | Trips while fleeing, often making things worse | Accidentally triggers traps meant for others. Unreliable in the best way |
| **The Veteran** | Slow, deliberate, efficient routes | Complacent near familiar hazards, cautious near new ones | Experienced enough to spot obvious traps but overconfident around equipment they've used for years |
| **The New Hire** | Wanders, gets lost, enters restricted areas | Panics immediately at anything unusual | Has no idea where they are. Walks into places they shouldn't be. Extremely oblivious near equipment |
| **The Overachiever** | Moves faster than all other workers, covers maximum ground | Panics efficiently — gets out fast | Hits more traps per simulation simply due to covering more of the map. Skips breaks, deviates from routine |
| **The Slacker** | Barely moves. Spends most of simulation in one spot | Minimal reaction — too tired to panic properly | Requires traps to come to them. Deviates toward break areas constantly |
| **The Phone Addict** | Walks slowly, head down, completely distracted | Looks up briefly, looks back down, keeps walking into it | Does not react to other workers' warnings. Completely unreachable by social archetypes. Zero fix-it behavior |
| **The Health and Safety Rep** | Patrols methodically, notices environmental details | Calmly moves away from danger, warns others professionally | Essentially a mini-inspector. Highest fix-it behavior of all archetypes. Notices and actively disables obvious traps. Worth significant points if caught |
| **The Lunch Guy** | Beelines toward any food source | Abandons all survival instinct if food is involved | Follows food-related lures without hesitation. Immune to other social influences while food is present. Routine heavily deviates toward break room |
| **The Foreman** | Stays near their designated area, periodic walkthroughs | Retreats to safe location when danger detected | Special archetype — full behavior documented in Manager_Behavior.md |

---

## WILDCARD ARCHETYPES
*Defined by unusual or unpredictable behavior*

| Archetype | Movement | Hazard Reaction | Interaction with Others |
|-----------|----------|-----------------|------------------------|
| **The Daredevil** | Actively seeks out dangerous-looking situations | Excited rather than afraid. Approaches hazards on purpose | Encourages other workers to "come look at this" near active traps. Investigates but doesn't fix |
| **The Unlucky One** | Normal | Triggers traps even when they logically shouldn't be able to. Probability bends around them | Accidents happen near them regardless of planning. A gift and a wildcard |
| **The Lucky One** | Normal | Somehow avoids everything through improbable fortune | Extremely satisfying when finally caught. The game's ultimate challenge target |
| **The Conspiracy Theorist** | Follows the trail of recent incidents around the map | Convinced something is wrong, investigates actively | Draws entirely wrong conclusions. Warns workers about the wrong hazards. Accidentally useful |
| **The Sleepwalker** | Completely random movement, ignores all obstacles | Does not react. Continues sleepwalking | Total wildcard. Can stumble into traps, through traps, past animals, and off scaffolding entirely by accident |

---

## ARCHETYPE INTERACTIONS — NOTABLE COMBINATIONS

Some archetypes create especially reliable or funny emergent situations when placed together:

| Combination | What Happens |
|-------------|--------------|
| Screamer + Crowd Follower | One incident pulls the entire crew toward it |
| Hero + any injured worker | Hero rushes in, triggers same trap, second Hero rushes in |
| Gossip + Paranoid One | Gossip follows Paranoid One who is actively fleeing, dragging Gossip into danger |
| Daredevil + Investigator | Both approach the hazard simultaneously, competing to get closer |
| Supervisor + New Hire | Supervisor sends New Hire somewhere dangerous, stays safe themselves — until you trap the station |
| Phone Addict + any trap | Reliable. Every time |
| Lucky One + Unlucky One | Place them near the same trap and let probability argue with itself |
| Sleepwalker + animals | Sleepwalker wanders through an animal hazard without waking up. Animal follows, confused |
| Foreman + Crowd Follower | Foreman directs workers somewhere. Crowd Followers bring everyone else along |
| Health and Safety Rep + Daredevil | Rep tries to stop Daredevil. Both end up in the hazard |
| Health and Safety Rep + tampered equipment | Rep attempts to fix it. Timing determines outcome. Always funny |
| Denier + any recurring hazard | Walks back into the same hazard zone after a near miss. Every time |
| Conspiracy Theorist + Paranoid One | Both convinced something is wrong. Both wrong about what it is. Inspector responds to their reports |

---

## THE FOREMAN / MANAGER — SPECIAL ARCHETYPE

The Foreman (Construction Site) / Manager (all other workplaces) is the most mechanically significant worker on any site. Full behavior, escalation system, retreat behavior, backup group, and authority equivalent per workplace are documented in **Manager_Behavior.md**.

Summary:
- Stays near designated safe location by default
- Conducts periodic walkthroughs
- Directs other workers — influencing their routines
- Retreats when they almost get caught
- Triggers three-stage escalation ladder culminating in authorities
- Worth significant bonus points if caught

---

## IMPLEMENTATION PRIORITY NOTES

*For solo dev — suggested implementation order:*

**Phase 1 — Core roster (v1 / demo):**
The Oblivious One, The Paranoid One, The Clumsy One, The Hero, The Screamer, The Runner, The New Hire, The Slacker, The Foreman

**Phase 2 — Full release additions:**
The Veteran, The Overachiever, The Gossip, The Loner, The Crowd Follower, The Phone Addict, The Supervisor, The Freezer, The Investigator, The Daredevil, The Lunch Guy

**Phase 3 — Wildcard/late additions:**
The Unlucky One, The Lucky One, The Conspiracy Theorist, The Sleepwalker, The Health and Safety Rep

**Daily Routines:** Implement in Phase 1 with simplified routines (2-3 activities). Expand in Phase 2.
**Fix-It Behavior:** Implement in Phase 2 — requires archetype detection system to be stable first.
**Highlight System:** Implement in Phase 2 — requires debrief screen infrastructure.

---

## Conflicts Resolved From Prior Draft (Grok)

| Element | Resolution |
|---------|-----------|
| Named specific workers (Kevin, Karen, Chad) | Removed as persistent characters — reclassified as archetype flavor inspiration in individual level documents |
| Health & Resilience as confirmed attribute | Flagged as unconfirmed — noted in Core Worker Attributes as TBD for implementation phase |
| "Later levels: distinct characters with backstories" | Removed — conflicts with archetype system and all-workplaces-available-from-start design |
| "Special Problem Employees" | Absorbed into Manager/special archetype system and Health and Safety Rep |
| "Early levels: generic workers" | Removed — conflicts with all workplaces available from start |
| Daily routines concept | Kept and expanded into full section |
| Fix-it behavior | Kept and expanded into full section |
| Highlight system | Kept and integrated with debrief screen documentation |
| Suspicion sensitivity as per-worker attribute | Kept and added to Core Worker Attributes table |
| Chain reactions feel alive through worker influence | Kept as design philosophy language |

---

*This is a living document. New archetypes may be added as additional workplace environments are designed. Cross-reference Manager_Behavior.md for full Manager/Foreman behavior system.*
