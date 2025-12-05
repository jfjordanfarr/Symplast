# DESIGN DOCUMENT 02: THE VEHICLE / THE "CELL"

**Scope:** Chassis Construction, Mobility Classes, The Automation Core (Nucleus), and The Activation Loop.
**Core Thesis:** "The Vehicle is a dormant giant. You are the spark that wakes it."

---

## 1.0 THE CHASSIS (THE CYTOSKELETON)

The vehicle is not a rigid mesh; it is a **Tensegrity Structure**.

### 1.1 The Frame & The Snap
* **The Foundation:** Players build on a **Frame Rail** system.
* **Tensegrity Physics:**
    * Vehicles are held together by "Struts" (Compression) and "Cables" (Tension).
    * **The Mechanic:** Impact or drag doesn't just damage "Health"; it distorts the frame.
    * **The Snap:** If a vehicle is pushed beyond its structural tolerance (e.g., a "Galley Rower" pulse that is out of sync), the frame doesn't bend—it *snaps* violently. This is the **Frame Snap** failure state.

### 1.2 The "Trucker Scale"
* **Mass:** Minimum 5 Tons. Maximum 200 Tons.
* **Interaction:** The player is small. To repair an engine, you don't click a menu; you physically climb a ladder, walk along a catwalk, and open a hatch.

---

## 2.0 MORPHOLOGY (DOMAINS OF MOTION)

Players select a "Class" based on where they survive in the vertical column of the world.

### 2.1 The Terrestrial (The Kinesin)
* **Role:** **The Pathbreaker.**
* **Locomotion:** Treads, Balloon Tires.
* **Function:** Crushes vegetation to create "Roads" (Packed Earth) for followers.
* **Threat:** The Mud (Sinkage).

### 2.2 The Benthic Anchor (The Root)
* **Role:** **The Heat Sink.**
* **Locomotion:** Negative Buoyancy Ballast / Heavy Winches. They sink and hang.
* **Environment:** The Deep Ocean (Cold, Dark, High Pressure).
* **Gameplay Loop:**
    * These modules are "Boiler Rooms."
    * They accept **Waste Heat** from surface ships via the Tether.
    * *The Risk:* **Pressure Breach.** If the hull integrity fails, the ocean crushes the module instantly.

### 2.3 The Ridge-Walker (The Sentinel)
* **Role:** **The Harvester.**
* **Locomotion:** Hexapod Legs (Climbers).
* **Environment:** High Altitude / The Dry Zone.
* **Gameplay Loop:**
    * Operates above the cloud layer to harvest intense UV solar energy.
    * *The Risk:* **Fire.** The air is dry and the vehicle is hot. Fire-hardening is essential.

### 2.4 The Aerial (The Pollen)
* **Role:** **The Scout.**
* **Locomotion:** Tethered Kites/Aerostats.
* **Function:** Provides Radar/Lidar extension beyond the horizon.

---

## 3.0 THE NUCLEUS (THE AUTOMATION HUB)

The Nucleus is not a player. It is a **Server Rack** embedded in the wall of the Cockpit.

### 3.1 The Genome (The Blueprints)
* **Storage:** The Nucleus holds the **Transcriptome**—the library of every machine, part, and script the player has collected.
* **The Logic:** Players access the Terminal to set **"Introns"** (Regulatory Logic).
    * *Example:* "IF [Mud_Depth > 1m] THEN [Print: Wide_Treads]."
    * *Example:* "IF [Battery < 10%] THEN [Signal: Emergency_Beacon]."

### 3.2 The Transcript (The Signal)
* **The Trigger:** When a condition is met (e.g., Storm Incoming), the Nucleus generates a **Transcript**.
* **The Output:** This is a digital "Work Order" sent to the Fabricator (Ribosome).
* **The Failure:** If the Nucleus is damaged or the logic is bad (Hyperexcitable), it spams Transcripts, clogging the system with useless orders.

---

## 4.0 THE RIBOSOME (THE FABRICATOR)

* **Function:** The Ribosome receives the Transcript and physically prints the machine or part.
* **State:** The printed machine emerges **Inert**. It exists, but it is cold. It requires **Activation**.

---

## 5.0 THE ACTIVATION LOOP (THE HUMAN ROLE)

This is the core gameplay. The machine can build itself, but it cannot *start* itself without metabolic cost.

### 5.1 The "Prime" (Mitochondrial Activation)
* **The Mechanic:** **Manual Ignition.**
* **The Action:** The player must physically travel to the machine (Engine, Pump, Shield Generator) and interact with the **"Dead Switch"** or **"Primer Handle."**
    * *Low Skill:* Walking to the Oxygen Recycler to "kickstart" it every hour.
    * *High Skill:* **The Galley Rower.**
        * To perform a high-torque maneuver (e.g., punching through deep mud), multiple players must stand at multiple engines.
        * They must slam their "Primer Handles" in perfect sync (Temporal Summation).
        * *Result:* A massive "Action Potential" of torque that no automated system could safely authorize.

### 5.2 The "Chaperone" (Maintenance)
* **The Problem:** Machines that run too long accumulate **"Logic Drift"** (Heat/Entropy). They become "Hyperexcitable" (vibrating, overheating, locking doors).
* **The Action:** **Refolding.**
    * The player inspects the machine.
    * They perform a "Reset" minigame (flushing valves, clearing cache).
    * This returns the machine to a "Healthy/Cool" state.
* **The Risk:** If you ignore a Hyperexcitable machine, it triggers a **System Induced Suicide** (e.g., jettisoning the fuel core to "save" the ship).

### 5.3 The "Splice" (Editing)
* **The Problem:** The Nucleus is running a script that is Maladaptive for the current weather (e.g., trying to De-Humidify the Ocean).
* **The Action:** The player goes to the Nucleus Terminal.
* **The Fix:** They manually "Splice out" the bad logic block (The Intron) and upload a new "Patch."

---

## 6.0 THE SYMPLAST (INTERCELLULAR CONNECTION)

When vehicles tether, they share a "Cytoplasm" (Air/Power), but they retain individual Nuclei.

### 6.1 The "Gap Junction" (Shared Activation)
* **The Mechanic:** A player from Vehicle A can run across the tether to Vehicle B.
* **The Play:** They can **Prime** Vehicle B's engines.
* **Why:** If Vehicle B's player is busy (e.g., editing the Nucleus or piloting a drone), the neighbor acts as the **Surrogate Mitochondrion**, keeping the lights on.

### 6.2 The "Quarantine" (Callose Plug)
* **The Mechanic:** If Vehicle B becomes "Cancerous" (Hyperexcitable Nucleus), Vehicle A can physically pull the **"Emergency Sever"** lever.
* **The Effect:** The Tether snaps. The Cytoplasm connection is sealed. The sick module is cast adrift.

--- 

### DESIGNER'S NOTE
This structure enforces the **"Gardener"** relationship. The player plants the seeds (Nucleus Logic), the garden grows (Ribosome Printing), but the player must water and prune (Prime/Chaperone) to prevent the garden from becoming a jungle that chokes itself out.