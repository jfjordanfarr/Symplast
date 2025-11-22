# DESIGN DOCUMENT 01: THE PHYSICS OF COOPERATION

**Scope:** Atmospheric Physics, Terrain Interaction, Weather Systems, and the Mechanics of Tethering.
**Core Thesis:** "Solitary movement is entropy; Connected movement is life."

---

## 1.0 THE ATMOSPHERIC MODEL ("THE THICK AIR")

To simulate the 1,000-year future atmosphere, we discard standard "air drag" models used in racing games. Instead, we implement a **Viscous Fluid Simulation** roughly approximating Low Reynolds Number physics.

### 1.1 The "Stop" Rule (Inertia Damping)
In a standard game, if a player releases the throttle, the vehicle coasts to a stop over 100 meters. In *Symplast*, the atmosphere acts as a brake.
* **The Mechanic:** Global Drag Coefficient ($C_d$) is set 5x higher than standard Earth atmosphere.
* **Behavior:** If a player releases the throttle, the vehicle comes to a halt within 1–2 vehicle lengths.
* **The "Trucker" Feel:** This gives vehicles a sensation of immense weight. Every meter traveled requires active torque. There is no "drifting."

### 1.2 The "Wake" Volume (Slipstreaming)
This is the primary economic engine of the game.
* **The Volume:** Every vehicle casts a "low-pressure cone" behind it, calculated based on its Cross-Sectional Area.
* **The Calculation:**
    * `Wake_Efficiency = (Leader_Mass / Follower_Mass) * Proximity`
    * *Zone A (Drafting):* < 10m distance. **60% Fuel Reduction.**
    * *Zone B (Trailing):* 10m–30m distance. **20% Fuel Reduction.**
* **The UI Feedback:** We do not use "Speed Lines." Instead, we use **Particulate Flow**. Dust and rain wrap around the leader and create a visible "clear tunnel" behind them. The follower sees they are in the "bubble" of calm air.

### 1.3 Energy as Metabolism (ATP)
Fuel is not just for movement; it is for *existence*.
* **Idle Drain:** Even when stopped, the vehicle consumes fuel to run life support (AC/Heat/Scrubbers).
* **Torque Drain:** Movement burns fuel exponentially based on friction.
* **The Lesson:** A solitary player will burn 80% of their cargo capacity just moving fuel to the next town. A convoy of 5 vehicles reduces that burn by ~40% across the group, making the trip profitable.

---

## 2.0 THE STALLED WEATHER (BIOME PHYSICS)

The world is divided into semi-permanent weather cells. Each biome is not just a visual change, but a fundamental change in the **Physics Ruleset**.

### 2.1 Low Pressure Zone: "The Wet / The Mud"
**Concept:** A stalled rainstorm that has lasted for decades.
* **Physics Modifier:** **Ground Friction Multiplier (0.2x).**
* **The Threat: Sinkage.**
    * We use a **Voxel Terrain Deformation** system (similar to *MudRunner*).
    * Heavy vehicles sink until their chassis hits the collider floor ("bottoming out").
* **The Interaction:**
    * *Wheels:* Spin uselessly in deep mud. High RPM, zero movement.
    * *Treads:* Better grip, but damage the road for others.
    * *Walkers:* The best for mud (stepping over it), but high center of gravity.
* **Cooperative Solution:** **The Winch Train.** A heavy vehicle (Anchor) parks on solid ground. It winches the smaller vehicles through the mud pit one by one.

### 2.2 High Pressure Zone: "The Heat / The Baker"
**Concept:** A cloudless, stagnant heat dome (50°C+).
* **Physics Modifier:** **Thermal Exchange Rate (0.1x).**
* **The Threat: Internal Entropy.**
    * Engines produce heat. Normally, air cools the engine. In the Heat Dome, the air is too hot to absorb the heat.
    * *The Accumulator:* A bar on the HUD fills up. If it hits 100%, the reactor scrams (shutdown).
* **The Interaction:**
    * *Radiator Geometry:* Players must deploy "Fins" (Fractal surface area). This increases drag (bad for moving) but increases cooling (good for surviving).
    * *Night/Day Cycle:* Movement is often impossible at noon. Convoys must park and "sleep" (Sessile Mode) during the day and move only at night.

### 2.3 The Drowned Zone: "The Surge"
**Concept:** Coastal ruins with unpredictable tidal currents.
* **Physics Modifier:** **Buoyancy & Lateral Force.**
* **The Threat: The Current.**
    * Water moves faster than the vehicles. Lateral drag pushes vehicles off course, slamming them into buildings.
* **Cooperative Solution:** **The Raft.**
    * Terrestrial vehicles cannot swim well. They tether to an **Aquatic Class** (Barge/Sub).
    * The Aquatic vehicle provides the propulsion; the Terrestrial vehicles act as "Cargo," locking their treads and turning off their engines to reduce drag.

---

## 3.0 THE UNIVERSAL TETHER ("THE SYMPLAST LINK")

The Tether is not just a rope. It is the **Umbilical Chord**. It is the physical manifestation of the game's social contract.

### 3.1 Mechanical Implementation
* **The Hardpoint:** Every vehicle has a standardized electromagnetic winch point (The "Universal Port").
* **The Physics Joint:**
    * It is not a rigid rod (which feels fake).
    * It is a **Damped Spring Joint** with a variable break force. It has "slack" and "tension."
    * *Snapping:* If two vehicles pull in opposite directions with force > Break Threshold, the cable snaps. This creates tension (gameplay) during panic situations.

### 3.2 The Resource Bridge (Vascularity)
When tethered, the two vehicles effectively become one system.
* **Fluid Transfer:** Pipes extend along the cable. Fuel and Water automatically balance. If Vehicle A has 100% Fuel and Vehicle B has 0%, the system equalizes them to 50/50 over time.
    * *Override:* Players can set "Valves" to stop this if they need to quarantine a resource.
* **Data Sharing (The Nervous System):**
    * **Shared Fog of War:** If the Scout (Aerial) is tethered to the Hauler (Ground), the Hauler sees what the Scout sees on their map.
    * **Damage Reports:** The Hauler can see a warning light: "Scout Engine Overheating."

### 3.3 The "Right of Exit" (Disengagement)
* **The Button:** A physical emergency release lever in the cockpit.
* **The Delay:** It takes 2 seconds to disengage (mechanical unlatching sound).
* **Why:** This prevents griefing (instantly dropping someone off a cliff) but allows escape if the leader is driving into a volcano.

---

## 4.0 FISSION-FUSION DYNAMICS (MODES OF BEING)

The Convoy is a state machine. It switches between **Nomad** (Animal) and **Fortress** (Plant) modes.

### 4.1 Fission State (Animal Mode)
* **Configuration:** Vehicles are connected by long, slack tethers (50m–100m).
* **Behavior:**
    * Movement is possible.
    * Drag is minimized (Linear formation).
    * Vulnerability is high (Soft membranes exposed).
* **Use Case:** Travel, Exploration, Foraging.

### 4.2 Fusion State (Plant Mode)
* **Trigger:** The Convoy stops. Players initiate "Lockdown Protocol."
* **Configuration:**
    * Vehicles pull tight, circle up, or lock chassis-to-chassis.
    * **The Membrane:** External blast shields deploy.
* **Buffs:**
    * **+400% Stability:** Nearly impossible to flip in high wind.
    * **+200% Refining:** Processing raw resources (Drafting) becomes efficient because the reactor vibration stops.
    * **"The Garden":** Only in Fusion State can the "Livestock/Farm" modules operate at full capacity (Goats graze, plants grow).
* **Use Case:** Surviving the "Hypercane" (Boss Storms), Nighttime Repair, Crafting/Refining sessions.

---

## 5.0 THE ULTIMATE ANTAGONIST: "THE PHAGE"

To force the "Size Filter" (Big is better), we introduce a threat that ignores weapons but respects geometry.

### 5.1 The Drone Swarms ("Phages")
* **Lore:** Ancient, self-replicating autonomous micro-drones left over from the wars. They scavenge metal.
* **The Algorithm:** They swarm targets that are **Isolated** and **Small**.
    * *Target Lock:* They lock onto objects with a Total Mass < 10 Tons.
* **The Mechanic:**
    * A single Player Vehicle is ~5 Tons. The Phages will swarm it, strip its hull, and eat it.
    * **The Solution:** Tethering.
    * If 3 Vehicles tether, the "System Mass" reads as 15 Tons.
    * The Phage AI ignores them. They are perceived as "Terrain," not "Prey."
* **The Lesson:** You don't group up to shoot the enemy. You group up to become **invisible** to the predation algorithm.

---

### DESIGNER'S NOTE ON IMPLEMENTATION
For the prototype, focus on the **Drag Curve** and the **Wake Cone**. If simply following another player feels satisfying (the "suction" of the slipstream), the rest of the social mechanics will emerge naturally. If the driving feels floaty or generic, the game fails. The physics must feel "Heavy."

---

# ADDENDUM TO DOC 1: THE SYNAPSE (PLAYER-BUILT RAILS)

*Can players build rails?*
In the late game (The City Phase), yes. But we don't lay steel tracks on the ground. We build **Cableways**.

### 1. The "Tensegrity Rail" (Cable Cars)
* **The Build:** Players fire heavy harpoons between two "Sessile" (Tower) units. They tighten the cable until it is a rigid line.
* **The Physics:** This creates a **Zip-Line** or **Gondola** route above the mud/flood.
* **The Vehicle:** Players modify their vehicles with "Pulley Modules."
* **The Function:** This allows for rapid, low-energy resource transfer between the "Refinery" and the "Mine" without battling the mud physics every trip.
* **The Cellular Analogy:** This is the cell building the **Cytoskeleton** to organize its internal logistics.

### 2. Why this fits the "Stalled Weather"
* **Ground Rails fail** because the mud moves and the floods rise.
* **Suspended Rails (Monorails/Cables) survive** because they are above the entropy.

So, the answer is: **Yes, there are trains.** But they are either **Terrifyingly Fast Maglevs** jumping gaps in the ruins, or **Slow, Heavy Gondolas** strung between player towers. They represent the "Microtubule Network" of the emergent organism.