# DESIGN DOCUMENT 03: THE TRANSCRIPTOME (SYSTEMS & METADATA)

**Scope:** Blueprint Data Structures, Evolutionary Trees (DAG), Safety/Moderation (The Immune System), and The Economy of Relevance.
**Core Thesis:** "Ideas are alive. They must mutate to survive the changing world."

---

## 1.0 THE GENETIC STRUCTURE (THE RECIPE DAG)

We do not use a standard "File Save" system. We use a **Distributed Version Control System** (like Git) wrapped in a biological metaphor.

### 1.1 The Node (The Recipe)
Every object in the game (a specific Engine tune, a Hull shape, a Suspension setup) is a **Node**.
* **The Data Payload:**
    * **Geometry:** The mesh data (Vertices/Voxels).
    * **Metadata:** Author UUID, Creation Time, Weather Optimization Tags.
    * **Parent ID:** The UUID of the blueprint this was modified from.
    * **The "Hash":** A cryptographic signature ensuring integrity.

### 1.2 The Lineage (Phylogeny)
Because every Node points to a Parent, we generate a **Directed Acyclic Graph (DAG)**.
* **The "Tree of Life" UI:** When a player inspects a vehicle, they don't see a flat list of stats. They see the **Evolutionary History**.
    * *Root:* "Heavy Chassis" by **User:Atlas** (Gen 1).
    * *Branch:* "Heavy Chassis (Mud Mod)" by **User:Nomad** (Gen 2).
    * *Leaf:* "Heavy Chassis (Mud Mod + Red Paint)" by **User:You** (Gen 3).
* **Attribution:**
    * **User:Atlas** receives "Prestige" (Royalty) every time **User:You** prints the Gen 3 version.
    * This encourages players to build "Root" technologies (Foundational Frameworks) rather than just cosmetic skins.

---

## 2.0 THE IMMUNE SYSTEM (SAFETY & MODERATION)

Moderating millions of 3D assets is impossible for humans and too expensive for cloud AI. We move the "Immune Response" to the **Client Edge**.

### 2.1 The "Local Check" (T-Cell Response)
* **The Engine:** We integrate a quantized Small Language/Vision Model (e.g., Gemma 3 2B or Phi-3 Mini) via ONNX Runtime directly into the game client.
* **The Workflow:**
    1.  Player clicks "Save Blueprint."
    2.  **Pre-Flight:** The local game engine renders the object from 6 angles (snapshots) and extracts the text description.
    3.  **The Scan:** The Local AI analyzes the images and text for prohibited content (Hate Speech, NSFW).
    4.  **The Result:**
        * *Pass:* The AI generates a **Safety Hash**. The blueprint is allowed to be uploaded to the server.
        * *Fail:* The AI returns a **"Protocol Error."**
* **Diegetic Feedback:** The UI says: *"Cultural Integrity Violation: Geometry matches known corruption patterns. Please revise."*

### 2.2 Retrograde Signaling (Notoriety & Necrosis)
If a bad actor bypasses the local check (modded client), the **Network Immune System** kicks in via player reporting.
* **The Flag:** A player reports a blueprint.
* **The Necrosis:** The server marks that specific Node as "Toxic."
* **The Pruning:**
    * The system identifies the "Toxic Node."
    * It **Cuts the Branch**. That specific node and its direct children are hidden from the public library.
    * **Protection:** The *Parent* nodes (the innocent original creators) remain untouched. The tree remains healthy; only the infected limb is removed.

---

## 3.0 ENVIRONMENTAL OBSOLESCENCE (MALADAPTATION)

To prevent the "Meta" from stagnating, blueprints don't just "decay." They become **Pathological**.

### 3.1 The "Fitness" Score (Contextual Validity)
* **Scenario:** A "Dry Zone" moisture trap script works great in the desert.
* **The Shift:** In the "Wet Zone," that same script becomes a logic bomb, trying to dehumidify the ocean until it burns out the pumps.
* **The Visual:** In the Fabricator menu, the blueprint glows **Red** (Pathological/Dangerous).

### 3.2 The Spliceosome (The Fix)
* **The Mechanic:** The player must act as the **Spliceosome**.
* **The Loop:**
    1.  Player physically goes to the terminal.
    2.  They identify the "Maladaptive Intron" (the moisture script).
    3.  They "cut out" the code block to save the pump.
* **The Lesson:** Technology is not static. Maintenance requires adaptation.

---

## 4.0 THE LIBRARY (THE CODEX)

This is the UI where players interact with the Transcriptome.

### 4.1 Methylation (The Archival System)
We cannot show the player 50,000 blueprints. We use "Epigenetic Silencing" to manage bloat.
* **Active Cache (mRNA):** The top 50 blueprints that are (A) High Fitness for current weather and (B) Popular in the Convoy. These are instant-print.
* **Deep Archive (DNA):** Everything else.
    * *Access Cost:* Retrieving a blueprint from the Deep Archive takes time (Simulated Data Retrieval). It costs "Compute" resources.
    * *Why:* This forces players to curate their "Local Deck" of blueprints. "Do we keep the Snow Tires in the cache? No, it's 50 degrees outside. Archive them."

### 4.2 The Economy of Citations (Proof of Work)
* **No "Likes":** We explicitly reject vanity metrics. You cannot "Like" a blueprint.
* **The Metric:** You can only **Cite** it.
    * *Action:* A Citation is generated when a player *prints* and *installs* your design.
    * *Cost:* Citing costs resources. It is a bet on survival.
* **The Notification:** "Your 'Gen 3 Rotor' is currently active in 14 convoys."
* **The Result:** High Citation count = High Reliability. It is the fossil record of utility.

### 4.3 The "Prestige" (The License to Lead)
* **Currency:** "Prestige" is the aggregate of your Citations and your "Uptime" (Manual Activations).
* **The Stack Overflow Model:**
    * *Junior Dev (Low Prestige):* Can fix tires, but cannot edit the Nucleus Script.
    * *Senior Architect (High Prestige):* When they propose a course correction, the group listens because 500 people are running their code.
* **Spending:** You spend Prestige to **Boost** the priority of a request (e.g., "We need a new Algae Tank design NOW").

### 4.4 The "Seed" Mechanic (P2P Distribution)
* To keep the network decentralized (and save server costs), blueprints are distributed via **BitTorrent-style Seeding**.
* **The Mechanic:** To use a blueprint, your Convoy must "Host" it.
* **The Inventory:** Your ship has a limited "Data Drive." You can only host ~100 active blueprints.
* **The Social Choice:** "We have to delete the *Entertainment Module* blueprints to make room for the *Weapon Systems*. We are forgetting how to have fun to survive the war."

---

### DESIGNER'S NOTE ON IMPLEMENTATION
The crucial part of this system is the **Weather Link**.
If the blueprints degrade just because "Time Passed," it feels like a chore (Durability).
If they degrade because **The World Changed**, it feels like a puzzle.
The player thinks: *"My ship isn't broken; it's just wrong for this new world. I need to evolve it."* This is the core biological lesson.