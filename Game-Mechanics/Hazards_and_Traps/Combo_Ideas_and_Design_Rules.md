# Combo Ideas & Hazard Design Rules — Safety Code Violator

**Safety Code Violator GDD**
*Documents high-value hazard combinations, chain reaction design targets, and core hazard design rules. Use this as a creative reference during level design and hazard implementation.*

---

## Design Philosophy

Combos are the heart of the game's "I can't believe that worked" moments. The best combos feel like they were discovered rather than prescribed — the player experiments, something unexpected happens, and they immediately want to recreate it.

This document serves two purposes:
1. **Design targets** — combos the game should be capable of producing, used to validate that the hazard and physics systems work correctly
2. **Player inspiration** — the debrief screen and tutorial hints can reference these to teach players what's possible without prescribing exactly how to do it

**Core combo design principle:** The best traps are combinations of 3+ smaller ones. A grand piano falling on someone is funny once. A grand piano falling because a clumsy worker bumped into a ladder that knocked over a filing cabinet that fell onto the crane controls is funny every time and scores dramatically better.

---

## Combo Scoring Bonuses

These map directly onto the scoring axes in ProgressionAndScoring_FINAL.md:

| Bonus Type | What Triggers It | Scoring Axis |
|------------|-----------------|-------------|
| **Length Bonus** | More hazards in one unbroken chain | Chain Reaction Length |
| **Thematic Bonus** | Incident matches location or worker archetype ironically | Style / Irony Bonus |
| **Plausibility Bonus** | Chain looks extremely believable as a genuine accident | PD Rating |
| **Creativity Bonus** | Rarely combined hazard types used together | Creativity Bonus |
| **Variety Bonus** | Multiple hazard categories involved in one chain | Variety Bonus |
| **Animal Bonus** | Animal hazard involved at any point in chain | Creativity Bonus |
| **Inspector/Manager Bonus** | Inspector or Manager caught as part of chain | Inspector/Manager Outcome |

The highest-scoring runs combine all of these — a long, believable, creative, varied chain that ends with the Inspector triggering the last trap while investigating.

---

## Hazard Design Rules

Every hazard in the game must satisfy these rules. Use when designing new hazards or evaluating whether a proposed hazard fits the game.

**Rule 1 — Every hazard must have a believable corporate excuse**
No hazard should be obviously and inexplicably malicious on its own. Even a crocodile moat needs a corporate justification ("site management opted for unconventional perimeter security"). The humor comes from the deadpan presentation, not from the hazard winking at the camera.

**Rule 2 — Stronger hazards have higher suspicion**
High-impact hazards contribute more to the PD meter. This is the core tension — the most satisfying hazards are also the riskiest to use. Subtlety is rewarded. Full tier system in HazardInheritanceSystem.md.

**Rule 3 — The best traps are combinations of 3+ smaller ones**
A single High Suspicion hazard is risky and scores moderately. Three Low Suspicion hazards that chain together score better, contribute less PD, and are more satisfying. The system should always reward layered thinking over brute force.

**Rule 4 — Visual and audio feedback must be extremely satisfying**
Every hazard trigger needs a distinct, punchy audio-visual moment. Chain reactions should feel like they're building — each link audibly and visually distinct from the last. The debrief highlight reel exists specifically to replay the best moments. If a hazard triggering doesn't feel satisfying in isolation, it won't feel satisfying in a chain.

**Rule 5 — Every hazard must have a clear armed/triggered visual state**
Players need to know at a glance whether their traps are still active. Full visual state requirements in Art_Bible_FINAL.md.

**Rule 6 — Animals follow their own logic**
Animal hazards are active rather than passive — they move semi-randomly and can trigger other traps, interfere with the inspector, and create emergent chain reactions the player didn't plan. This is a feature. Design animal placement around probability rather than certainty.

**Rule 7 — Archetype interactions are part of the hazard design**
A trap placed near a Screamer is a different trap than the same one placed near an Oblivious One. Hazard design should consider which archetypes interact with it most interestingly. The best hazard placements exploit specific archetype behaviors.

---

## COMBO EXAMPLES

*These are design targets — combinations the game should be capable of producing. Not prescribed sequences, but demonstrations of what the systems enable.*

---

### UNIVERSAL COMBOS
*Work across multiple environments*

**The Classic Chain**
Scorpions in work boots → worker panics → runs into forklift/heavy equipment → equipment hits chemical barrel → barrel ignites near suspended load → load drops onto safety fencing → workers fall into whatever is below
*Notes: Low suspicion throughout. Long chain. Excellent PD score.*

**The Hero Problem**
Any incident → Hero archetype rushes to help → triggers same trap → second Hero rushes to help first Hero → also triggers same trap
*Notes: Requires Hero archetype in crew. Self-sustaining chain. Deeply funny. Medium suspicion.*

**The Fog Machine Play**
Fog machine (visibility zero) → workers walk blindly into multiple hazards simultaneously → Screamer triggers panic in unknown direction → Crowd Followers pile toward the sound → into whatever is there
*Notes: Fog machine is the setup for everything else. Medium suspicion on fog itself. High chaos potential.*

**The Inspector Trap**
PD meter fills → inspector spawns → inspector walks toward most recent incident → incident was near a rigged ladder/greased floor/spring tile → inspector triggers it → bonus points, inspector neutralized
*Notes: Requires planning the incident location to funnel the inspector. High skill ceiling.*

**The Manager Decoy**
Trigger small incident on opposite side of map from best remaining traps → Manager investigates decoy → backup group follows → while they're investigating, main traps activate on unguarded side
*Notes: Requires understanding Manager patrol routes. High strategy, high reward.*

**The Animal Cascade**
Release animal hazard → animal wanders into environmental trap → trap triggers, sending object toward workers → Screamer reacts → Crowd Followers pile toward Screamer → into second animal hazard
*Notes: Animals are unpredictable. This combo has variance but when it works it's spectacular.*

**The Paranoid One Paradox**
Paranoid One notices suspicious area and warns others → other workers avoid that zone → Paranoid One's alternate route takes them through a different trap → Paranoid One triggers it while avoiding the first one
*Notes: Requires knowing the Paranoid One's avoidance behavior. Low suspicion, high irony bonus.*

---

### CONSTRUCTION SITE COMBOS

**Vertical Doom**
Loosened ladder rungs → worker falls from scaffolding → lands on crane load safety pin → suspended load drops → load swings and hits scaffolding section → entire scaffolding section collapses onto ground level workers
*Notes: Three-zone chain. Maximum vertical chain reaction potential.*

**The Pterodactyl Problem**
Workers reach top floor → Pterodactyl nest disturbed → Pterodactyl panics workers → panicking worker backs into greased railing → falls onto crane → crane goes full spin mode → Gorilla on scaffolding now also involved somehow
*Notes: Once the pterodactyl is involved, outcomes are unpredictable. This is correct.*

**Ground Level Cascade**
Tampered forklift steering → forklift veers into chemical barrel stack → barrels ignite near welding sparks → fire spreads to crane fuel line → crane operator abandons crane mid-operation → unsecured load drops → foundation pit fencing removed → workers retreat directly into pit → crocodiles were already in the pit
*Notes: Eight-link chain. All Low-Medium suspicion. Exceptional score potential.*

**The Foreman Retirement**
Rigged coffee maker in trailer (Low) → overloaded power strip (Low) → gas leak near microwave (Medium) → Foreman enters trailer for scheduled break → coffee maker electrocutes → power strip ignites → microwave spark ignites gas → trailer tips off supports (High but everything else already triggered) → Foreman caught
*Notes: Front-loaded with Low suspicion traps. High suspicion only at final trigger when it matters least for PD.*

---

### OFFICE COMBOS

**The Productivity Improvement**
Wet floor near entrance → worker slips → slides into open-plan workspace → knocks over filing cabinet → filing cabinet hits overloaded power strip → electrical fire → sprinkler system activates (water + electrical = secondary hazard) → all remaining workers slip on wet floor → Phone Addict still hasn't looked up
*Notes: Classic escalating chain. All Low-Medium suspicion. Strong thematic fit.*

**The Meeting Room Incident**
Whiteboard marker replaced with solvent → fumes build in soundproofed meeting room → workers become disoriented → Freezer archetype locks up in doorway → prevents evacuation → Screamer in room amplifies panic → allergen concentrate in ventilation activates simultaneously → debrief notes "productivity meeting concluded early"
*Notes: Enclosed space multiplies everything. Soundproofing means inspector responds slowly.*

**The EMP Play**
EMP device in server room (High) → all electronic safety systems fail simultaneously → elevators freeze mid-floor → security doors slam shut → lights out → workers navigate blind → multiple hazards activate in darkness → inspector cannot identify trap locations → PD contribution from subsequent traps reduced
*Notes: EMP is High suspicion but disables inspector effectiveness. Strategic use near full PD meter.*

**Corporate Satire Special**
Annual performance review triggers trapdoor (High) → worker falls → Hero rushes to help → also falls → Health and Safety Rep attempts to cordon off area → walks into motivational poster avalanche → Conspiracy Theorist investigates wrong end of office → finds the velociraptor
*Notes: Maximum archetype interaction. Style/Irony bonus near-certain. Very high suspicion but very high everything else too.*

---

### RESTAURANT / KITCHEN COMBOS

**Grease Inferno**
Deep fryer overflow → grease spreads across kitchen floor → rushing worker slips → falls into commercial mixer → mixer launches contents at open flame → grease fire ignites → kitchen ventilation hood redirects flame → industrial blast chiller nearby activates as emergency response → temperature differential causes condensation → floor now both burning and ice cold
*Notes: Kitchen hazards chain exceptionally well. High visual spectacle.*

**The Health Code Violation**
Rat infestation (Low) → workers scatter → scattered worker knocks over industrial shelving → shelving hits gas line → gas leak near pilot light → explosion → walk-in freezer door jammed on fleeing worker → second worker tries to help → both trapped → bear in the walk-in freezer was already there
*Notes: Bear in the walk-in freezer requires pre-placement. The rat infestation starts everything. Low suspicion opening.*

**The Dumbwaiter Special**
Industrial mixer malfunction → launches contents at worker → worker stumbles into dumbwaiter → dumbwaiter activated → sends worker to wrong floor → wrong floor has its own active hazard → second incident reported from different floor simultaneously → inspector cannot determine which floor to prioritize
*Notes: Multi-floor chains split inspector attention. Strong strategic value.*

---

### HOSPITAL COMBOS

**The MRI Incident**
MRI machine powered beyond limits → pulls all metal objects across room → includes hard hats, tools, instrument trays → workers caught in magnetic pull → defibrillator wall unit activates automatically → runaway hospital bed (metal frame) launches toward MRI → chain of metal objects creates secondary projectile hazard
*Notes: MRI is the linchpin. High suspicion but generates extraordinary chain.*

**The Surgical Robot Upgrade**
Surgical robot software update (High) → operates with great confidence and no accuracy → wrong patient, wrong procedure → hospital bed hydraulics launch occupant → defibrillator misfire on second worker → pneumatic sample transport over-pressured → tubes become rail guns → velociraptor in supply closet decides now is the time
*Notes: Once the surgical robot starts, everything else is secondary chaos.*

---

### SPACE STATION COMBOS

**The Cascade**
Thruster misfire → station rotates unexpectedly → everything not bolted down becomes projectile → food in zero gravity obstructs vision → worker in EVA suit with tampered equipment goes outside → airlock opens wrong direction → attitude thrusters all fire simultaneously → solar panels repositioned toward station → concentrated beam enters through viewport → velociraptor in supply closet is now also in zero gravity
*Notes: Space station chains are inherently spectacular. Every hazard is amplified by zero gravity.*

---

### CROSS-ENVIRONMENT ANIMAL CHAINS

**The Geese Problem**
Angry geese released → workers flee → fleeing workers trigger multiple environmental hazards simultaneously → Screamer among fleeing group → entire crew converges on single point → point has been pre-trapped → inspector arrives → geese have no concept of inspector authority
*Notes: Geese work in literally any environment. Universal chain opener.*

**Dinosaur Migration**
Brachiosaurus enters site (Medium — how do you prove it was intentional) → walks through environmental structures without noticing → structural damage activates dormant traps → panicking workers flee toward velociraptor in supply closet → velociraptor emerges → T-Rex visible through window, cannot fit inside → all of this is on the debrief highlight reel
*Notes: Brachiosaurus as chain initiator is underrated. Medium suspicion, enormous consequences.*

---

## Policy & Workflow Hazards — Future Consideration

*The following hazard category was proposed in early design and is not confirmed for v1. Captured here for future reference.*

"Policy & Workflow" hazards are passive modifiers rather than placed physical objects — invisible changes to how workers behave that make them more vulnerable to physical hazards:

- Removed Safety Training — workers less likely to notice obvious hazards
- Mandatory Overtime — workers more fatigued, slower reactions, more accidents
- Encouraged Multi-Tasking — workers distracted, more erratic movement

These would function more like level modifiers than placed traps, potentially selectable during briefing rather than the setup phase. Implementation would require a separate system from the existing placement mechanics. Worth considering for a post-v1 update as a "management decisions" layer.

---

## Chain Reaction Documentation Format

*When adding new combos to this document, use this format for consistency:*

**[Combo Name]**
Step 1 → Step 2 → Step 3 → Final outcome
*Notes: Suspicion profile, archetype interactions, scoring potential, any special conditions.*

---

*This is a living document. New combos should be added as new environments are designed and as playtesting reveals emergent chains the design team didn't anticipate. The best entries in this document will be ones nobody planned.*

*Cross-reference HazardInheritanceSystem.md for full hazard definitions, WorkerArchetypes_FINAL.md for archetype behavior details, and ProgressionAndScoring_FINAL.md for scoring axis definitions.*
