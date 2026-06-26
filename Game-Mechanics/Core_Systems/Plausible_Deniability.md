# Plausible Deniability System

**Safety Code Violator GDD**
*The core tension mechanic. Causing chaos is easy — causing chaos that looks like a series of unfortunate accidents is the skill.*

---

## Overview

The **Plausible Deniability (PD) Meter** is the primary tension system in *Safety Code Violator*. It tracks how suspicious your handiwork looks to the Safety Inspector. Pure chaos is always available to you — but smart, subtle chaos is where the high scores live.

---

## Meter Basics

- **Range:** 0% – 100%
- **Starting value:** 0% at the beginning of every shift — unless unresolved traps from previous shifts are carrying over, in which case it refills immediately based on accumulated passive suspicion. See `Shift_and_Level_Structure.md` for the persistent trap PD accumulation rules.
- **At 100%:** The Safety Inspector spawns on site and begins neutralizing your traps. This is a pressure event, not a hard fail — stars earned up to that point are kept regardless of what happens next.

**The hard fail condition is separate:** Manager escalation Stage 3 (Authorities Arrive), which is triggered by the Manager's own escalation ladder — not by the PD meter. See `Manager_Behavior.md` for full details.

---

## How the Meter Changes

**Increases (Raises Suspicion):**
- Incidents caused by High Suspicion hazards — these are obviously intentional and spike the meter significantly per event
- Incidents caused by Medium Suspicion hazards — deniable but questionable, moderate PD contribution
- Repeated incidents of the same type in a short window — patterns attract attention
- Workers with high Suspicion Sensitivity noticing and reporting sabotage (Paranoid One, Health and Safety Rep)
- The Safety Inspector arriving and observing active traps directly

**Decreases / Keeps Low:**
- Using Low Suspicion hazards — each incident contributes minimally to the meter
- Mixing many different hazard types — varied incidents read as unrelated bad luck rather than a pattern
- Chain reactions that read as cascading workplace accidents rather than deliberate sabotage — a long low-suspicion chain keeps the meter low while maximizing chaos score
- Workers attempting to "fix" something and triggering it themselves — looks like operator error, not sabotage

---

## Suspicion Tiers

Every hazard is assigned a suspicion tier that determines its PD contribution per incident. Full hazard list with tiers in `Master_Hazards.md` and `Hazard_Inheritance_System.md`.

| Tier | PD Contribution Per Incident | Notes |
|------|------------------------------|-------|
| Low Suspicion | Minimal | Looks like a workplace accident. Use freely |
| Medium Suspicion | Moderate | Deniable but will accumulate. Use deliberately |
| High Suspicion | Significant | Obviously intentional. Use sparingly or as a chain reaction endpoint |

---

## Strategic Layers

**Short-term — managing the current shift:**
- Keep the PD meter below 50% to qualify for 5-star ratings
- Keep it below 75% for 3-star minimum
- Inspector spawn at 100% ends your setup advantage — prioritize low-suspicion chains
- Catching the Inspector and Manager in traps generates PD — doing both while staying under 50% is the core mastery challenge

**Long-term — managing across multiple shifts:**
- Unresolved traps left on the map carry passive PD accumulation into subsequent shifts
- Accumulating too many leftover traps across multiple shifts can cause a new shift to begin with the Inspector already on site (75%+ starting PD threshold)
- See `Shift_and_Level_Structure.md` for full persistent trap mechanics

---

## UI Representation

- Visible meter in the corner of the screen throughout simulation
- Color coded: Green → Yellow → Orange → Red
- Warning indicator when approaching critical threshold
- "Close Call" visual highlight when you barely stay under the limit

---

## Interaction with Other Systems

- **Scoring:** Final PD meter percentage feeds directly into the Plausibility Rating scoring axis, which acts as a multiplier on Chaos Score. High chaos with high plausibility is the ideal run. See `Progression_and_Scoring.md`.
- **Star Ratings:** PD ceiling is a hard requirement for upper star tiers — PD above 75% caps you at 2 stars regardless of other performance.
- **Manager Escalation:** The Manager's escalation ladder runs completely independently from the PD meter. Both systems can be active simultaneously — a maxed PD meter brings the Inspector while the Manager escalation ladder runs in parallel. See `Manager_Behavior.md`.
- **Persistent Traps:** Unresolved traps from prior shifts add passive PD before the new shift even begins. This is the only source of above-zero starting PD. See `Shift_and_Level_Structure.md`.
- **Worker Archetypes:** The Paranoid One and Health and Safety Rep are the most dangerous workers for PD accumulation — both notice suspicious setups and can report them, accelerating meter fill before any incident even occurs.

---

## Conflicts Resolved From Prior Draft

| Element | Resolution |
|---------|-----------|
| Starting value varies by contract difficulty | **Removed** — no contract system. Starting value is 0% unless persistent traps carry PD forward |
| Reaching 100% = "you get fired / level failed" | **Corrected** — 100% PD spawns the Inspector (pressure event). Hard fail is Manager escalation Stage 3 only |
| Long-term reputation track across contracts | **Removed** — no contract or reputation system. Long-term PD consequence is persistent trap accumulation only |
| Reputation Decay mechanic | **Removed** — explicitly cut from design |
| Alibi System (fake training sessions, scapegoats) | **Unconfirmed** — not in current GDD. Flagged as potential future mechanic only |
| Investigator Personalities | **Unconfirmed** — not in current GDD |
| Timing-based suspicion (accidents too early in shift) | **Removed** — PD is driven by hazard suspicion tiers and incident patterns, not shift timing |
