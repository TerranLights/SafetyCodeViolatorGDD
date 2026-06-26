## 2. Art Direction (Expanded for 2.5D Angled View)

### Overall Visual Philosophy
**Bright, clean, cartoonish corporate satire** that deliberately contrasts with the growing destruction. The game should look professionally cheerful at the start of every shift — then devolve into glorious, colorful mayhem.

**Reference Vibes**: 
- *Untitled Goose Game* (clean, readable cartoon style)
- *The Sims* (expressive characters + destructible environments)
- *Overcooked* / *PlateUp!* (busy but readable kitchen chaos)
- Corporate training video aesthetic gone wrong

### Camera & View-Specific Requirements
- **2.5D Angled View** (~35–40° tilt)
- Assets must look good from this fixed angle with some perspective depth
- Strong silhouettes and clear outlines so everything remains readable when zoomed out
- Verticality matters — falling objects, collapsing shelves, and multi-level chaos must look dramatic

### Color Palette
**Starting State (Professional)**
- Corporate blues, soft teals, light grays, clean whites
- Accents of corporate green and orange

**Escalating Chaos**
- Increasing warm tones: oranges, reds, yellows
- Smoke, sparks, fire glow, emergency lighting
- puddles, oil spills, and scorch marks add visual texture

**UI Colors**
- Clean corporate blues/grays with red/orange warning accents for the Plausibility Meter

### Character Art Style
- **Stylized cartoon** with exaggerated proportions (larger heads, expressive faces)
- Strong color coding by role (Intern = bright hoodie, Manager = tie + button-up, Chef = dirty apron, etc.)
- **Key Animations**:
  - Normal working routines (typing, carrying, chatting)
  - Reactive expressions (confusion, panic, smugness)
  - Over-the-top ragdoll deaths with flailing limbs and spin effects
  - Personality-specific walks and idle behaviors

### Environment & Destruction
- **Before**: Pristine, orderly, almost sterile
- **During**: Progressive destruction layers (papers flying, cracks, spills, smoke)
- **After**: Gloriously messy — broken glass, toppled shelves, burn marks, caution tape everywhere

**Hazard Visual Design**
- Highly readable icons + states (normal → damaged → destroyed)
- Satisfying particle effects (sparks, liquid splashes, dust clouds, flying debris)
- Clear “before and after” states for easy player feedback

### Lighting & Effects
- Dynamic lighting that reacts to chaos (emergency strobes, fire glow, flickering bulbs)
- God rays / volumetric dust in construction sites and factories
- Screen shake + bloom during big explosions/combos
- Highlight Reel mode: dramatic lighting, slow-motion, vignette, and particle emphasis

### Technical Art Requirements
- 2D sprites with normal maps for subtle 2.5D depth
- Modular environment pieces (easy to destroy/rearrange)
- Particle systems heavily used for destruction and comedy
- Optimized for Android (texture atlases, LOD for distant workers)
- Scalable UI that works at different zoom levels

### Tone Consistency Rules
- Violence must always feel **cartoonish and slapstick** — never graphic or disturbing
- Use squash & stretch, exaggerated physics, and bright colors to keep everything fun
- Humor comes from contrast: professional setting vs absurd disaster

---

**Status**: This gives us a clear, consistent visual target we can reference when creating assets or choosing style for prototypes.
