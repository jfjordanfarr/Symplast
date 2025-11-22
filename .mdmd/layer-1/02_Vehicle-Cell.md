# DESIGN DOCUMENT 02: THE VEHICLE / THE "CELL"

**Scope:** Chassis Construction, Mobility Classes, Internal Metabolism (Systems), and Biological Integration.
**Core Thesis:** "The Vehicle is the Membrane that separates Order (You) from Entropy (The Storm)."

---

## 1.0 THE CHASSIS (THE CYTOSKELETON)

The vehicle is not a pre-made asset. It is a modular assembly built upon a **Stress-Simulated Frame**.

### 1.1 The Frame Rail System
* **The Foundation:** Players start with a **Frame Rail**. This is the spine.
* **Grid vs. Physics:** Modules snap to a grid for ease of use, but the *physics* are calculated based on structural integrity.
* **Stress Propagation:**
    * Every module has Mass.
    * Every connection point has a "Shear Strength."
    * *The Mechanic:* If a player builds a tower that is too tall without cross-bracing (Struts/Tensegrity), the physics engine will snap the bolts when the vehicle hits a bump.
    * *Visual Feedback:* "Stress View" (Lidar Overlay) shows parts glowing Red when they are near failure.



### 1.2 The "Trucker Scale"
* **Mass:** The smallest viable vehicle is ~5 Tons. The largest Land Trains are ~200 Tons.
* **Interaction:** Entering the vehicle is a 3-second animation of climbing a ladder. Tires are 2 meters tall. This scale emphasizes that the player is a *tiny occupant* of a massive machine.

---

## 2.0 MORPHOLOGY (DOMAINS OF MOTION)

Players choose their "Class" by the **Propulsion Modules** they install. This defines their ecological niche in the Convoy.

### 2.1 The Terrestrial (The Kinesin / Muscle)
* **Locomotion:** Treads, Heavy-Duty Balloon Tires, or Walker Legs.
* **Role:** **The Pathbreaker.**
    * *Terrain Deformation:* The terrestrial vehicle interacts directly with the voxel mud.
    * *The "Road" Mechanic:* Heavy treads compress the mud, creating a temporary "Packed Earth" surface. Following vehicles gain a +30% traction buff when driving in these tracks.
* **Constraint:** High Friction. Fuel consumption scales linearly with weight.

### 2.2 The Aquatic (The Vesicle / Vascular)
* **Locomotion:** Screws (Propellers), Hydrojets, Pontoons.
* **Role:** **The Heavy Hauler.**
    * *Displacement:* Aquatic vehicles ignore ground friction. Their efficiency is defined by **Drag Coefficient** (how sleek the hull is).
    * *Capacity:* They can carry 10x the mass of a Terrestrial vehicle for the same fuel cost, provided there is water.
* **Constraint:** Draft. If the vehicle is too heavy, it scrapes the bottom of shallow flooded ruins (Hull Damage).

### 2.3 The Aerial (The Pollen / Scout)
* **Locomotion:** Rotors, Aerostats (Blimps), Parafoils.
* **Role:** **The Optic Nerve.**
    * *The Tethered Kite:* Due to high winds, free flight is suicide. Most Aerials operate as "Kites" winched to a ground unit.
    * *Radar Horizon:* Ground units have Lidar ranges of ~200m (blocked by trees). An Aerial unit at 300m altitude extends the Convoy’s vision to 5km, spotting resources and weather patterns.
* **Constraint:** Fragility. Aerial units have almost no armor. A "Downburst" weather event requires them to emergency-winch down or be destroyed.

### 2.4 The Sessile (The Bone / Coral)
* **Locomotion:** Hydraulic Anchors, Concrete Pylons.
* **Role:** **The Refinery.**
    * *The "Rooting" Mechanic:* The player drives to a location and deploys Anchors. The physics engine locks the vehicle to the terrain (Mass becomes Infinite).
    * *Efficiency Buff:* Because the engine is no longer driving wheels, 100% of reactor output goes to **Refining** and **Charging**.
    * *Defense:* Sessile units can deploy heavy blast shields that would be too heavy to move, acting as windbreaks for the rest of the convoy.

---

## 3.0 METABOLISM (INTERNAL SYSTEMS)

The vehicle functions like a eukaryotic cell. It must balance **Energy Input**, **Material Processing**, and **Waste Excretion**.

### 3.1 The Reactor (Mitochondria)
* **Input:** Fuel Rods (Refined Carbon/Isotopes).
* **Output:** Electricity (Watts) + **Thermal Waste (Heat)** + **Toxic Waste (ROS)**.
* **The "ATP" Simulation:**
    * Every system (Engine, Lights, Lidar) draws Watts.
    * If Demand > Supply, systems brownout. (Lights flicker, engine stalls).
    * *Overclocking:* Players can push the reactor past 100%, but this generates **ROS (Reactive Oxygen Species)**—a "Corrosion" status effect that eats the reactor's health from the inside.

### 3.2 The Radiators (Thermal Regulation)
* **The Problem:** Heat does not just disappear. It must be exchanged with the atmosphere.
* **Mechanic:**
    * *Active Cooling:* Fans. Consumes power, works in all weather.
    * *Passive Cooling:* "Fern" Geometry (fins). Consumes no power, but relies on wind speed.
* **The Heat Dome Crisis:** In high-temp biomes, Passive Cooling fails. Players must shut down non-essential systems (hibernation) to prevent meltdown.

### 3.3 The Membrane (Hull & Shields)
* **Layered Armor:**
    * *Outer Layer (The Cell Wall):* Ablative plates (Ceramic/Steel). These chip away visually when hit by debris. Cheap to replace.
    * *Inner Layer (The Plasma Membrane):* The pressure seal. If this breaches, the "Cabin Atmosphere" leaks, and the crew begins to suffocate/freeze.
* **Maintenance:** Players must physically go outside (EVA) with welders to patch the Outer Layer before the Inner Layer is compromised.

---

## 4.0 THE MICROBIOME (BIOLOGICAL INTEGRATION)

To bridge the gap between "Machine" and "Life," we introduce biological components as functional ship systems. This is the **"Ark"** aspect.

### 4.1 The "Digester" (The Gut)
* **The Problem:** The Reactor produces "Toxic Sludge" (ROS/Chemicals). Venting it attracts Phages (Enemies).
* **The Solution:** **The Algae Tank.**
    * A module filled with bio-engineered slime.
    * *Input:* Toxic Sludge + UV Light.
    * *Output:* "Bio-Mass" (Green sludge) + Clean Water.
    * *Risk:* If the tank ruptures, the interior of the ship becomes contaminated.

### 4.2 The Livestock (The Symbionts)
* **The Asset:** Goats, Chickens, or Synthetic-Biology equivalent.
* **Housing:** "The Coop" module.
* **The Loop:**
    * The Goats eat the "Bio-Mass" (from the Algae Tank) and "Weeds" (harvested from outside).
    * The Goats produce **Milk/Protein**.
    * *Player Buff:* Consuming high-quality protein increases "Focus" (Repair speed) and "Endurance" (EVA time).
* **Psychology:** The sound of chickens clucking inside a heavy industrial rover creates a crucial auditory contrast. It makes the vehicle feel like a *Home*.

---

## 5.0 THE COCKPIT (THE NUCLEUS INTERFACE)

The UI should feel **Diegetic** and **Tactile**. No floating menus in the world.

### 5.1 The Dashboard
* **Analog Aesthetics:** Needles, toggle switches, CRT monitors.
* **Startup Sequence:** Starting the engine isn't one button. It’s: *Battery On -> Fuel Pump -> Reactor Prime -> Ignition.* This makes movement feel intentional and heavy.

### 5.2 The "Transcriptome" Editor (CAD Station)
* **Location:** A specific terminal inside the vehicle.
* **Visual Style:** The "Blue Prince" / Lidar aesthetic.
* **Function:** This is where players design new modules.
    * *The "Fork" Button:* Players can pull up the blueprint of their current engine, modify the intake geometry for the current weather, and "Print" a replacement part using the onboard Fabricator.

### 5.3 The Periscope (Lidar Overlay)
* **Visibility:** In a storm, visibility is near zero.
* **The Scanner:** The driver pulls down a "Periscope" or activates a "Heads Up Display."
* **The Effect:** The muddy world is replaced by the wireframe Lidar view (The Technical Art Style).
    * *Pros:* Perfect geometry visibility. Shows wind vectors.
    * *Cons:* Monochromatic. Cannot see colors (resource rarity) or subtle terrain textures (mud depth).
    * *Gameplay:* The driver constantly toggles between "Real Vision" (for context) and "Lidar Vision" (for navigation).


---

# ADDENDUM TO DOC 2: THE VECTOR CLASS (THE MICROTUBULE)

**Concept:** Vehicles that sacrifice freedom of movement for extreme efficiency by latching onto **Fixed Infrastructure**.
**Biological Analogy:** Kinesin Motors walking on Microtubules.

### 1. The "Ghost Rails" (Environmental Infrastructure)
We do not use ground rails (too much mud). We use **Elevated Maglev Pylons** from the Old World.
* **The Setting:** Stretching across the "Wet Zones" and "Drowned Zones" are the rusted, moss-covered remains of massive inter-city Maglev lines. They stand 50 meters above the mud, cutting through the canopy.
* **The Risk:** The track is not continuous. Sections have collapsed.
* **The Reward:** Zero Friction. Zero Mud. 100% Speed.

### 2. The Vehicle: "The Vector" (The Clamp)
This is a new vehicle morphology. It does not have wheels or treads.
* **Locomotion:** **Magnetic/Mechanical Clamps**. It physically locks onto the Monorail Beam.
* **The Gameplay Loop:**
    * *The Sprint:* You find a rail line. You align your clamps. You engage. You rocket forward at 200 km/h (unthinkable speeds for a Crawler).
    * *The Break:* Your Lidar detects a gap in the track 2km ahead (a collapsed section).
    * *The Transition:* You must slow down, disengage the clamps, deploy **Emergency Landing Gear** (or Airbags), and drop 50 meters into the mud below to continue as a Crawler until you find the next rail section.
* **Role in Convoy:** **The Ferry.**
    * A massive "Vector" engine can clamp onto the rail, and then winch up 5-6 smaller Terrestrial vehicles, carrying them like luggage. It becomes a **High-Speed dropship**.

---
