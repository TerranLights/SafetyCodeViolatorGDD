# Art Bible & Style Guide — Safety Code Violator

**Safety Code Violator GDD**
*Consolidated reference for all visual direction, character design, environment art, UI style, and technical art specifications.*

---

## Confirmed Visual Direction

**Style:** Stylized cartoon 2D
**Camera:** Isometric top-down
**Engine:** Godot (Steam + Android)
**Tone:** Clean, bright, and comedic — never grim or photorealistic

---

## 1. Overall Visual Philosophy

The core visual tension of Safety Code Violator is the contrast between **pristine corporate professionalism** and **glorious destructive chaos**. The art should always feel fun and comedic. The world starts clean, orderly, and almost sterile. By the end of a good shift it looks like a disaster zone. This contrast is the visual joke.

**Design principles:**
- Strong readability at all times — players need to understand what's happening at a glance, especially on mobile
- Bright, saturated colors during normal operation
- Increasing visual chaos and particle density as disasters unfold
- Strong silhouettes and readable shapes — critical for isometric scale where workers are relatively small
- Exaggerated animations for deaths, reactions, and chain reactions
- The art should never make the player feel bad — cartoon violence only, comedic framing always

**Tone References:**
- *Untitled Goose Game* — readability, mischief, clean cartoon world that accepts chaos naturally
- *Overcooked* series — busy but always readable chaos, strong color coding, mobile-friendly clarity
- Corporate HR training videos — the UI aesthetic specifically. Clean, authoritative, deeply ironic given the content

---

## 2. Camera & Presentation

**Camera type:** Isometric top-down
**View angle:** Standard isometric — overhead enough to see full floor layouts clearly, angled enough to show vertical elements (scaffolding, shelves, multi-level structures)

**Camera behavior:**
- Smooth zoom and pan during setup and simulation phases
- Dramatic slow-motion camera during highlight moments and chain reaction peaks
- Dynamic camera shake and particle focus on big impacts and combos
- Highlight reel playback uses film-strip style framing with high contrast and bloom effects

**Isometric-specific design notes:**
- All environmental elements must read clearly from directly above at slight angle
- Vertical elements (scaffolding, shelving, cranes) need strong silhouettes visible from isometric perspective
- Worker characters must be immediately identifiable by silhouette and color at small isometric scale — facial expressions are secondary to overall shape and color coding

---

## 3. Color Palette

### Base Corporate Palette (Start of Shift)
The world looks professional, clean, and safe. The irony is intentional.

- **Backgrounds:** Soft cool grays, teals, light blues
- **Accents:** Corporate green (#00A86B), orange highlights (#FF6B00)
- **Characters:** Bright, distinct colors per role — see Role Color Coding below
- **Overall feel:** A workplace that has never had a single incident. Until now.

### Chaos Escalation Palette
As incidents accumulate, the world's color temperature shifts toward warm chaos.

- **Minor chaos:** Papers flying, small spills — subtle warm color introduction
- **Medium chaos:** Increasing oranges and yellows, light smoke, sparks
- **Heavy chaos:** Reds, fire, thick dark smoke with glowing orange/red edges, spilled colorful liquids, scorched browns and blacks
- **UI escalation:** PD meter shifts Green → Yellow → Orange → Red as it fills

### UI Colors
- Clean dark blue/gray panels with bright accent colors
- Blues, greens, and grays in normal state
- Red and orange accents for danger states
- Subtle scanline or digital display effects on meters — corporate safety dashboard aesthetic
- Plausibility Meter styled as a safety monitoring dashboard that becomes increasingly alarming

---

## 4. Character Design Guidelines

### Proportions
- **Standard cartoon proportions** — no exaggerated big heads
- Characters should be readable and expressive without distorted proportions
- At isometric scale, silhouette clarity matters more than facial detail

### Silhouettes
- Strong, clear outlines so workers are recognizable even when small on screen
- Each archetype should have a distinct silhouette readable at isometric zoom level
- Role color coding reinforces silhouette recognition — see below

### Role Color Coding
Workers are visually identifiable by role at a glance:

| Role | Visual Style |
|------|-------------|
| Interns | Bright hoodies, casual clothes, slightly too-large lanyards |
| Middle Managers | Button-up shirts, ties, clipboard or phone always present |
| Factory/Site Workers | Hard hats, high-vis vests, work boots |
| Chefs/Kitchen Staff | White uniforms with stains that accumulate during chaos |
| Office Workers | Business casual, varying colors per archetype |
| Security Staff | Dark uniforms, utility belt |
| Medical Staff | Scrubs, lanyards |
| The Manager (special) | Visually distinct from regular workers — slightly larger presence, better clothes |
| Safety Inspector (special) | High-vis vest, clipboard, officious expression |

### Shading
- Cel-shaded with soft gradients
- Subtle rim lighting for isometric depth
- Normal maps / lighting tricks where needed for environmental depth

### Animations
- Expressive reactions (confusion, panic, smugness, obliviousness)
- Over-the-top cartoon ragdoll deaths — flailing limbs, spin, exaggerated bounce
- Personality-specific idle and walk cycles per archetype
- Fix-it behavior animations — workers approaching and interacting with suspicious equipment
- Satisfying "thud" and crash sounds paired with visual feedback on every impact

---

## 5. Environment & Props

### Start State
Clean, orderly, almost sterile. Every workplace looks like it passed its last inspection with flying colors. The contrast with what's about to happen is the visual setup for the joke.

### Destruction Layers
Environments have progressive destruction states that accumulate during simulation:

| Layer | Visual Elements |
|-------|----------------|
| **0 — Pristine** | Clean, orderly, no damage |
| **1 — Minor** | Papers and small objects displaced, minor spills, small scuffs |
| **2 — Medium** | Broken objects, visible cracks, light smoke, sparks, larger spills |
| **3 — Heavy** | Toppled furniture, fire, structural damage, thick smoke, debris everywhere |

Destruction is modular — individual elements can be in different damage states simultaneously. A pristine break room next to a completely destroyed open-plan workspace is both visually readable and funny.

### Props
- Highly readable icons and outlines on all interactive objects
- Cartoonish prop details that telegraph their danger — coffee machine with faintly evil-looking steam, filing cabinet visibly straining under its load, scaffolding plank that is clearly not load-bearing
- Clear "armed," "triggered," and "neutral" visual states for player-placed traps — critical for gameplay readability
- "Broken" states with sparks, leaks, and wobbling animations

### Trap Visual States
All player-placed traps must have three clearly distinct visual states readable at isometric scale:

| State | Visual Treatment |
|-------|-----------------|
| **Neutral** | Object looks normal — only subtle tells for attentive players |
| **Armed** | Subtle glow, slight animation, or indicator visible to player but not obviously alarming |
| **Triggered** | Full activation visual — particles, sound, animation |

The gap between Neutral and Armed should be small enough to maintain plausible deniability visually — if a trap looks obviously dangerous, it should contribute more to the PD meter accordingly.

---

## 6. Effects & VFX

### High Priority Particles
- Sparks and flying debris
- Liquid splashes (water, coffee, industrial chemicals — all color coded)
- Smoke plumes that grow and darken with chaos level
- Fire with glowing embers
- Screen shake on big impacts
- Bloom effects on explosions and high-energy events
- Slow-motion emphasis and particle focus during highlight moments

### Ragdoll & Physics
- Juicy, cartoon-style ragdolls on every incident
- Exaggerated bounce and spin — more cartoon than realistic
- Workers should look like they're having the worst day of their lives in the funniest possible way
- Chain reaction visual clarity — each step of a chain should be visually distinct and readable

---

## 7. UI / HUD Style

**Overall aesthetic:** Corporate HR training video. Clean, authoritative, slightly dated. The UI treats devastating workplace incidents as productivity metrics.

### Key UI Elements

**Plausibility Deniability Meter**
- Styled as a safety monitoring dashboard
- Color shifts Green → Yellow → Orange → Red as it fills
- At maximum, triggers a visual alarm state before inspector spawns
- Should feel like a corporate KPI dashboard becoming increasingly alarming

**Setup Phase UI**
- Clean overlay showing available loadout, placement budget, and per-type limits
- Trap placement indicators clearly visible on isometric map
- Large, finger-friendly touch targets for Android — minimum tap area 44x44dp

**Simulation Phase UI**
- Working Day Timer visible and readable at all times
- Speed control buttons prominent and touch-friendly
- PD meter always visible
- Minimal clutter — the simulation is the main event

**Debrief Screen**
- Film-strip style framing for highlight reel moments
- Corporate tone throughout — incidents described as "productivity events" and "equipment anomalies"
- Star rating presented with appropriate corporate fanfare
- "Most Valuable Victim," "Best Combo," "Insurance Money Saved" presented as positive KPIs

### Typography
- Clean sans-serif fonts throughout
- Corporate weight and spacing — this is a professional safety management application
- Danger states use bold weight and red/orange color only — not different fonts

---

## 8. Technical Art Specifications

### File Standards
- **Format:** PNG with transparency
- **Resolution:** Work at 2x–4x for crisp scaling across screen sizes
- **Normal maps:** Separate normal/specular maps for environmental elements requiring depth
- **Sprites:** Hand-drawn 2D with normal mapping for isometric depth where needed

### Performance (Android Priority)
- Texture atlases for all sprite sheets
- Object pooling for particle systems — smoke, sparks, debris
- LOD (Level of Detail) for distant workers — simplified sprites at zoom-out
- Godot-optimized asset pipeline throughout
- Particle density scales with device performance tier

### Android-Specific
- All interactive elements meet minimum touch target sizing (44x44dp minimum)
- UI scales cleanly across common Android screen ratios
- No UI elements in bottom 15% of screen (thumb rest zone)
- Color choices tested for readability in outdoor/bright ambient light conditions

### Isometric-Specific
- All tile-based map elements constructed on isometric grid
- Worker sprites oriented for isometric perspective — not purely top-down
- Vertical elements (shelving, scaffolding, multi-floor structures) use consistent depth cues
- Shadow casting consistent across all environmental elements

---

## 9. Visual Priorities by Development Phase

**Phase 1 (Demo / Construction Site):**
- Core worker silhouettes and role color coding
- Construction Site environment set — pristine and destruction layers 1-2
- Trap neutral/armed/triggered states
- Core particle effects (sparks, debris, smoke)
- HUD and PD meter
- Basic ragdoll

**Phase 2 (Full release environments):**
- Full destruction layer 3
- Per-environment prop sets and color palettes
- Full particle library
- Highlight reel camera and film-strip UI
- Debrief screen full design
- Advanced ragdoll variations per incident type

**Phase 3 (Polish):**
- Slow-motion effects and bloom
- Screen shake tuning
- Cosmetic unlock visuals
- Per-archetype idle and walk cycle variations
- Environmental ambient animations (flickering lights, steam, wind)

---

## Conflicts Resolved From Prior Drafts (Grok)

| Element | Resolution |
|---------|-----------|
| Big heads / exaggerated proportions | Removed — confirmed standard cartoon proportions. Silhouette clarity prioritized instead |
| 2.5D angled view 35-40° | Replaced with confirmed isometric top-down |
| Hades / Spiritfarer as tone references | Removed — wrong tone. Untitled Goose Game and Overcooked kept as better fits |
| Everything else | Kept and expanded |

---

*This is the canonical art direction reference. Art_Bible.md and Art_Style_Guide.md have been consolidated here. Both originals can be discarded.*
