# Hazard Types & Inheritance System

**Safety Code Violator GDD**
*Organized by hazard for code implementation. Each hazard is a class. Workplace environments inherit from relevant hazard type pools. Environment-specific hazards are unique subclasses.*

---

## Intended Class Architecture (Godot)

```
HazardBase (parent class)
├── UniversalHazard (available to ALL environments)
├── CrossEnvironmentHazard (available to tagged environment groups)
│   ├── IndustrialHazard
│   ├── FoodServiceHazard
│   ├── OfficeCorporateHazard
│   ├── MedicalScienceHazard
│   ├── RetailWarehouseHazard
│   ├── EntertainmentHazard
│   └── ExtremeWildcardHazard
└── EnvironmentSpecificHazard (unique to one setting)
    ├── ConstructionSiteHazard
    ├── OfficeHazard
    ├── RestaurantHazard
    └── [one subclass per environment]
```

### Environment Category Tags

| Tag | Environments |
|-----|-------------|
| **Industrial** | Construction Site, Factory, Shipyard, Oil Rig, Mine/Quarry, Chemical Plant, Nuclear Plant, Logging Site, Demolition Site, Junkyard |
| **FoodService** | Restaurant/Kitchen, Fast Food, Brewery/Distillery, Hotel, Catering Company |
| **OfficeCorporate** | Office Building, Call Center, Bank, Law Firm, Government Building |
| **MedicalScience** | Hospital, Laboratory, Pharmaceutical Plant, Veterinary Clinic |
| **RetailWarehouse** | Retail Store, Warehouse/Fulfillment Center, Supermarket, Car Dealership |
| **Entertainment** | Casino, Carnival/Amusement Park, Sports Stadium, Circus, Movie Studio/Film Set, Zoo |
| **ExtremeWildcard** | Space Station, Submarine, Haunted House, Ski Resort, Funeral Home, Daycare |

---

## TIER 1 — UNIVERSAL HAZARDS
*Available in every environment regardless of setting. The baseline toolkit.*

### Animals — Universal

| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Angry geese | Low | Geese exist everywhere. Nobody respects this |
| Rabid raccoon | Low | Urban and rural. Universally unwelcome |
| Swarm of bees | Medium | Hive can be placed anywhere with a ceiling or overhang |
| Wasp nest | Medium | Hidden in any container, cabinet, or fixture |
| Tarantulas in container | Low | More panic than danger. Panic causes the danger |
| Scorpions in footwear | Low | Delayed trigger. Activates when worn |
| Confused penguin | Low | Causes chaos through pure bewilderment. Origin unexplained |
| Honey badger | Low | Doesn't care. Genuinely doesn't care |
| Pack of angry chihuahuas | Low | Individually ridiculous, collectively devastating |
| Kangaroo | Medium | Chaotic, unpredictable, surprisingly strong |
| Bear | High | Can appear anywhere. Usually from bathroom |
| Gorilla in appropriate uniform | High | Fitting in, trying its best, still dangerous |
| Velociraptor | High | In the supply closet / storage room. Always |
| Dragon | High | We said no realism |

### Animals — Dinosaurs (Universal)

| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Velociraptor | High | Storage room. Every workplace has a storage room |
| Dilophosaurus | High | Spits. Catastrophic near any workspace |
| Pterodactyl | High | Nests on any elevated structure |
| Brachiosaurus | Medium | Not aggressive. Just enormous. Hard to prove intentional |
| Ankylosaurus | High | Living wrecking ball. Tail destroys everything in arc |
| Triceratops | High | A bull but significantly worse |
| T-Rex | High | Confined to ground level due to size. Funny constraint |
| Stegosaurus | Medium | Slow, spiky, confused |
| Spinosaurus | High | Larger than T-Rex. Less aware of personal space |
| Pachycephalosaurus | Medium | Headbutts walls, machinery, workers with equal enthusiasm |

### Falling / Dropping Things — Universal

| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Anvil | Medium | Timeless. No explanation needed |
| Grand piano | High | No workplace needs a piano. Yet here we are |
| Safe full of money | Medium | Irresistible to workers who look up at it |
| Boulder | High | No explanation. Just a boulder |
| Bathtub | High | Looney Tunes energy. Always funny |
| Grandfather clock | Medium | Inexplicably present. Very heavy |
| Vending machine | High | Full. Very full |
| A second, angrier safe | High | The first one wasn't enough |
| Giant novelty dice | High | How did these get here |
| A very large fish | High | Falling from above. Origin unknown |

### Miscellaneous — Universal

| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Cursed item in storage | Low | Worker who interacts with it attracts every hazard on site |
| Confetti cannon | Low | Blinds workers at critical moments. Festive |
| Fog machine | Medium | Reduces visibility map-wide temporarily |
| Giant fan | Medium | Redirects falling objects and animals unpredictably |
| TNT labeled "Definitely Not TNT" | Medium | Workers suspicious but not suspicious enough |
| Trapdoor | Medium | Leads somewhere bad. Universal fit |
| Quicksand pit | Medium | Disguised as regular flooring/ground |
| Spring-loaded floor tile | Medium | Launches workers upward into something worse |
| Wishing well | High | Grants wishes extremely literally and badly |
| Clown | High | Follows specific workers until they panic |
| Portal | High | Sends workers somewhere worse |
| Ghost (Haunted Shift variant) | Low | Universal — every workplace has a tragic history |

---

## TIER 2 — CROSS-ENVIRONMENT HAZARDS
*Available to tagged environment groups only*

---

### INDUSTRIAL
*Construction Site, Factory, Shipyard, Oil Rig, Mine/Quarry, Chemical Plant, Nuclear Plant, Logging Site, Demolition Site, Junkyard*

#### Animals — Industrial

| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Angry bull | High | Plausible near any outdoor industrial site |
| Wild boar | Medium | Common near outdoor sites |
| Moose | High | Outdoor industrial only. Enormous, indifferent |
| Rhinoceros | High | Where did it come from. Industrial sites don't ask |
| Elephant | High | Knocks everything over by existing |
| Wolverine | Medium | Common near remote industrial sites |
| Emu | Medium | Famously won a war |
| Cassowary | Medium | Actively malicious |
| Crocodile / alligator | Medium | Any site with standing water or a moat |
| Sharks | High | Any site with a pit that fills with water |
| Hippo | High | Most dangerous animal in Africa. Fits industrial water hazards |
| Giant octopus | High | Any industrial water tank |
| Electric eel | Low | Any industrial standing water |
| Piranhas | Low | Smaller industrial water hazards |
| Snapping turtles | Low | Industrial ponds and pits |

#### Falling / Dropping Things — Industrial

| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Stack of bricks with loose brick | Low | Universal to industrial sites |
| Fraying rope holding heavy load | Low | Standard industrial equipment failure |
| Unsecured toolbox | Low | Falls from height when vibrated |
| Stack of steel beams, pin removed | Medium | Wide area impact |
| Entire pallet of materials | Medium | Crane or forklift load accident |
| Shipping container not secured | High | Takes out everything in landing zone |
| Second vehicle falling from height | High | How did it get up there |
| Port-a-potty dropped from height | Medium | Sealed. The smell is a secondary hazard |
| Generator dropped from height | Medium | Power outage as secondary effect |

#### Vehicles — Industrial

| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Tampered vehicle steering | Low | Any industrial vehicle |
| Runaway forklift | High | Self-propelled, no driver, bad intentions |
| Runaway steamroller | Medium | Slow, unstoppable |
| Rocket-powered wheelbarrow | High | Exactly what it sounds like |
| Trebuchet | High | Somehow obtained. Medieval, effective |

#### Environmental — Industrial

| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Mislabeled chemical barrels | Low | Any industrial site with storage |
| Tampered heavy equipment | Low | Fails during regular use |
| Exposed electrical wiring | Low | Standard industrial hazard |
| Fuel/chemical mixing accident | Medium | Mislabeled containers near heat source |
| Foundation/pit fencing removed | Medium | Workers walk off the edge |
| Structural collapse trigger | High | One pin removed, dominoes from there |
| Crane full spin mode | High | Suspended load swings in full circles |

---

### FOOD SERVICE
*Restaurant/Kitchen, Fast Food, Brewery/Distillery, Hotel, Catering Company*

#### Animals — Food Service

| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Rat infestation | Low | Health code nightmare. Workers panic |
| Angry swan in delivery area | Medium | Swans near hotel/restaurant deliveries |
| Seagulls | Low | Any food service with outdoor area |
| Cockroach swarm | Low | Causes panic, secondary accidents |

#### Falling / Dropping Things — Food Service

| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Industrial shelving collapse | Low | Overloaded stock shelving |
| Commercial oven door | Medium | Flies off hinges at pressure |
| Giant catering pot | Medium | Falls from industrial hook |
| Barrel of liquid from height | Medium | Brewery specific but fits all food service |

#### Environmental — Food Service

| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Grease fire | Low | Kitchen standard. Spreads rapidly |
| Wet floor near fryer | Low | Slip into something hot |
| Gas leak near ignition source | Medium | Kitchen explosion |
| Industrial mixer malfunction | Medium | Launches contents at high speed |
| Walk-in freezer door jammed | Medium | Workers trapped, temperature drops |
| Deep fryer overflow | Medium | Hot oil spreads across floor |
| Commercial dishwasher flood | Low | Floor becomes extremely slippery |
| Faulty refrigeration unit | Low | Ammonia leak, workers pass out |

---

### OFFICE / CORPORATE
*Office Building, Call Center, Bank, Law Firm, Government Building*

#### Animals — Office/Corporate

| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Angry swan in lobby | Medium | Escaped from nearby pond |
| Pigeon infestation | Low | Gets into ventilation, causes chaos |
| Raccoon in break room | Low | Knocked over bins, now defensive |

#### Falling / Dropping Things — Office/Corporate

| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Overloaded filing cabinet tips | Low | Bottom drawer opened, top-heavy |
| Office bookshelf collapse | Low | Too many binders |
| Ceiling tile falls | Low | Old building, water damage |
| Heavy printer from shelf | Medium | IT equipment improperly stored |
| Whiteboard falls from wall | Low | Improperly mounted |

#### Environmental — Office/Corporate

| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Overloaded power strip | Low | Causes electrical fire |
| Faulty elevator | Medium | Doors open on wrong floor or don't open at all |
| Loose stair railing | Low | Standard building negligence |
| Ancient HVAC system | Low | Pumps something unpleasant into ventilation |
| Revolving door too fast | Medium | Workers cannot exit or enter |
| Faulty office chair | Low | Collapses or launches occupant |
| Tangled ethernet cables across floor | Low | Trip hazard at scale |
| Coffee maker explosion | Low | Ancient, overloaded, inevitable |

---

### MEDICAL / SCIENCE
*Hospital, Laboratory, Pharmaceutical Plant, Veterinary Clinic*

#### Animals — Medical/Science

| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Escaped lab animal | Low | Rat, rabbit, or something larger |
| Escaped exotic specimen | High | Something that definitely should not be loose |
| Angry veterinary patient | Medium | Large animal not happy about its appointment |

#### Falling / Dropping Things — Medical/Science

| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Medical equipment from shelf | Low | Improperly stored, heavy |
| Industrial chemical container | Medium | Falls and leaks or explodes |
| Laboratory centrifuge projectile | Medium | Fails catastrophically at high speed |

#### Environmental — Medical/Science

| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Mislabeled chemical compounds | Low | Mixed with wrong substance |
| Faulty autoclave | Medium | Pressure builds, releases catastrophically |
| Biohazard container breach | Medium | Contents disputed |
| Slippery hospital floor | Low | Freshly waxed, no warning sign |
| Faulty medical gas supply | Medium | Wrong gas to wrong location |
| Centrifuge malfunction | Medium | High-speed rotation failure |
| Electrical medical equipment fault | Low | Shock hazard near standing water |

---

### RETAIL / WAREHOUSE
*Retail Store, Warehouse/Fulfillment Center, Supermarket, Car Dealership*

#### Animals — Retail/Warehouse

| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Rat infestation | Low | Storage areas especially |
| Pigeon in store | Low | Got in through loading bay |
| Angry customer's dog | Medium | Technically not a worker hazard but here we are |

#### Falling / Dropping Things — Retail/Warehouse

| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| High-shelf stock collapse | Low | Overloaded shelving, one item pulled |
| Pallet drop from forklift | Medium | Warehouse standard |
| Display stand collapse | Low | Retail floor hazard |
| Heavy flat-pack furniture | Medium | Falls from top shelf |
| Car from display platform | High | Car dealership specific but fits retail broadly |

#### Environmental — Retail/Warehouse

| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Wet floor, no sign | Low | Classic |
| Conveyor belt malfunction | Medium | Warehouse/fulfillment specific |
| Loading dock fall | Medium | Bay door open, no barrier |
| Shrink wrap machine malfunction | Medium | Wraps something it shouldn't |
| Automatic door malfunction | Low | Opens and closes at wrong time |
| Forklift in enclosed space | Medium | Warehouse only, tight corridors |

---

### ENTERTAINMENT
*Casino, Carnival/Amusement Park, Sports Stadium, Circus, Movie Studio/Film Set, Zoo*

#### Animals — Entertainment

| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Escaped zoo animal | High | Zoo specific but fits entertainment broadly |
| Circus animal loose | High | Lion, tiger, elephant, bear |
| Angry performing animal | Medium | Done with this. Done |
| Pelican in concession area | Low | Stadium/carnival coastal locations |
| Angry turkey in parking lot | Low | Stadium events especially |

#### Falling / Dropping Things — Entertainment

| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Stage lighting rig | Medium | Movie studio, stadium, circus |
| Rigging collapse | Medium | Any entertainment venue with overhead equipment |
| Scoreboard falls | High | Stadium specific but fits entertainment |
| Prop falls from height | Low | Movie studio especially |
| Circus trapeze apparatus | Medium | Improperly secured |

#### Environmental — Entertainment

| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Faulty carnival ride | Medium | Amusement park especially |
| Pyrotechnics malfunction | High | Stadium, circus, movie studio |
| Stage trapdoor malfunction | Medium | Opens at wrong time |
| Faulty casino machine | Low | Electrical, mechanical, or both |
| Crowd crush trigger | High | Stadium events — requires careful tone handling |
| Film set practical effect failure | Medium | Explosion, fire, vehicle |

---

### EXTREME / WILDCARD
*Space Station, Submarine, Haunted House, Ski Resort, Funeral Home, Daycare*

#### Animals — Extreme/Wildcard

| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Polar bear | High | Ski resort especially |
| Avalanche-triggered wildlife | High | Ski resort — animals fleeing the slope |
| Ghost animal | Medium | Haunted house — spectral version of any animal |

#### Falling / Dropping Things — Extreme/Wildcard

| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Equipment in zero gravity | Medium | Space station — floats then impacts |
| Ski lift equipment | Medium | Ski resort |
| Casket falls from stand | Medium | Funeral home |

#### Environmental — Extreme/Wildcard

| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Hull breach | High | Submarine and space station |
| Oxygen supply tampered | High | Space station and submarine |
| Avalanche trigger | High | Ski resort |
| Embalming fluid spill | Medium | Funeral home |
| Haunted house practical effect gone wrong | Low | Haunted house — hard to distinguish from the act |
| Toy scattered across floor | Low | Daycare — trip hazard at industrial scale |
| Zero gravity malfunction | High | Space station |
| Periscope malfunction | Medium | Submarine |

---

## TIER 3 — ENVIRONMENT-SPECIFIC HAZARDS
*Unique to a single workplace setting. Custom subclass per environment.*

---

### Construction Site
| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Pterodactyl nest on scaffolding | High | Disturbed when workers reach top floor |
| Crocodile moat at entrance | High | Surrounds the gate |
| Crane full spin mode | High | Sweeps multiple levels |
| Entire scaffolding section collapse | High | One pin, dominoes |
| Greased ladder | Medium | Worker slides back down into something |
| Fake entrance | High | Second gate, leads somewhere terrible |
| Wrecking ball with smiley face | High | It's winking at you |
| Concrete mixer launches contents | Medium | High speed when opened wrong |

### Office Building
| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Printer paper avalanche | Low | Filing room collapses outward |
| Motivational poster falls | Low | Heavy frame, poorly mounted |
| Ergonomic chair launches | Medium | Spring mechanism tampered |
| Water cooler sabotaged | Low | Floods immediate area |
| Fire drill at wrong moment | Medium | Everyone evacuates into something outside |

### Restaurant / Kitchen
| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Flambé gets out of hand | Medium | Table-side cooking goes wrong |
| Dumbwaiter malfunction | Medium | Sends worker instead of food |
| Industrial spit roast | High | Rotates. Catches things |
| Soup of the day is wrong | Low | Ambiguous. Deeply wrong |

### Hospital
| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Runaway hospital bed | Medium | Wheels unlocked on a slope |
| Defibrillator misfire | Medium | Applied incorrectly to wrong person |
| Wrong medication dispensed | Low | Pharmacy error, subtle |
| MRI magnet attracts everything metal | High | Pulls equipment, tools, hard hats across room |

### Casino
| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Rigged slot machine explosion | Medium | Jackpot mechanism tampered |
| Card shuffler malfunction | Low | Launches cards at high velocity |
| Poker chip avalanche | Low | Improperly stacked, collapses |
| Roulette wheel goes critical | Medium | Spinning too fast, ball becomes projectile |

### Nuclear Power Plant
| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Coolant leak | Medium | Floor becomes extremely slippery and cold |
| Control rod tampered | High | The report will not say what happened next |
| Radiation warning alarm tampered | Low | Silenced. Workers don't evacuate |
| Geiger counter gives wrong readings | Low | Workers go somewhere they shouldn't |

### Zoo
| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Enclosure latch left open | Medium | One specific animal now free |
| Feeding time wrong exhibit | High | Wrong food in wrong enclosure triggers wrong animal |
| Petting zoo animal goes feral | Medium | It was always going to happen |
| Giraffe loose in staff area | High | Too tall for most indoor spaces. Very confused |

### Carnival / Amusement Park
| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Ferris wheel unlocked | High | Rotates freely, gondolas swing |
| Hall of mirrors — real maze | Medium | Staff genuinely cannot find the exit |
| Funhouse floor malfunction | Medium | Tilts, rotates, or opens |
| Cotton candy machine explodes | Low | Sugar. Everywhere. Extremely slippery |
| Balloon animal goes wrong | Low | Somehow. We don't know how either |

### Space Station
| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Airlock opens wrong direction | High | The report will simply say "decompression event" |
| Thruster misfires | High | Station rotates unexpectedly |
| Food in zero gravity | Low | Floating food items obstruct vision |
| Space suit tampered | High | Worker puts it on, goes outside, suit malfunctions |

### Submarine
| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Torpedo loaded backwards | High | The report will be very short |
| Periscope hits something | Medium | Unexpected surface object |
| Diving plane jammed | High | Submarine descends uncontrollably |
| Sonar at full volume | Low | Crew disoriented, stumble into things |

### Haunted House
| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Real ghost mixed with fake ghosts | Low | Indistinguishable from the act |
| Prop chainsaw is real chainsaw | High | How did this happen |
| Actual trapdoor where floor should be | Medium | Staff member falls through their own attraction |
| Jumpscare animatronic too powerful | Medium | Knocks workers backward into something |

### Ski Resort
| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Ski lift stops mid-run | Medium | Workers stranded, then dropped |
| Snow cannon aimed wrong | Medium | Covers staff entrance in three seconds |
| Avalanche trigger | High | Listed above, noted here for specificity |
| Snowplow path altered | Medium | Takes unexpected route through staff area |

### Funeral Home
| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Wrong body in wrong casket | Low | Administrative. Causes significant distress |
| Hearse brakes tampered | Medium | Rolls. Downhill. With occupant |
| Cremation oven door malfunction | High | Opens at wrong time |
| Embalming equipment misfires | Medium | Listed above, noted here specifically |

### Circus
| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Cannon aimed at wrong target | High | The human cannonball act goes off-script |
| Tightrope wire cut partially | Medium | Holds until it doesn't |
| Lion tamer loses whip | High | Self-explanatory |
| Clown car contains too many clowns | Medium | They keep coming. It doesn't stop |

### Daycare
| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Toy scattered across entire floor | Low | Industrial-scale trip hazard |
| Art supply explosion | Low | Glitter. Permanent. Everywhere |
| Juice box pressure buildup | Low | Somehow. Physics is different here |
| Nap time alarm malfunction | Low | Staff fall asleep at critical moment |

### Laboratory
| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Experiment gets out of containment | High | Nature of experiment: TBD |
| Chemical reaction chain | Medium | One mislabeled bottle starts it |
| Centrifuge launches sample | Medium | High speed, wrong trajectory |
| Something in the fridge that shouldn't be | Low | Nobody labeled it. Nobody should open it |

### Oil Rig
| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Blowout preventer tampered | High | The report will use the word "incident" |
| Helicopter pad slippery | Medium | Supply helicopter lands, slides |
| Flare stack misdirected | High | Points somewhere it shouldn't |
| Diving bell malfunction | High | Goes down. Does not come back up on schedule |

### Mine / Quarry
| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Support beam removed | Medium | Structural collapse on timer |
| Minecart brakes removed | High | Classic. Timeless |
| Dynamite mislabeled | High | Labeled as something reasonable |
| Ventilation fan reversed | Medium | Pushes bad air in instead of out |

### Shipyard
| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Dry dock flooded early | High | Ship not finished. Workers inside |
| Welding near fuel line | Medium | Standard shipyard catastrophe |
| Hull section falls | High | Improperly secured during construction |
| Crane drops ship component | High | Very large. Very heavy |

### Bank
| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Vault door malfunction | Medium | Traps workers inside or swings into them |
| Pneumatic tube system overloaded | Low | Launches canisters at high speed |
| Security door closes on wrong person | Low | Trapped in airlock between doors |
| Dye pack in wrong place | Low | Covers everyone in immediate area |

### Movie Studio / Film Set
| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Stunt gone wrong — real fire | High | Practical effect not properly contained |
| Prop weapon is real weapon | High | Prop department filing is very poor |
| Camera crane swings into crew | Medium | Operator error. Allegedly |
| Green screen hides actual drop | Medium | Worker walks through what looks like a wall |

---

## IMPLEMENTATION NOTES

- All Tier 1 hazards are instantiated in every environment automatically
- Tier 2 hazards are inherited by environment based on category tag — one environment can have multiple tags if appropriate (e.g. a Hotel might inherit both FoodService and OfficeCorporate)
- Tier 3 hazards are manually assigned to their single environment only
- Suspicion tiers (Low/Medium/High) are properties of each hazard class and feed directly into the PD meter calculation
- Animal hazards across all tiers share the ActiveHazard behavior (semi-random movement, can trigger other traps, can interfere with inspector)

---

*This is a living document. Hazards will be added and refined as each environment is fully designed.*
