# Art Bible - Safety Code Violator

**Chosen Direction**: Stylized 2.5D / Pseudo-3D Cartoon  
**Camera**: 2.5D Angled View (~35–40° tilt)

## 1. Overall Visual Philosophy

- Bright, clean, and highly readable cartoon style with subtle 3D depth.
- Strong contrast between "pristine corporate professionalism" and "glorious destructive chaos".
- The art should always feel **fun and comedic**, never grim or photorealistic.
- Goal: Make cartoon violence feel satisfying and hilarious.

**Tone Reference**: 
- *Untitled Goose Game* (readability + mischief)
- *Hades* / *Spiritfarer* (stylized 2.5D depth)
- *Overcooked* series (busy but clear chaos)

## 2. Color Palette

**Base Corporate Palette (Start of Shift)**
- Main Background: Soft cool grays, teals, light blues
- Accents: Corporate green (#00A86B), orange highlights (#FF6B00)
- Characters: Bright, distinct colors per role

**Chaos Escalation Palette**
- Increasing warm tones: oranges, reds, yellows
- Smoke: dark grays with glowing orange/red edges
- Fire & Sparks: vibrant yellow → orange → red
- Destruction: browns, scorched blacks, spilled colorful liquids

**UI Colors**
- Clean dark blue/gray panels with bright accent colors
- Plausibility Meter: Green → Yellow → Orange → Red

## 3. Character Design Guidelines

- **Proportions**: Slightly exaggerated heads (big heads, smaller bodies) for readability and expression.
- **Silhouettes**: Strong, clear outlines so workers are recognizable even when zoomed out.
- **Shading**: Cel-shaded with soft gradients + subtle rim lighting for 2.5D depth.
- **Animations**:
  - Expressive faces (confusion, panic, smugness, irony)
  - Over-the-top ragdoll deaths with flailing limbs and spin
  - Personality-specific idle and walk cycles

**Role Color Coding Examples**
- Interns: Bright hoodies / casual clothes
- Managers: Button-up shirts + ties
- Factory Workers: Hard hats + high-vis vests
- Chefs: White uniforms with stains that grow during chaos

## 4. Environment & Props

- **Start State**: Clean, orderly, almost sterile corporate/industrial look.
- **Destruction Layers** (progressive):
  1. Minor (papers, small spills)
  2. Medium (broken objects, cracks, smoke)
  3. Heavy (toppled furniture, fire, structural damage)
- Modular pieces so destruction feels dynamic.
- Strong vertical readability (shelves, cranes, scaffolding).

## 5. Effects & Destruction

**High Priority Particles & VFX**
- Sparks, flying debris, liquid splashes
- Smoke plumes that grow with chaos
- Fire with glowing embers
- Screen shake + bloom on big impacts
- Slow-motion emphasis during highlight moments

**Ragdoll & Physics**
- Juicy, cartoon-style ragdolls
- Exaggerated bounce and spin on deaths
- Satisfying "thud" and crash sounds paired with visual feedback

## 6. UI / HUD Style

- Corporate / HR training video aesthetic (clean sans-serif fonts, subtle shadows)
- Plausibility Meter should feel like a "safety dashboard" that gets increasingly alarming
- Large, finger-friendly buttons for Android
- Highlight Reel UI: Dramatic, celebratory, with film-strip style framing

## 7. Technical Art Specifications

- **Art Style**: Hand-drawn 2D sprites with normal maps / lighting tricks for 2.5D depth
- **Resolution**: Work at 2x–4x resolution for crisp scaling
- **Performance**:
  - Texture atlases
  - Object pooling for particles
  - LOD (Level of Detail) for distant workers
- **File Format**: PNG with transparency + separate normal/specular maps where needed

---

**This Art Bible** gives us a clear, consistent target we can reference while making assets.
