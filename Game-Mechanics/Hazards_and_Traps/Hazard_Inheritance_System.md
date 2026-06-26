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
| Chemical plant mixing valves cross-connected | High | Combines things that should never combine |
| Nuclear plant cooling system replaced | High | Coolant replaced with something that isn't coolant |
| Oil rig blowout preventer software bug | High | Activates randomly after patch |
| Mine ventilation reversed, exits sealed | High | Simultaneous. Very bad |
| Logging site bundling wire under tension | High | Snaps, whips across entire area |
| Shipyard magnetic crane loses polarity | High | Repels metal at full magnet strength |
| Factory line speed governor removed | High | Production line at 50x normal speed |
| Demolition charges rearranged | High | Building falls toward workers instead of away |
| Junkyard car crusher remote activated | High | Anything in range qualifies as a car |
| Chemical plant pressure relief valves welded shut | High | Every vessel on a timer |
| Nuclear plant control room displays all show normal | High | Nothing is normal |
| Factory robotic arm reprogrammed | High | Very fast, very strong, no longer ignoring humans |
| Oil rig helideck lights rearranged | High | Helicopter lands somewhere that isn't the deck |
| Shipyard dry dock pumps reversed | High | Floods instead of drains |
| Mining explosive inventory mislabeled | High | Workers handle wrong items with wrong tools |

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
| Industrial blast chiller set to absolute zero | High | Worker enters walk-in, temperature drops instantly |
| Dumbwaiter overloaded with something alive | High | Contents disputed |
| Commercial kitchen ventilation hood becomes flamethrower | High | Grease trap ignites, hood redirects |
| Brewery fermentation tank over-pressured | High | Cork-pops the entire top off |
| Industrial meat slicer blade replaced | High | Something faster. The report is brief |
| Catering van on slope, brakes removed | High | Converted to battering ram |
| Hydraulic restaurant booth seating | High | Compresses instead of reclining |
| Soda fountain carbonation at industrial pressure | High | Nozzles become pressure jets |
| Industrial dishwasher at parts-cleaning temperature | High | Set far beyond food service range |
| Walk-in freezer CO2 backup vents inward | High | Vents directly into room instead of outside |
| Grease trap connected to main burner | High | Entire kitchen becomes one large flame |
| Commercial juicer handles more than fruit | High | If encouraged |
| Automated food delivery robot speed governor removed | High | No longer food-safe speeds |
| Grease trap overfilled deliberately | High | Entire floor becomes grease skating rink |

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
| Motivational poster avalanche | Medium | Entire hallway of heavy framed posters falls in sequence |
| Office supplies ordered in industrial quantities | High | Pallet of staplers on third floor. Floor gives way |
| Suspended ceiling grid drops | High | Tiles, lighting rigs, ventilation ducts, all of it |

#### Electrical / EMP — Office/Corporate

| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Overloaded power strip | Low | Causes electrical fire |
| Coffee maker explosion | Low | Ancient, overloaded, inevitable |
| All USB ports deliver full building voltage | Medium | Discovered one port at a time |
| Static electricity carpet plus exposed wiring | Medium | Workers become conductors |
| Faulty fluorescent lighting cascade | Medium | Entire floor's lights explode in sequence like dominoes |
| Photocopier toner replaced with conductive powder | Medium | Entire machine becomes live on use |
| EMP device disguised as server rack | High | Knocks out all electronic safety systems simultaneously |
| Overloaded server room combustion | High | Heat buildup, sprinklers activate, water plus electrical |
| Tampered building lightning rod | High | Directs strike into building instead of away |
| Van de Graaff generator in stairwell | High | Workers touching metal railings get launched |
| Mainframe overload cascade | High | Building's entire electrical system fails in sequence |
| Tesla coil in break room | High | Arcs between metal objects unpredictably |
| Wireless charging pads overloaded across floor | High | Generates heat, catches carpet |
| Smart building system hacked | High | Everything automated turns against workers simultaneously |
| Defibrillator wall unit tampered | High | Activates automatically when anyone walks past |
| Electric fence around corporate campus | High | Campus environments only |
| Power surge protectors replaced with surge inducers | High | Every device connected becomes a hazard |
| Entire server room UPS battery bank short-circuited | High | Enormous heat and charge simultaneously |
| Backup generator floods ground floor with exhaust | High | Activated during power failure |
| Stairwell handrails electrified | High | Discovered on contact |
| Biometric scanner stores charge | High | Delivers on fingerprint contact. Escalates |
| Security camera motors overloaded | High | Cameras spin off mounts at speed |
| Electronic visitor badges contain charge | High | Delivered when tapped to check in |

#### Structural / Architectural — Office/Corporate

| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Faulty elevator | Medium | Doors open on wrong floor or don't open at all |
| Loose stair railing | Low | Standard building negligence |
| Revolving door too fast | Medium | Workers cannot exit or enter |
| Tangled ethernet cables across floor | Low | Trip hazard at scale |
| Load-bearing wall removed during renovation | High | Floor above collapses on timer |
| Escalator at triple speed in wrong direction | High | Deposits workers somewhere bad |
| Glass floor panels improperly installed | High | Look solid. Aren't |
| False ceiling rigged to drop entirely | High | Everything above the drop ceiling comes down |
| Fire suppression system filled with wrong substance | High | Not water |
| Elevator cable frayed | High | Drops one floor at a time before going all the way |
| Mezzanine safety glass replaced with sugar glass | High | Looks identical. Holds nothing |
| Open plan floor has hidden slope | Medium | Furniture slides slowly toward one wall all simulation |
| Atrium skylight loosened | High | Falls inward rather than outward |
| Conference room soundproofing conceals structural damage | Medium | Nobody hears the warning signs |
| Building window cleaning rig goes rogue | High | Swings into windows from exterior |
| Raised access floor panels in wrong configuration | High | Entire IT department floor collapses in sections |
| Fire escape stairs replaced with decorative ones | High | Hold no weight |
| All office chairs have one-directional wheels | Medium | Only move toward windows |
| Fire door magnets reversed | High | All fire doors slam open or closed simultaneously |

#### Ventilation — Office/Corporate

| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Ancient HVAC system | Low | Pumps something unpleasant into ventilation |
| HVAC pumps laughing gas into specific floor | High | Workers helpless, stumble into things |
| Ventilation system reversed | High | Pumps exhaust fumes inward |
| Something released into air handling unit | High | Nature deliberately vague in safety report |
| Ventilation fan blades loosened | High | Detach at speed, travel through ductwork |
| Specific office air supply redirected to pure nitrogen | High | Workers lose consciousness without warning |
| Aerosol cans placed in ventilation return | High | Heat activates, propelled through ductwork |
| Dry ice dumped into HVAC | High | CO2 builds in lower floors |
| Industrial fog machine wired into ventilation | High | Entire building fills. Workers completely blind |
| Ventilation connected to underground garage exhaust | High | Carbon monoxide builds gradually |
| Allergen concentrate released into meeting room | Medium | Before big presentation. Workers incapacitated |
| HVAC oscillates between -10C and 50C rapidly | High | Workers dressed for neither extreme |
| Pollen concentrate in specific meeting room | Medium | Big presentation. Nobody can speak |

#### Security Systems — Office/Corporate

| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Automated sprinkler connected to motion sensors | High | Activates whenever anyone moves |
| Security card readers deliver escalating shock | High | Low at first. Builds |
| Building intercom produces disorienting frequencies | Medium | Workers stumble into things |
| Automated bollards activate randomly at full speed | High | Parking lot. Full speed |
| All emergency exit signs point wrong direction | Medium | Discovered during emergency |
| PA system taken over | High | Plays sounds causing specific archetypes to panic |
| Keycard doors all unlock simultaneously on fire alarm | High | Including doors that shouldn't |
| Security robot goes rogue | High | Roomba-scale to humanoid depending on level |
| Panic button triggers building-wide lockdown | High | Everyone trapped inside with your hazards |
| CCTV hacked to show wrong feeds | Low | Security guard watching empty hallway |

#### Plumbing / Water — Office/Corporate

| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Water cooler connected to hot water supply | Medium | Scalding. Immediate |
| Bathroom pipes rerouted | Medium | Cold tap is boiling. Hot tap is ice cold |
| All hand dryers overloaded to industrial heat | Medium | Bathroom becomes hazard zone |
| Sprinkler system activated manually | High | Floods specific floor |
| Fire suppression filled with flammable substance | High | The report will not use the word "ironic" |
| Executive washroom fountain contains wrong liquid | Medium | Decorative. Wrong |
| Entire plumbing pressure-boosted | High | All taps become pressure washers |
| Urinal cakes replaced with reactive compound | Medium | Reacts with water. Obviously |

#### Corporate-Specific Absurdity — Office/Corporate

| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Faulty office chair | Low | Collapses or launches occupant |
| Industrial paper shredder where regular one should be | Medium | Handles anything fed into it |
| Boardroom table on hidden hydraulics | High | Launches upward during meeting |
| Projector screen conceals mechanism | Medium | Something behind it |
| Executive chair with rocket assist | High | CEO tier. Nobody questions it |
| Motivational poster launches whoever stands beneath it | High | "REACH FOR THE STARS" is literal |
| Pneumatic document tube at dangerous pressure | High | Canisters become projectiles through walls |
| Coffee machine connected to wrong supply line | High | Dispenses something industrial |
| Photocopier filled with flash powder | High | Activates on lid press |
| Annual performance review triggers trapdoor | High | Results-based activation |
| Hot desking assigns everyone to same desk | Medium | Forty workers converge on one location |
| Printer network sends all jobs to one printer | High | Machine overloads, explodes with paper |
| Corporate team building obstacle course on roof | High | Mandatory attendance |
| Motivational speaker microphone causes feedback | High | Shatters glass in immediate area |
| Standing desk locked at maximum height | Medium | Workers can't reach anything, eventually fall |
| Ergonomic ball chair over-pressured | High | Pops at threshold, launches occupant |
| Entire office on wheels, AC activates | Medium | Desks begin rolling when building's AC turns on |
| Mail room pneumatic tubes fire through walls | High | Pressurized to penetrate partition walls |
| Vending machine contains live animals | High | Workers find out on purchase |
| CEO's corner office has a moat | High | Nobody questions it. It's his office |
| Mandatory fire drill during other hazard activation | High | Workers evacuate into outdoor hazards |
| Company mascot costume contains something | Medium | Something that objects to being in there |
| Office holiday party punch bowl on wrong tap | Medium | Connected to something that isn't punch |
| Whiteboard marker replaced with industrial solvent | Medium | Fumes in enclosed meeting room |
| Corporate rebranding paint never dries | Low | Entire office. Everyone. Permanently |
| All office chairs only move toward windows | Medium | Listed above, noted specifically here |
| Office refrigerator under significant pressure | High | Contents unknown. Do not open |

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
| MRI machine powered beyond limits | High | Pulls any metal object in building toward it |
| Surgical robot software update | High | Operates with great confidence and no accuracy |
| Autoclave self-cleaning cycle near workers | High | Steam release catastrophic |
| Pharmaceutical compounding machine misfills | High | Wrong compound, wrong capsules, industrial scale |
| Hospital bed hydraulics overloaded | High | Launches occupant to ceiling |
| Defibrillator charging cycle set to continuous | High | Wall unit becomes electric fence |
| Medical gas cylinders all opened simultaneously | High | Oxygen-rich environment. Any spark catastrophic |
| Radiation therapy equipment misdirected | High | Points at waiting room |
| Hospital laundry industrial press malfunction | High | Handles more than linens |
| Pneumatic sample transport over-pressured | High | Tubes become rail guns |
| Laboratory fume hood fan reversed | High | Concentrates fumes inward |
| Cryogenic storage tank vents liquid nitrogen | High | Across lab floor |
| Centrifuge with intentional imbalance | High | Shakes itself apart at speed. Shrapnel |
| Gene sequencer produces wrong results | Medium | Causes existential distress in all nearby workers |
| Veterinary surgery table hydraulics at maximum | High | Patient and vet both launch |

---

### RETAIL / WAREHOUSE
*Retail Store, Warehouse/Fulfillment Center, Supermarket, Car Dealership*

#### Animals — Retail/Warehouse

| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Rat infestation | Low | Storage areas especially |
| Pigeon in store | Low | Got in through loading bay |
| Angry customer's dog | Medium | Technically not a worker hazard. Here we are |

#### Falling / Dropping Things — Retail/Warehouse

| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| High-shelf stock collapse | Low | Overloaded shelving, one item pulled |
| Pallet drop from forklift | Medium | Warehouse standard |
| Display stand collapse | Low | Retail floor hazard |
| Heavy flat-pack furniture from top shelf | Medium | Falls when browsed |
| Car from display platform | High | Car dealership. Display platform hydraulics fail |

#### Environmental — Retail/Warehouse

| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Wet floor no sign | Low | Classic |
| Conveyor belt malfunction | Medium | Warehouse/fulfillment specific |
| Loading dock fall | Medium | Bay door open, no barrier |
| Shrink wrap machine malfunction | Medium | Wraps something it shouldn't |
| Automatic door malfunction | Low | Opens and closes at wrong time |
| Forklift in enclosed space | Medium | Tight corridors, no margin |
| Automated warehouse robot reprogrammed | High | Selects workers instead of packages |
| Conveyor belt speed governor removed | High | Anything on it reaches escape velocity |
| Pallet wrapper set to wrap anything stationary | High | Worker pauses. Consequences follow |
| Loading dock leveler hydraulics reversed | High | Launches trucks upward on arrival |
| Self-checkout extremely literal about unexpected items | High | Unexpected item in bagging area. Very literal |
| Warehouse vertical carousel runs continuously | High | Anything caught in it goes around |
| Shopping cart return machine compresses beyond limits | High | Beyond design parameters |
| Forklift mast at max height in enclosed space | High | Punches through ceiling |
| Retail muzak converted to sonic weapon frequencies | High | Affects entire floor |
| Supermarket pricing gun at industrial staple pressure | High | No longer a pricing gun |
| Display mannequins replaced with something that moves | High | Nature of replacement TBD |
| Car dealership hydraulic lift remote activated | High | Car descends onto whoever is beneath it |
| Warehouse fire suppression at industrial concentration | High | Entire floor chest-deep in foam in seconds |
| Retail escalator handrails electrified | High | Discovered on contact |
| Stock room compactor activated remotely | High | Wrong contents. Compacts anyway |

---

### ENTERTAINMENT
*Casino, Carnival/Amusement Park, Sports Stadium, Circus, Movie Studio/Film Set, Zoo*

#### Animals — Entertainment

| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Escaped zoo animal | High | Zoo specific but fits entertainment broadly |
| Circus animal loose | High | Lion, tiger, elephant, bear |
| Angry performing animal | Medium | Done with this. Done |
| Pelican in concession area | Low | Coastal stadium/carnival locations |
| Angry turkey in parking lot | Low | Stadium events especially |

#### Falling / Dropping Things — Entertainment

| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Stage lighting rig | Medium | Movie studio, stadium, circus |
| Rigging collapse | Medium | Any entertainment venue with overhead equipment |
| Scoreboard falls | High | Stadium. Very large. Very heavy |
| Prop falls from height | Low | Movie studio especially |
| Circus trapeze apparatus falls | Medium | Improperly secured |

#### Environmental — Entertainment

| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Faulty carnival ride | Medium | Amusement park especially |
| Pyrotechnics malfunction | High | Stadium, circus, movie studio |
| Stage trapdoor malfunction | Medium | Opens at wrong time |
| Faulty casino machine | Low | Electrical, mechanical, or both |
| Film set practical effect failure | Medium | Explosion, fire, vehicle |
| Casino card shuffler at projectile velocity | High | Modified to shuffle extremely fast |
| Amusement park ride launch system reprogrammed | High | Launches without track |
| Stadium floodlights overloaded | High | Explode in sequence across entire venue |
| Circus cannon over-charged | High | Range significantly increased |
| Movie studio pyrotechnics triggered remotely | High | During non-stunt scene |
| Zoo enclosure environmental controls reversed | High | Tropical gets arctic. Arctic gets tropical. All doors open |
| Casino chip sorting machine at industrial speed | High | Handles more than chips |
| Stadium PA produces brown note frequency | High | Affects entire crowd and staff |
| Circus high wire tensioned beyond breaking point | High | Snaps when weight applied. Whips both directions |
| Movie studio car stunt vehicle remote controlled | High | No driver |
| Amusement park haunted house set to real | High | Practical effects are now actual effects |
| Stadium hot dog cart pressurized | Medium | Condiment cannon |
| Casino money counter modified | High | Handles more than money |
| Circus clown car structural integrity compromised | High | Collapses when fully loaded |
| Film set entire lighting grid drops simultaneously | High | All of it |

---

### EXTREME / WILDCARD
*Space Station, Submarine, Haunted House, Ski Resort, Funeral Home, Daycare*

#### Animals — Extreme/Wildcard

| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Polar bear | High | Ski resort especially |
| Avalanche-triggered wildlife | High | Animals fleeing the slope |
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
| Haunted house practical effect gone wrong | Low | Hard to distinguish from the act |
| Toy scattered across floor | Low | Daycare — trip hazard at industrial scale |
| Zero gravity malfunction | High | Space station |
| Periscope malfunction | Medium | Submarine |
| Space station attitude thrusters all fire simultaneously | High | Station spins. Everything not bolted down becomes projectile |
| Submarine ballast tanks all blow simultaneously | High | Uncontrolled ascent. Decompression event |
| Ski resort snow cannon network all activate | High | Resort buried in minutes |
| Funeral home embalming pump wrong supply, wrong direction | High | Industrial pressure |
| Haunted house emergency lighting replaced with darkness | High | Total blackout during peak chaos |
| Daycare nap time machine produces infrasonic frequency | High | Staff fall asleep simultaneously |
| Space station solar panels refocused | High | Concentrated solar beam enters station |
| Submarine torpedo tube pressurized without torpedo | High | Pressure wave propagates through hull |
| Ski resort all chairlift chairs detached simultaneously | High | Chairs become projectiles downslope |
| Funeral home viewing room floor waxed with industrial compound | High | Completely frictionless |
| Haunted house fog system connected to industrial chemical supplier | High | Not fog juice |
| Daycare ball pit contains something at the bottom | High | We don't need to say what |
| Space station food rehydration system connected to fuel line | High | The report will be brief |
| Submarine sonar amplified to hull resonance frequency | High | Structural consequences |
| Ski resort avalanche control explosives aimed at lodge | High | Instead of slope |

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
| Radiation warning alarm silenced | Low | Workers don't evacuate |
| Geiger counter gives wrong readings | Low | Workers go somewhere they shouldn't |

### Zoo
| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Enclosure latch left open | Medium | One specific animal now free |
| Feeding time wrong exhibit | High | Wrong food triggers wrong animal |
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
| Avalanche trigger | High | Noted here specifically for this environment |
| Snowplow path altered | Medium | Takes unexpected route through staff area |

### Funeral Home
| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Wrong body in wrong casket | Low | Administrative. Causes significant distress |
| Hearse brakes tampered | Medium | Rolls. Downhill. With occupant |
| Cremation oven door malfunction | High | Opens at wrong time |
| Embalming equipment misfires | Medium | Noted here specifically |

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
| Something in the fridge | Low | Nobody labeled it. Nobody should open it |

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

### Factory
| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Assembly line speed at maximum | High | Products become projectiles |
| Industrial press wrong timing | High | Closes at wrong moment |
| Robotic arm reprogrammed | High | Listed above, specific here |
| Quality control laser misdirected | High | Industrial laser. Points at workers |

### Chemical Plant
| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Mixing valves cross-connected | High | Listed above, specific here |
| Pressure relief valves welded shut | High | Every vessel on a timer |
| Chemical shower triggered wrong | Medium | Emergency safety shower activates wrong chemical |
| Storage tank integrity compromised | High | One tank. Then the next |

### Logging Site
| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Log flume redirected toward workers | High | Logs move fast. Workers don't move faster |
| Chainsaw remote triggered | High | Operating on its own |
| Tree felling direction altered | High | Falls toward workers instead of away |
| Log bundling wire under tension snaps | High | Listed above, specific here |

### Demolition Site
| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Charges rearranged | High | Building falls wrong direction |
| Wrecking ball reprogrammed | High | Targets something other than the building |
| Debris chute aimed wrong | Medium | Deposits debris somewhere occupied |
| Structural survey deliberately wrong | Low | Workers enter unsafe section |

### Junkyard
| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Crusher remote activated | High | Listed above, specific here |
| Compacted car stack unstable | High | Stack collapses when disturbed |
| Electromagnetic crane wrong target | High | Lifts workers instead of cars |
| Hazardous waste barrel mislabeled | Low | Standard junkyard administrative failure |

### Sports Stadium
| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Scoreboard descent | High | Listed above, specific here |
| Field sprinkler system at pressure | High | Nozzles become jets |
| Retractable roof malfunction | High | Closes or opens at wrong time, wrong speed |
| Goalpost collapses | Medium | Improperly secured |

### Hotel
| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Revolving door at maximum speed | High | Listed above, specific here for hotel lobby |
| Laundry chute misdirected | Medium | Deposits staff somewhere |
| Room service cart rigged | Low | Contents disputed |
| Swimming pool chemical balance wrong | Medium | Staff discover during maintenance |

### Brewery / Distillery
| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Fermentation tank over-pressured | High | Listed above, specific here |
| Still explosion | High | Pressure builds in distillation apparatus |
| Barrel stack collapses | Medium | One barrel pulled, dominoes |
| Tasting room connected to wrong barrel | Low | Contents significantly stronger than labeled |

### Fast Food
| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Drive-through barrier at full speed | High | Arm comes down on vehicles |
| Ice cream machine finally explained | High | What is in there. We find out |
| Ball pit in play area contains something | High | Same energy as daycare. Different context |
| Soft drink dispenser pressurized | High | Fountain becomes industrial nozzle |

### Pharmaceutical Plant
| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Compounding machine misfills at scale | High | Listed above, specific here |
| Tablet press wrong compound | High | Produces something not in the formulary |
| Clean room air supply wrong | High | Positive pressure room goes negative |
| Temperature-controlled storage fails | Medium | Contents become unpredictable |

### Veterinary Clinic
| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Angry large animal appointment | High | Listed above, specific here |
| Sedation dose miscalculated | Medium | Wrong direction |
| Surgical laser misdirected | High | Veterinary laser. Points at staff |
| Exotic animal containment failure | High | The species is not disclosed in the report |

### Catering Company
| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Van loaded wrong, center of gravity off | High | Turns corner, consequences follow |
| Industrial chafing dish fuel ignites | Medium | Under wrong container |
| Catering lift fails at event venue | High | Full load. Descends |
| Wrong menu delivered to wrong event | Low | Severe allergy implications. The report is clinical |

### Government Building
| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Security screening equipment reversed | High | Sends items back at speed |
| Parliamentary/council chamber trapdoor | High | Installed by previous administration |
| Document destruction machine handles more | High | More than documents |
| Official vehicle fleet brakes tampered | High | Entire motor pool |

### Law Firm
| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Filing room structural failure | High | Weight of case files finally wins |
| Conference call system feedback | Medium | Specific frequency. Shatters glassware |
| Evidence room containment failure | High | Nature of evidence: TBD |
| Legal library bookshelf domino | Medium | One volume pulled, all fall |

### Call Center
| Hazard | Suspicion | Notes |
|--------|-----------|-------|
| Headset delivers charge on call connect | High | Every incoming call |
| Server room overheats into floor | High | Heat rises through raised floor into call floor |
| Chair adjustment lever pressurized | Medium | Launches occupant |
| Hold music frequency causes disorientation | Medium | Workers stumble, headsets tangled |

---

## IMPLEMENTATION NOTES

- All Tier 1 hazards are instantiated in every environment automatically
- Tier 2 hazards are inherited by environment based on category tag — one environment can have multiple tags if appropriate (e.g. a Hotel might inherit both FoodService and OfficeCorporate)
- Tier 3 hazards are manually assigned to their single environment only
- Suspicion tiers (Low/Medium/High) are properties of each hazard class and feed directly into the PD meter calculation
- Animal hazards across all tiers share the ActiveHazard behavior (semi-random movement, can trigger other traps, can interfere with inspector)
- High-danger hazards across all categories should now be represented roughly equally across environment types — no setting should feel significantly safer than any other to design for

---

*This is a living document. Hazards will be added and refined as each environment is fully designed.*
