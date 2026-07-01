# Sound & Music Direction — Safety Code Violator

**Safety Code Violator GDD**
*Audio direction for music, sound effects, voice, ambient design, and technical implementation.*

---

## Overall Audio Philosophy

Cheerful corporate energy that slowly descends into comedic chaos. Sound design is a major source of humor in this game — not just accompaniment to the visuals but an active comedy layer in its own right.

The audio arc of every shift mirrors the visual arc: clean and professional at the start, increasingly unhinged as chaos builds, triumphant and absurd at the debrief. The gap between the corporate presentation of the audio and the carnage it's soundtracking is where a lot of the humor lives.

**Audio tone references:**
- Corporate elevator music taken to its logical extreme
- Looney Tunes / classic cartoon sound design — exaggerated, physical, satisfying
- Stock training video music — motivational, slightly oppressive, deeply ironic

---

## Music

### Hub / Menu Music
- Upbeat, slightly sinister corporate elevator music
- "Smooth jazz with a hint of evil"
- Clean, professional, completely appropriate for a safety consultancy firm

### In-Shift Music
Music evolves dynamically based on the **Plausible Deniability meter** — the primary chaos measurement system. As PD fills, the music responds:

| PD Level | Music State |
|----------|------------|
| 0–25% | Clean, motivational stock training video music. Upbeat. Professional |
| 25–50% | Subtle changes — extra percussion enters, tempo slightly elevated |
| 50–75% | More unhinged — distorted instruments creep in, tempo increases, hints of chaos |
| 75–99% | Frantic, comedic action music — full percussion, distorted brass, things going wrong |
| 100% (Inspector spawned) | Distinct alarm-dressed-as-corporate-notification sting, then music shifts to tense pursuit energy |

**Speed control audio interaction:**
- At 1x speed: music plays normally
- At fast-forward speeds: music pitches up slightly and compresses — at 64x, the effect is deliberate chipmunk energy
- Worker ambient chatter and panic sounds also pitch up at fast-forward — very funny, very intentional
- At pause: music fades to near-silence, ambient environment sounds only

### Highlight Reel Music
- Triumphant, over-the-top victory fanfares
- Cartoonish stings timed to each highlight moment
- Film-score "ta-da" energy for the Most Valuable Victim reveal
- Comedic descending tones for any particularly absurd moment

### Debrief Music
- Triumphant opening sting on debrief screen appearance
- Each star reveal has its own audio moment — building fanfare for each star earned
- 5-star reveal gets full bombastic treatment
- 1-star result gets a deflated trombone. Obviously

---

## Sound Effects

### Hazard Placement (Setup Phase)
- Satisfying clicks, beeps, and corporate-sounding confirmations for each placement
- Low-suspicion hazard placement: subtle, professional confirmation tone
- High-suspicion hazard placement: slightly more dramatic confirmation — the game knows what you're doing
- Optional: subtle evil chuckle on particularly nasty placements (player-toggleable in settings)
- Budget limit reached: corporate "ding" with slight warning tone

### Worker Ambient Sounds (Normal Operation)
- Workplace-appropriate ambient chatter — phones ringing, keyboards typing, machinery operating
- Each environment has a distinct ambient soundscape:

| Environment | Ambient Sound Profile |
|-------------|----------------------|
| Construction Site | Power tools, concrete mixer, crane operations, hard hat knocks, shouting across distance |
| Office | Keyboards, phone calls, printer running, coffee machine gurgling, distant meeting noise |
| Restaurant/Kitchen | Sizzling, chopping, industrial ventilation, orders called out, plates clattering |
| Factory | Heavy machinery, conveyor belts, industrial fans, warning beepers |
| Hospital | PA system, medical equipment beeps, trolley wheels, hushed voices |
| Casino | Slot machines, chips shuffling, ambient crowd murmur, aircon hum |
| Construction Site (Night) | Much quieter — wind, distant traffic, single security light humming |

Ambient soundscape shifts dynamically as chaos builds — individual sounds drop out and are replaced by impact sounds, alarms, and panic.

### Worker Reaction Sounds
- **Normal state:** Role-appropriate ambient chatter, footsteps, task sounds
- **Noticing something suspicious:** Confused murmur, brief pause in activity
- **Panic:** Escalating yells, screams, running footsteps
- **Incident:** Distinct per-incident audio — see below

**Archetype-specific audio flavor (not named characters — per archetype):**
- The Screamer: Ear-splitting shriek that audibly draws other workers
- The Oblivious One: No reaction sounds until the last possible moment, then profound surprise
- The Hero: Concerned shout of "I've got it!" right before triggering the same trap
- The Paranoid One: Anxious muttering that builds before they flee
- The Clumsy One: Constant minor fumbling sounds during normal operation
- The Phone Addict: Faint tinny phone audio audible during normal operation, cuts out on incident
- The Denier: "It's fine, it's absolutely fine" energy in voice tone before walking back into hazard

### Incident & Accident Sounds
- Exaggerated cartoon physics sounds — boings, crashes, squelches, whistles, slides
- Satisfying impact and destruction sounds calibrated to incident scale
- Small incident: compact, punchy sound
- Large incident: full layered audio event with impact, secondary effects, and resolution sound
- Chain reaction audio layering: each step of the chain has its own sound trigger, building on the previous — the audio tells the chain reaction story

**Specific notable sounds:**
- Crocodile moat: satisfying snap, brief pause, splash
- Grand piano falling: classic descending piano chord glissando on the way down, enormous crash on impact
- Velociraptor: distinct from all other animals. The report will note "unusual vocalizations"
- Geese: exactly as terrifying as they are in real life. Players should feel genuine alarm
- Pterodactyl: prehistoric screech that echoes across the whole map
- EMP device: brief high-pitched whine, then total silence as all electronic sounds cut out simultaneously — very effective
- Bear in bathroom: muffled sounds of something deeply wrong, then door opening

### Animal Audio
Animals are active hazards with semi-random behavior — their audio reflects this:
- Animals have distinct audio signatures that alert nearby workers before visual contact
- Animal audio spreads panic independent of visual range — the sound of geese approaching is itself a hazard
- Animals interacting with other traps produce combined audio events — crocodile + electrical hazard produces a sound the safety report declines to describe

### Inspector Audio
- **Spawn sting:** Alarm-dressed-as-corporate-notification — the sound of a KPI dashboard alert, not a police siren
- **Active patrol:** Purposeful footsteps, clipboard sounds, professional muttering
- **Disabling a trap:** Satisfied corporate sound — "issue logged and resolved"
- **Triggering a trap:** Full incident audio plus a beat of silence, then the inspector's own surprised reaction
- **Inspector caught:** Special audio moment — triumphant sting plus the sound of paperwork going everywhere

### Manager / Escalation Audio

Each stage of the Manager escalation ladder has distinct audio:

| Stage | Audio |
|-------|-------|
| Manager investigating | Authoritative footsteps, concerned muttering, clipboard flipping |
| Manager near-miss | Sharp intake of breath, brief pause, then retreating footsteps |
| Stage 2 — Backup arrives | Door opening, multiple sets of footsteps, hushed urgent conversation |
| Stage 2 — Group near-miss | Multiple sharp reactions, overlapping concerned voices |
| Stage 3 — Authorities called | Phone dial tone, brief call, then distant siren growing closer |
| Authorities arrive | Hard stop audio sting — the shift is over |

### Persistent Trap Audio
Unresolved traps remaining between shifts have a subtle ambient audio tell during the next shift's setup phase:
- Low Suspicion leftover: very faint hum or drip — easy to miss
- Medium Suspicion leftover: more noticeable ambient sound — a slight electrical buzz, a creak
- High Suspicion leftover: clearly audible to attentive players — something is obviously not right

This audio layer is heard only during setup phase and fades when simulation begins.

### UI & Feedback Audio
- Corporate "ding" for positive meter changes and placements
- Warning tones as PD meter rises through thresholds — each threshold (25%, 50%, 75%, 100%) has its own escalating alert tone
- Star reveal sounds on debrief — individual ding per star earned
- Milestone completion: distinct satisfying chime separate from star sounds
- Menu navigation: clean, corporate click sounds

---

## Audio Progression During a Shift

```
Shift Start
└── Clean corporate ambient soundscape
    └── Hazard placement confirmation sounds (setup phase)
        └── Simulation begins — ambient sound + worker routines
            └── First incident — audio event, worker reactions, PD meter ding
                └── Music begins shifting (PD 25%+)
                    └── Escalating incidents — layered audio, rising panic sounds
                        └── PD 75%+ — music fully unhinged, overlapping chaos audio
                            └── Inspector spawn sting (if PD maxes)
                                └── Shift end state audio
                                    └── Debrief — triumphant/deflated based on star rating
```

---

## Technical Implementation

### Godot Audio Architecture
- **Adaptive music system:** Godot Audio Buses with parameter-driven transitions tied to PD meter value
- **Dynamic sound layering:** Chaos level drives ambient mix — individual environment sounds fade as destruction sounds increase
- **Audio bus structure:**
  - Music Bus (with adaptive layering)
  - Ambient Bus (environment-specific, fades during high chaos)
  - SFX Bus (incidents, physics, UI)
  - Voice Bus (worker reactions, archetype lines)
  - UI Bus (separate from gameplay audio for consistent volume)

### Voice Lines
- Archetype-specific voice lines recorded with multiple emotional states per archetype
- States needed per archetype: Idle, Suspicious, Panicking, Incident, Post-incident
- Lines should be brief and punchy — these play over active chaos
- Corporate deadpan tone for worker "normal" state lines
- Escalating absurdity as panic level increases

### Mobile Optimization (Android)
- Compressed audio assets — OGG Vorbis for music, WAV for short SFX
- Lower simultaneous channel count than PC — prioritize incident and voice sounds over ambient
- Music adaptive system simplified for lower-end devices — fewer simultaneous layers
- Audio ducking when multiple sounds play simultaneously — prevent muddiness
- Test audio mix specifically on phone speakers (not just headphones) — most mobile players use speakers

### Speed Control Audio Handling
- All audio time-stretches with simulation speed
- At 1x: all audio plays normally
- At 4x–16x: subtle pitch elevation, still intelligible
- At 64x: deliberate chipmunk effect — played for comedy, not realism
- Pause: all gameplay audio fades to near-silence within 0.5 seconds

---

## Cosmetic Audio Unlocks (Track 4 — Sound Packs)

Six sound packs unlocked by cumulative star total. Full Track 4 unlock schedule in `Progression_and_Scoring.md`.

| Pack | Description | Unlocks At |
|------|-------------|------------|
| Evil Laugh Pack | Alternate placement confirmation sounds featuring increasingly theatrical villain laughs | 5 stars |
| Corporate Jargon Pack | Worker ambient lines replaced with impenetrable business speak ("synergizing the vertical" right before walking into a trap) | 25 stars |
| Silent Film Pack | All voice lines replaced with dramatic piano accompaniment and title cards | 60 stars |
| Nature Documentary Pack | Hushed reverent narration describing each incident, procedurally generated from incident type | 120 stars |
| Dramatic Orchestral Pack | All sound effects replaced with full orchestral equivalents. The grand piano falling has a full string section | 180 stars |
| Retro Arcade Pack | 8-bit sound effects throughout — prestige unlock beyond max gameplay progression | 250 stars |

---

*This is the canonical audio direction reference. Cross-reference Time_Simulation.md for speed control behavior, Art_Bible.md for visual direction, and Progression_and_Scoring.md for cosmetic unlock details.*
