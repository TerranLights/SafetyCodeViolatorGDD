# Sound_and_Music_Direction
This audio direction will make the game *feel* as funny as it plays.

## Overall Audio Philosophy
Cheerful corporate energy that slowly descends into comedic chaos. Sound design is a major source of humor.

## Music

### Hub / Menu Music
- Upbeat, slightly sinister corporate elevator music
- Think “smooth jazz with a hint of evil”

### In-Game Shift Music
- Starts very clean and motivational (think stock training video music)
- Gradually becomes more unhinged as chaos increases:
  - More percussion and distorted instruments
  - Tempo increases slightly with time speed
  - Final minutes can turn into frantic, comedic action music

### Highlight Reel Music
- Triumphant, over-the-top victory fanfares mixed with cartoonish stings

## Sound Effects

### Hazard Placement
- Satisfying “clicks”, “beeps”, and corporate-sounding confirmations
- Subtle evil chuckle on particularly nasty placements (optional toggle)

### Worker Sounds
- Normal chatter, phone calls, typing, coffee slurping
- Increasing panic yells, screams, and ironic last words as things go wrong
- Distinct voice lines per personality (Kevin’s confused “whoa!”, Karen’s outraged “This is unacceptable!”)

### Accident Sounds
- Exaggerated cartoon physics sounds (boings, crashes, squelches, whistles)
- Satisfying impact and destruction sounds
- Chain reaction audio layering (one sound triggers the next)

### UI & Feedback
- Corporate “ding” for meter changes
- Warning tones as Plausible Deniability rises
- Big, bombastic sounds for highlight reel moments

## Audio Progression During a Shift
1. **Early Shift** — Calm, professional ambience
2. **Mid Shift** — Rising tension, more impacts and yells
3. **Peak Chaos** — Layered destruction, overlapping screams, music going off the rails
4. **Debrief** — Triumphant, celebratory tone

## Technical Notes
- Adaptive music system (Godot Audio buses + parameters)
- Dynamic sound layering based on chaos level
- Voice lines recorded with multiple emotional states
- Mobile optimization: lower channel count, compressed assets
