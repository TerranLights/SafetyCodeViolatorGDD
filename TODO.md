# TODO — Safety Code Violator GDD

*Prioritized list of outstanding tasks across the design document. Updated as items are completed or new issues are identified.*

---

## TIER 1 — Fix Now ✓ COMPLETE
*Active documents with confirmed errors or stale content that needs correcting before anything else.*

- [x] **`README.md`** — Updated gameplay loop bullet to reflect confirmed sandbox design; removed contract briefing language.

- [x] **`Game-Mechanics/Core_Systems/Hazard_System.md`** — Fully rewritten as a clean overview doc: confirmed three-tier structure, confirmed suspicion tiers, confirmed hazard properties, setup-phase-only placement rules, progression system reference, and cross-references to Master_Hazards.md / Hazard_Inheritance_System.md. Conflicts Resolved section added.

- [x] **`Game-Mechanics/Hazards_and_Traps/Combo_Ideas_and_Design_Rules.md`** — Fixed `Art_Bible_FINAL.md` → `Art_Bible.md`.

---

## TIER 2 — Open Design Decisions
*Questions flagged in the GDD that need a confirmed answer before implementation can proceed on those systems.*

- [ ] **Undo/Redo during setup phase** — Listed in Core_Design.md as unconfirmed. Present in early drafts and described in UI_and_Controls.md as a confirmed feature. Strong case for yes — needs locking in or out.

- [ ] **"Restart Shift with same setup" option** — QoL feature: replay a shift with identical trap placement. Not confirmed. Low implementation cost, high player value.

- [ ] **Violator Hub between shifts** — Currently player goes straight to workplace select. Early drafts had a hub space. Unconfirmed either way — needs a decision so the main menu scene can be properly scoped.

- [ ] **Worker health/resilience as a per-worker attribute** — Flagged as unconfirmed for v1. Affects how archetypes like The Lucky One and The Unlucky One behave mechanically. Needs a decision.

- [ ] **Ghost types** — `Level_Variants.md` lists four ghost types (Standard, Poltergeist, Phantom Foreman, The Whistler) but marks them all TBD. Needs expanding into the same detail level as worker archetypes.

- [ ] **Cosmetic unlock thresholds (Track 4)** — Progression track 4 exists and the cosmetic categories are listed, but the specific star thresholds for each unlock are not defined. Needs filling in once content is finalised.

- [ ] **Controller support on PC** — Mentioned as secondary target in Platform_and_Technical.md but unconfirmed. Affects input architecture decisions.

- [ ] **New Game+** — Flagged in Level_Progression.md as unconfirmed. Low priority for v1 but worth deciding so it doesn't get accidentally designed around.

- [ ] **Android cloud saves** — Local saves confirmed. Google Play Games cloud sync is TBD.

---

## TIER 3 — Missing Documents
*Systems that are referenced throughout the GDD but have no dedicated document.*

- [ ] **Safety Inspector behavior document** — The Inspector is one of the three major active threats in the game (alongside the Manager and the PD meter) and is referenced constantly across the GDD, but has no dedicated document. Manager_Behavior.md covers the Manager in full detail — the Inspector deserves the same treatment. Needs to cover: spawn conditions, patrol behavior, trap detection range, trap disabling behavior, how it interacts with workers and animals, what happens when it triggers a trap, and how it can be caught.

- [ ] **Level design docs for remaining workplaces** — Construction Site and Office Building have full canonical level documents. All other 38+ planned workplaces need the same treatment (zones, trap slots, worker mix, milestone tree, strategic notes). Suggested priority order based on design distinctiveness:
  1. Restaurant / Kitchen
  2. Factory
  3. Hospital
  4. Casino
  5. Space Station
  6. Then remaining environments from `Planned_Workplaces.md`

- [ ] **Style / Irony Bonus — definition doc or section** — Listed as a scoring axis in `Progression_and_Scoring.md` and referenced in combo design, but never precisely defined. What specifically triggers it? How is it detected by the game? Needs a clear definition before implementation.

- [ ] **Weekly Challenge Shifts — design doc** — Confirmed as a feature in the progression system (earns bonus stars, optional, never required) but never designed in detail. Needs: how shifts are curated, how often they rotate, how they're presented to the player, and how they fit into the save system.

---

## TIER 4 — Low Priority / Polish
*Items that can wait until active development begins or until the relevant system is being built.*

- [ ] **Portal destinations** — `Hazard_Inheritance_System.md` lists "Portal" as a Universal hazard with "Destination TBD per level." Each level doc can define this when that level's doc is written.

- [ ] **Ambiguous hazard descriptions** — A handful of entries in `Hazard_Inheritance_System.md` have placeholder descriptions ("nature of replacement TBD", "nature of experiment: TBD", "nature of evidence: TBD"). Fine to leave until those specific levels are being designed.

- [ ] **Milestone star weighting review** — With 15 milestones × 26 stars × 40+ workplaces = 1,040+ milestone stars available vs a 200+ star progression cap, milestone stars alone far exceed what's needed to max progression. Consider whether some lower-tier milestones should reward badge progress only (no stars), reserving star rewards for the harder ones. Not urgent — can be tuned during playtesting.

- [ ] **Combo doc — add combos for new environments** — `Combo_Ideas_and_Design_Rules.md` currently has examples for Construction Site, Office, Restaurant, Hospital, and Space Station. As new level docs are written, corresponding combo examples should be added here.

---

## COMPLETED
*For reference — tasks resolved during the June 2026 GDD audit session.*

- [x] Plausible Deniability doc — removed contract references, corrected fail state, removed reputation/rank systems
- [x] Godot Architecture doc — removed ViolatorHub/contract board, renamed `resources/contracts/` → `resources/workplaces/`, added ShiftManager singleton, expanded singleton descriptions
- [x] UI & Controls doc — removed contract/rank/reputation framing, rewrote Briefing Screen, removed mid-simulation intervention tools from Simulation Phase UI
- [x] Sound & Music doc — fixed non-existent speed tiers (2x, 8x, 32x → confirmed 1x/4x/16x/64x), fixed self-referential consolidation note
- [x] Cross-reference filename sweep — corrected `_FINAL` suffixes and camelCase names across all active docs (8 incorrect patterns, 63 instances fixed)
- [x] Milestone count — locked at 15 per workplace across all docs (was inconsistently "10–15" in some places)
