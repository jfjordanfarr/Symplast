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

## 3.0 THE TENSEGRITY WEB ("THE SYMPLAST LINK")

The Tether is not just a rope. It is the **Umbilical Chord**. It is the physical manifestation of the game's social contract.

### 3.1 Mechanical Implementation
* **The Hardpoint:** Every vehicle has a standardized electromagnetic winch point (The "Universal Port").
* **The Physics Joint:**
    * It is not a rigid rod (which feels fake). It is a dynamic spring-damper system.
    * **Structural Interdependent Failure:** It’s not just about sharing fuel. It’s about **Load Bearing**.
    * **"The Frame Snap":** If the Convoy encounters a high-torque event (Mud Surge), the stress isn't applied to one car; it is distributed. If the players are out of sync (some pushing, some dragging), the *Tether* doesn't break—the *Chassis* breaks.

### 3.2 The "Muscle" Mechanic (Galley Rower)
* **Concept:** Coordinated forward pulses (Temporal Summation) create exponential torque.
* **The Mechanic:** A convoy can punch through mud that would mire a single engine if they accelerate in perfect sync.
* **The Resource Bridge (Vascularity):**
    * **Fluid Transfer:** Pipes extend along the cable. Fuel and Water automatically balance.
    * **Data Sharing:** Shared Fog of War and Damage Reports.

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

## 5.0 THE ULTIMATE ANTAGONIST: THE LOGIC TRAP (ENTROPY)

To force the "Sanity Filter" (Clean Code is better), we introduce a threat that ignores weapons but respects hygiene.

### 5.1 Phantom Mass (The Prion State)
* **Concept:** When a script enters an infinite loop or memory leak (Infinite Paperclip), the server does not crash. It applies a **Physical Penalty**.
* **The Mechanic:** The physics engine assigns **"Simulated Load."** A 50-ton vehicle behaves as if it weighs 500 tons.
* **The Feedback:** The vehicle sinks in mud. Engines scream at 100% RPM but achieve 5% speed. Fuel burn skyrockets.
* **The Horror:** You are not being attacked; you are just suddenly, impossibly *heavy*.

### 5.2 The Vector (Bad Code)
* **Pathologies are self-inflicted.** They come from over-tuning a reactor script or downloading an unverified "Optimizer" that lacks an exit condition.
* **Horizontal Transfer:** Prions travel through the **Tether**. When you open the "Data Valve" to share maps, the Prion jumps. Tethering with a stranger is now a high-risk medical decision.

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