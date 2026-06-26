# The Manager — Behavior & Escalation System

**Safety Code Violator GDD**
*The Manager is a special high-value worker archetype present in every workplace environment. The name and appearance change per environment but the underlying behavior system is identical across all levels.*

---

## The Manager Concept

"The Manager" is the construction site flavor name. Every workplace has an equivalent — a senior figure who runs the location, is worth significant bonus points if caught, and whose behavior creates the game's primary escalation threat.

### Workplace Equivalents

| Environment | Manager Title |
|-------------|---------------|
| Construction Site | Foreman |
| Office | Middle Manager / Department Head |
| Restaurant / Kitchen | Head Chef / Shift Manager |
| Fast Food | Store Manager |
| Hospital | Head Nurse / Chief of Medicine |
| Casino | Pit Boss |
| Nuclear Power Plant | Plant Supervisor |
| Zoo | Zookeeper Supervisor |
| Carnival | Carnival Manager |
| Space Station | Mission Commander |
| Factory | Floor Supervisor |
| Chemical Plant | Safety Officer (ironic) |
| Retail Store | Store Manager |
| Warehouse | Warehouse Supervisor |
| Laboratory | Lead Researcher |
| Bank | Branch Manager |
| Hotel | Head Concierge / General Manager |
| Shipyard | Dock Supervisor |
| Oil Rig | Rig Foreman |
| Mine / Quarry | Mine Supervisor |
| Logging Site | Crew Chief |
| Demolition Site | Demolition Foreman |
| Junkyard | Yard Manager |
| Ski Resort | Resort Manager |
| Amusement Park / Carnival | Park Manager |
| Movie Studio | Assistant Director / Set Manager |
| Sports Stadium | Event Coordinator |
| Circus | Ringmaster |
| Funeral Home | Funeral Director |
| Brewery / Distillery | Brew Master |
| Law Firm | Senior Partner |
| Government Building | Department Director |
| Call Center | Call Center Supervisor |
| Car Dealership | Sales Manager |
| Pharmaceutical Plant | Production Supervisor |
| Veterinary Clinic | Head Veterinarian |
| Supermarket | Store Manager |
| Submarine | First Officer |
| Haunted House | Haunted House Director |
| Daycare | Head Caregiver |
| Space Station | Mission Commander |

---

## Normal Behavior

When no threat has been detected, the Manager:

- Stays near their **designated safe location** (trailer, office, break room, etc.) by default
- Periodically conducts **site walkthroughs** on a semi-fixed route covering all zones
- **Directs other workers** during walkthroughs — sending them to specific locations, which can work for or against the player depending on trap placement
- Returns to safe location after each walkthrough
- Is worth **significant bonus points** if caught during a run

---

## Investigation Triggers

Any of the following cause the Manager to leave their safe location and **investigate the site:**

- Directly witnessing an accident
- Hearing panic sounds from nearby workers (particularly The Screamer archetype)
- Noticing a suspicious trap during a walkthrough
- The Safety Inspector arriving on site

During investigation the Manager actively searches the area where the trigger occurred, moving cautiously and examining the surrounding zones.

---

## The Escalation Ladder

The Manager escalation system operates independently from the Plausible Deniability meter. It has three stages.

### Stage 1 — Manager on Alert

**Trigger:** Manager investigates and comes within the **proximity radius** of a triggered trap without being caught by it.

- "Almost hit" is defined as being within a set proximity radius of a triggered trap at the moment it activates
- The Manager does not need to visually witness the trap — proximity alone is sufficient
- Think of it as feeling the wind from the falling piano

**What happens:**
- Manager retreats immediately to their safe location
- Manager is now **wise to the player's methods** — becomes more cautious during any subsequent walkthroughs
- Manager begins **gathering backup**

---

### Stage 2 — Manager Returns with Backup

**Trigger:** Approximately **one minute of real-world time** after retreating, the Manager emerges with a backup group.

- Backup group size varies by level — not a fixed number
- Backup composition depends on workplace (security staff, HR, senior colleagues, etc.)
- Manager and backup **investigate the site together** as a group

**Escalation condition:** If more than **half the backup group** comes within the proximity radius of triggered traps without being caught, the group retreats and escalates to Stage 3.

**What happens on retreat:**
- Entire group returns to safe location
- Authorities are called

---

### Stage 3 — Authorities Arrive

**Trigger:** Manager and backup retreat from Stage 2 investigation.

- Authorities arrive on site after a short delay
- Authority type depends on workplace environment (see table below)
- **Hard fail condition** — level ends immediately and must be restarted from the beginning

**Reset behavior:** The escalation ladder resets completely on level restart. The Manager has no memory of previous attempts. Every run starts fresh.

---

## Workplace Authority Equivalents

When Stage 3 is triggered, the following authorities arrive depending on environment:

| Environment | Authorities |
|-------------|-------------|
| Construction Site | Police / OSHA Investigators |
| Office | HR Department / Employment Lawyers |
| Restaurant / Kitchen | Health Inspectors |
| Fast Food | Corporate Regional Manager + Health Inspector |
| Hospital | Medical Board / Malpractice Lawyers |
| Casino | Casino Security / FBI |
| Nuclear Power Plant | Nuclear Regulatory Commission |
| Zoo | Animal Control + Police |
| Carnival / Amusement Park | Safety Regulators + Local Police |
| Space Station | Mission Control (cuts oxygen supply) |
| Factory | Industrial Safety Board |
| Chemical Plant | Environmental Protection Agency + Hazmat Team |
| Retail Store | Corporate Loss Prevention |
| Warehouse | OSHA + Corporate Safety Team |
| Laboratory | Ethics Board + Government Regulators |
| Bank | FBI + Armed Response Unit |
| Hotel | Health and Safety Executive + Local Police |
| Shipyard | Coast Guard + Maritime Authority |
| Oil Rig | Environmental Agency + Coast Guard |
| Mine / Quarry | Mines Inspectorate |
| Logging Site | Forestry Commission + Safety Board |
| Demolition Site | Building Control Authority + Police |
| Junkyard | Environmental Agency |
| Ski Resort | Mountain Rescue + Safety Board |
| Movie Studio / Film Set | Union Representatives + Health and Safety |
| Sports Stadium | Event Safety Authority + Police |
| Circus | Animal Welfare + Safety Regulators |
| Funeral Home | Health Authority + Coroner's Office |
| Brewery / Distillery | Liquor Control Board + Safety Inspectors |
| Law Firm | Bar Association + Ethics Committee |
| Government Building | Internal Affairs + Federal Agents |
| Call Center | Corporate Compliance Team |
| Car Dealership | Trading Standards + Police |
| Pharmaceutical Plant | FDA + Hazmat Team |
| Veterinary Clinic | Animal Welfare Authority |
| Supermarket | Food Standards Agency + Health Inspectors |
| Submarine | Naval Command |
| Haunted House | Nobody is coming. You're on your own |
| Daycare | Child Services + Police |
| Space Station | Mission Control |

---

## Proximity Radius — Implementation Notes

- Exact radius values are a **playtesting and tuning decision** — not locked in at GDD stage
- The radius should feel fair and readable to the player — a near miss should look like a near miss on screen
- Consider a brief visual indicator when the Manager enters the danger radius of a triggered trap (a sweat drop, a startled expression) so the player knows they've been made
- Different trap types may warrant different effective radii — a falling piano has a wider danger zone than a loose floorboard

---

## Strategic Implications for the Player

- A trap that catches workers is good. A trap that **almost catches the Manager** is dangerous.
- Skilled players can deliberately **bait the Manager away** from their best traps by triggering a minor decoy incident elsewhere on the map
- Trapping the Manager's **safe location** is high risk, extremely high reward — if they retreat into a trapped trailer, bonus points and escalation avoided simultaneously
- The Manager's **walkthrough route** is semi-predictable — learning it and placing low-suspicion traps along it is the safest way to catch them
- During Stage 2, the **backup group moving together** creates a tempting cluster target — but catching too many of them risks triggering Stage 3 if any almost-misses occur simultaneously

---

## Interaction with Other Systems

- **PD Meter:** Manager escalation is independent of the PD meter. Both systems can be active simultaneously — a full PD meter brings the Safety Inspector while the Manager escalation ladder runs in parallel.
- **Safety Inspector:** Inspector arrival is one of the triggers for Manager investigation. Having both the Inspector and the Manager active at the same time is extremely high pressure.
- **Worker Archetypes:** The Screamer's panic call is one of the most reliable Manager investigation triggers. Place Screamers carefully. The Health and Safety Rep may proactively report suspicious activity to the Manager, accelerating their investigation.
- **Level Variants:** On Inspection Day, the Safety Inspector is already present from simulation start — this immediately triggers Manager investigation, compressing the available window significantly.

---

*This is a living document. Manager behavior may be refined during playtesting.*
