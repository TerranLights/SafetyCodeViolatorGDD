# Worker Archetypes

**Safety Code Violator GDD**
*Full roster of worker personality types. Each archetype affects movement, hazard reactions, and interactions with other workers. Mix and match across levels for emergent comedy.*

---

## Design Philosophy

Archetypes are the soul of the simulation. The best archetypes create unscripted comedy just by existing near each other — a Gossip following a Paranoid One who is fleeing a ghost that startled a Clumsy One who accidentally triggered a trap meant for someone else is exactly the kind of moment this game exists to produce.

Each archetype is defined by three things:
- **How they move** around the map normally
- **How they react** when something goes wrong nearby
- **How they interact** with other worker archetypes

Implementation note: Not all archetypes need to be in v1. This is the full intended roster. Prioritize during development based on complexity and comedic value.

---

## REACTIVE ARCHETYPES
*Defined primarily by how they respond to danger*

| Archetype | Movement | Hazard Reaction | Interaction with Others |
|-----------|----------|-----------------|------------------------|
| **The Screamer** | Normal | Screams loudly, drawing ALL nearby workers toward the incident | Massive chain reaction amplifier — their panic response pulls others into the same hazard |
| **The Denier** | Normal | Refuses to believe anything is wrong. Returns to hazard zones after near misses | Warns others to stop overreacting, sometimes dragging them back into danger |
| **The Freezer** | Normal | Locks up completely. Stands perfectly still in the worst possible spot | Other workers trip over or run into them while fleeing |
| **The Runner** | Normal | Sprints away from danger at full speed | Almost always runs directly into something worse. Interacts badly with The Screamer |
| **The Investigator** | Curious, wanders toward unusual things | Actively approaches hazards to get a closer look | Leads other curious workers toward danger. Pairs lethally with The Crowd Follower |

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
| **The Oblivious One** | Walks in straight lines regardless of what's ahead | Doesn't notice until it's too late | Does not warn others. Does not react to others' panic. Just keeps walking |
| **The Paranoid One** | Actively avoids suspicious-looking areas | Flees at first sign of anything unusual | Warns nearby workers, can inadvertently save others from your traps |
| **The Clumsy One** | Bumps into things, takes irregular paths | Trips while fleeing, often making things worse | Accidentally triggers traps meant for others. Unreliable in the best way |
| **The Veteran** | Slow, deliberate, efficient routes | Complacent near familiar hazards, cautious near new ones | Experienced enough to spot obvious traps but overconfident around equipment they've used for years |
| **The New Hire** | Wanders, gets lost, enters restricted areas | Panics immediately at anything unusual | Has no idea where they are. Walks into places they shouldn't be. Extremely oblivious near equipment |
| **The Overachiever** | Moves faster than all other workers, covers maximum ground | Panics efficiently — gets out fast | Hits more traps per simulation simply due to covering more of the map |
| **The Slacker** | Barely moves. Spends most of simulation in one spot | Minimal reaction — too tired to panic properly | Requires traps to come to them. Very easy to plan around once you know their spot |
| **The Phone Addict** | Walks slowly, head down, completely distracted | Looks up briefly, looks back down, keeps walking into it | Does not react to other workers' warnings. Completely unreachable by social archetypes |
| **The Health and Safety Rep** | Patrols methodically, notices environmental details | Calmly moves away from danger, warns others professionally | Essentially a mini-inspector. Notices and avoids obvious traps. Tries to warn coworkers. Worth significant points if caught |
| **The Lunch Guy** | Beelines toward any food source | Abandons all survival instinct if food is involved | Follows food-related lures without hesitation. Immune to other social influences while food is present |
| **The Foreman** | Stays near the Site Trailer, occasional site walkthroughs | Retreats to trailer when danger detected | Special archetype. Other workers follow their instructions. Worth bonus points. Directs workers into or away from hazard zones |

---

## WILDCARD ARCHETYPES
*Defined by unusual or unpredictable behavior*

| Archetype | Movement | Hazard Reaction | Interaction with Others |
|-----------|----------|-----------------|------------------------|
| **The Daredevil** | Actively seeks out dangerous-looking situations | Excited rather than afraid. Approaches hazards on purpose | Encourages other workers to "come look at this" near active traps |
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

---

## THE FOREMAN — SPECIAL ARCHETYPE NOTES

The Foreman is the most mechanically significant worker on the site:

- Stays near the **Site Trailer** by default
- Periodically conducts **site walkthroughs** on a fixed route
- Other workers **follow instructions** from the Foreman — meaning trapping the Foreman's walkthrough route is high value
- Worth **significant bonus points** when caught
- **Retreat behavior** — returns to trailer when danger is detected nearby, making them harder to catch later in simulation
- If the Foreman is caught early, workers lose their instruction source and behavior becomes more erratic — a double reward

---

## IMPLEMENTATION PRIORITY NOTES

*For solo dev — suggested implementation order:*

**Phase 1 — Core roster (v1 / demo):**
The Oblivious One, The Paranoid One, The Clumsy One, The Hero, The Screamer, The Runner, The New Hire, The Slacker, The Foreman

**Phase 2 — Full release additions:**
The Veteran, The Overachiever, The Gossip, The Loner, The Crowd Follower, The Phone Addict, The Supervisor, The Freezer, The Investigator, The Daredevil, The Lunch Guy

**Phase 3 — Wildcard/late additions:**
The Unlucky One, The Lucky One, The Conspiracy Theorist, The Sleepwalker, The Health and Safety Rep

---

*This is a living document. New archetypes may be added as additional workplace environments are designed.*
