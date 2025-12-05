# DESIGN BIBLE: PROJECT SYMPLAST

**High Concept:** A cooperative vehicle-survival sandbox set on a high-energy future Earth.
**Core Thesis:** "Survival is a Manual Override. The storm wants to kill you; your machine wants to kill itself to save the frame. You are the mediator."
**The Loop:** Players pilot modular vehicles that must physically latch together ("Tether") to overcome atmospheric drag and weather events, forming temporary, mobile cities. **The Maintenance of Sanity:** Players do not just pilot; they must physically move through their ship to "Prime" inert systems and "Chaperone" (Reset) systems that are becoming hyperexcitable/pathological.

---

## DOC 1: THE PHYSICS OF COOPERATION

[01_Physics-of-Cooperation.md](./01_Physics-of-Cooperation.md)

**Goal:** Enforce mutualism through environmental pressure, not moral instruction.

### 1.1 The Atmosphere: "The Viscous Reality"
We do not use standard "air" physics. We use **Low Reynolds Number** approximations.
* **The "Stop" Rule:** Due to extreme atmospheric density and vegetation drag, inertia is minimal. If a player cuts their engine, they do not coast; they stop almost instantly.
* **The Energy Penalty:** Moving solo requires 100% output for 50% speed. The "Drag" is a constant resource drain.
* **The Slipstream:** Large vehicles create a "low-pressure wake." Smaller vehicles traveling in this wake reduce fuel consumption by ~60%.
    * *Result:* Players naturally form convoys to save fuel.

### 1.2 Stalled Weather Systems (The Biomes)
The Jet Stream has collapsed, resulting in "Stalled Weather."
* **The Wet Zones (Low Pressure):** Permanent rain/mud. Requires High-Torque treads and waterproofing. Risk: Rust/Rot.
* **The Dry Zones (High Pressure):** Permanent sun/heat. Requires "Radiator" geometry (Fern-like cooling fins). Risk: Overheating.
* **The Drowned Zones:** Flooded coastlines. Requires buoyancy/submersibles.

### 1.3 The Universal Tether (The "Handshake")
To solve the "One Organism vs. Many" problem, we use **Flexible Coupling**.
* **The Mechanic:** All vehicles have a universal winch/magnet port.
* **Data & Power:** Once tethered, vehicles share a unified "Power Grid" and "Sensor Overlay."
* **Fission/Fusion:**
    * *Fusion:* During storms, vehicles winch tight, locking wheels to form a static "Fortress" (Plant Mode).
    * *Fission:* In calm weather, vehicles unspool cables to spread out and forage (Animal Mode), maintaining a data link up to 500m.

---

## DOC 2: THE VEHICLE (THE "CELL")

[02_Vehicle-Cell.md](./02_Vehicle-Cell.md)

**Goal:** Allow for radical player expression while ensuring functional interdependence.

### 2.1 Morphology: "How do you want to live?"
Players build their "Cell" based on how they wish to interact with the terrain.
* **The Terrestrial (Kinesin):** Heavy haulers, tracks, walkers. They crush vegetation to make paths (Infrastructure).
* **The Aquatic (Vascular):** Barges and subs. They move bulk goods effortlessly along flooded highways but cannot cross land.
* **The Aerial (Pollen):** Kites, gliders, and tethered drones. They provide long-range Lidar data but are fragile in storms.
* **The Sessile (Bone/Coral):** Stationary bunkers or converted ruins. High-efficiency refining and battery charging. They act as "Gas Stations" for nomads.

### 2.2 Internal Systems (Organelle Logic)
Players manage internal "heat" and "waste" akin to cellular metabolism.
* **The Inert Core (Mitochondria):** Generates power but requires manual "Priming" to start. Produces "Waste Heat" (ROS).
* **The Ribosome (Fabricator):** Prints new parts from blueprints (Transcripts).
* **The Cargo (Vacuole):** Storage for resources.
* **The Livestock (Microbiome):** Goats/Chickens kept in bays. They consume waste biomass (weeds) and produce high-density food (proteins), acting as a biological recycling loop.

---

## DOC 3: THE TRANSCRIPTOME (USER GENERATED CULTURE)

[03_Transcriptome-Systems-Metadata.md](./03_Transcriptome-Systems-Metadata.md)

**Goal:** A blueprint system that handles attribution, safety, and evolution without breaking immersion.

### 3.1 The DNA Structure (The DAG)
Blueprints are not static files; they are nodes in a **Directed Acyclic Graph**.
* **Attribution:** Every part tracks its "Root Author." If Player A designs a chassis, and Player B adds wings 6 months later, Player A still receives "Citation Credits" (Prestige) when Player B's ship is used.
* **Lineage UI:** Inspecting a ship reveals its evolutionary tree: *Base by Atlas > Cooling Mod by Sarah > Tuning by You.*

### 3.2 The Immune System (Safety)
* **Local AI Bounce:** A distilled, on-device LLM (e.g., Gemma 3 quantized) runs a pre-check on all blueprints before upload.
* **The Check:** Scans geometry and text descriptions for hate speech or prohibited imagery.
* **The Feedback:** If flagged, the system rejects the "Save" locally with a diegetic error: *"Cultural Integrity Check Failed: Blueprint unstable."*

### 3.3 The Half-Life of Relevance (mRNA Decay)
To prevent content bloat and simulate evolution:
* **Environmental Fit:** Blueprints have stats derived from the *current* weather. A "Gen 1 Radiator" works great in the Dry Zone.
* **The Shift:** When the weather shifts to "Wet Zone," the Gen 1 Radiator becomes inefficient (Maladaptive).
* **The decay:** The blueprint doesn't disappear, but it is "Methylated" (archived). Players must "Fork" the design, modify it for the new weather, and re-release it as "Gen 2." This keeps the engineering culture alive and reactive.

---

## DOC 4: VISUAL & TECHNICAL DIRECTION

[04_Visual-Direction.md](./04_Visual-Direction.md)

**Goal:** Grounded realism mediated by high-tech sensing. Averting "Fantasy Bioluminescence."

### 4.1 The Aesthetic: "Mud and Math"
* **The Naked Eye:** Hyper-realistic rendering of weather. Rain on glass, heavy mud, oxidized metal. Gritty, industrial, "NASA meets Caterpillar."
* **The Sensor Overlay (The "Blue Prince" Layer):**
    * When players activate scanners or build mode, the gritty world is overlaid with a clean, high-contrast Lidar/CAD wireframe.
    * This allows for precise technical play without sacrificing the oppressive atmosphere of the storm.
    * *Why:* It reinforces that the players are using technology to make sense of a hostile nature.

### 4.2 The Map: Geospatial Remix
* **Source Data:** Use real-world DEM (Elevation) and road data.
* **The Ghost Data:** Old World metadata (Google Maps tags) serves as the "Treasure Map."
    * A cluster of "Restaurant" tags buried under 10 meters of mud = A Carbon/Plastics deposit.
    * An "Industrial Park" tag = Heavy Metals deposit.

---

## DOC 5: THE SOCIAL META-GAME

[05_Metagame-Progression.md](./05_Metagame-Progression.md)

**Goal:** Governance via Physics. The simulation does not appoint leaders; it simulates the drag of indecision.

### 5.1 The Physics of Disagreement
* **The Tether as Contract:** Connection requires physically opening valves. Trust is a resource flow.
* **The Drag of Dissent:** If a player refuses to share or align, they become "Heavy" (Parasitic Drag). The convoy slows down.
* **The Resolution:** The group must either convince the dissenter or physically pull the "Manual Release Lever" to cut them loose.

### 5.2 The End Game: The Commonwealth
* **From Survival to Stability:** The goal is not to escape, but to stabilize the weather (Terraforming).
* **Public Goods:** Advanced groups build "Climate Stabilizers" that benefit everyone in the region, creating "Safe Zones" that attract new players.
* **Reputation as Currency:** Wealth is defined by how many people are willing to tether to you.