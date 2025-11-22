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

## 3.0 ENVIRONMENTAL OBSOLESCENCE (THE "mRNA" MECHANIC)

To prevent the "Meta" from stagnating (e.g., everyone using the "V1 Engine" forever), blueprints suffer from **Functional Decay** based on the world state.

### 3.1 The "Fitness" Score
Every blueprint has hidden "Fitness Stats" calculated against the **Current Weather**.
* **Scenario:**
    * *Gen 1 Engine* was designed during "The Heat Dome" (High Temp, Low Humidity). It has massive Radiators.
    * *Current Weather:* The world shifts to "The Wet Zone" (Mud, Rain).
* **The Decay:**
    * The Gen 1 Engine is now **Maladaptive**.
    * Its "Efficiency" stat drops by 40% because the open radiators clog with mud.
* **The Visual:** In the Fabricator menu, the blueprint glows **Dim/Grey** (Low Expression).

### 3.2 Mutation (Forced Innovation)
Players cannot simply "Repair" the blueprint. They must **Mutate** it.
* **The Loop:**
    1.  Player opens the "Gen 1 Engine" in the Editor.
    2.  Player adds "Mud Filters" and removes the "Extra Radiators."
    3.  Player saves as "Gen 2 Engine (Wet Season)."
* **The Result:** The new blueprint has High Fitness. It glows **Bright** (High Expression).
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

### 4.2 The Economy of Citations
* **Currency:** "Prestige."
* **Earning:** You earn Prestige when others *use* your blueprints.
* **Spending:** You spend Prestige to **Boost** the priority of a request.
    * *Example:* The Convoy is starving. You need a "High-Efficiency Algae Tank" *now*. You spend Prestige to broadcast a "Request for Mutation" to the network.
    * *The Architect:* A designer player sees the bounty, designs the tank, and claims the Prestige.

### 4.3 The "Seed" Mechanic (P2P Distribution)
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