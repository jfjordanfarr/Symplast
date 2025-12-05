# DESIGN DOCUMENT 04: VISUAL & TECHNICAL DIRECTION 

**Scope:** Art Direction, Rendering Pipeline, Geospatial Data Integration, and Diegetic UI.
**Core Thesis:** "The World is Messy (Entropy); The Data is Clean (Order)."

---

## 1.0 THE BIFURCATED AESTHETIC ("MUD AND MATH")

We do not choose between "Realism" and "Stylization." We implement **both** as distinct, toggleable perception modes. This simulates the experience of piloting a high-tech machine through a low-tech disaster.

### 1.1 Mode A: The Naked Eye (Diegetic Misery)
This is the default view through the windshield.
* **Visual Target:** *The Revenant* meets *MudRunner*.
* **Rendering Tech:** Physically Based Rendering (PBR), Ray-Traced Global Illumination, and Volumetric Fog.
* **Key Elements:**
    * **Obscuration:** Rain droplets on glass (refraction), condensation, mud splatters. The player should feel "blinded" by the weather.
    * **Atmosphere:** The air is thick. Light sources bloom heavily (halos). Shadows are soft and diffuse.
    * **Palette:** Desaturated. Browns (Mud), Greys (Slate/Storm), and Faded Safety Orange (Oxidized Paint).
* **Emotional Effect:** Claustrophobia, vulnerability, heaviness.

### 1.2 Mode B: The Sensor Overlay (The Visual Unifier)
This is the Augmented Reality view activated by the Lidar/Radar systems. It is the critical tool that makes the visual chaos of Mode A legible.
* **Visual Target:** *Blue Prince* / Architectural CAD / 1980s Vector Graphics.
* **Rendering Tech:** Post-Process Edge Detection, Depth-Based Color Banding, Flat Shading (Unlit).
* **Key Elements:**
    * **The Unifier:** When active, the chaotic colors (pink ships, rusted barges) vanish. Everything becomes **Topography and Stress**.
    * **The Grid:** The chaotic mud terrain is rendered as a clean, wireframe mesh.
    * **Data Visualization:** Wind vectors appear as white streamlines. Stress points on the chassis glow red.
    * **Palette:** High Contrast. Deep Blue background, White vector lines, Cyan data points.
* **Emotional Effect:** Control, precision, intelligence.
* **Gameplay Loop:** Players toggle Mode B to navigate the "Geometry" of the terrain, then switch back to Mode A to manage the "Physics" of the mud.

---

## 2.0 THE MAP: GEOSPATIAL ARCHEOLOGY

We do not hand-sculpt the world. We **Erode** the real world.

### 2.1 The Base Layer (The Anthropocene Fossil)
* **Source Data:** Real-world DEM (Digital Elevation Models) of regions like the Ohio River Valley or the Mississippi Delta.
* **The Erosion Algorithm:** We apply a procedural "1,000 Year Erosion" pass.
    * *Valleys:* Fill with sediment (Mud depth increases).
    * *Hills:* Sharpen (Soil washes away, leaving bedrock).
* **The "Technofossil" Stratum:**
    * We do not model ruined skyscrapers (they would have collapsed). We model **Mounds**.
    * *Visuals:* A grassy hill with "veins" of plastic and concrete.
    * *Plastiglomerate:* The bedrock of the future is a fused aggregate of melted plastic, coral, and basalt. This is the primary "Ore" players mine.

### 2.2 The Ghost Data (Metadata Gameplay)
We use OpenStreetMap (OSM) data as a gameplay layer.
* **The System:** The game reads the Lat/Long of old-world locations.
* **The Mechanic:**
    * If the player scans coordinates corresponding to a 2025 **"Gas Station,"** the Lidar highlights a "Chemical Deposit" deep underground.
    * If they scan a **"Big Box Store,"** it highlights a "Rare Earth/Electronics" deposit.
* **The UI:** The "Ghost Overlay" projects faint, glitchy outlines of the old buildings (wireframes) floating above the current mud, showing the player what *used* to be there.

---

## 3.0 THE VEHICLE: MATERIAL TRUTH (FORM FOLLOWS PHYSICS)

The vehicles are not defined by a style guide, but by **Material Properties**. The future is not a uniform army; it is a chaotic coral reef.

### 3.1 The Material Palette
Instead of enforcing "Industrial" or "Sci-Fi," we enforce the physical properties of the resource used.
* **Lignin (Grown Wood):** Renders with grain and knots. Absorbs water (darkens in rain). Burns. *Aesthetic: Wicker / Grown.*
* **Plastiglomerate (Recycled):** Renders with subsurface scattering. Vibrant colors (bleached by sun). Melts. *Aesthetic: Injection Molded / Punk.*
* **Oxidized Steel (Scavenged):** Heavy, rusted, pitted. High tensile strength. *Aesthetic: Brutalist / Heavy Metal.*
* **Aerogel/Glass (High Tech):** Translucent, fragile, internal refraction. *Aesthetic: Crystalline / Fragile.*

### 3.2 The Biomimetic Palette (Convergent Evolution)
Players will naturally evolve shapes based on function, creating a "Biomimetic" diversity.
* **The Leaf (Solar Harvesters):** Wide surface areas, fractals, transparent domes. *Result:* A "Crystal Palace" aesthetic.
* **The Bone (Heavy Haulers):** Trusses, thick plating, compact shapes. *Result:* An "Industrial Brutalist" aesthetic.
* **The Skin (Aerostats):** Tension fabrics, balloons, tensile wires. *Result:* A "Nomadic Yurt" aesthetic.

### 3.3 Visual Diversity & Safety (The Ghost Layer)
* **The Freedom:** If a player wants to paint their ship hot pink with anime decals, *let them.* It implies they found a cache of "Ancient Pigments."
* **The Filter:** The local LLM (Gemma 3) ensures content is safe (no hate speech/NSFW) without needing "Art Police."
* **The Result:** A **Punk/Collage** aesthetic that feels authentic to a scavenger civilization. We do not force everyone to be brown and grey.

### 3.4 Scale & Animation
* **The "Heavy" Animation Set:**
    * Suspension does not just bounce; it groans.
    * Deploying a "Solar Wing" takes 10 seconds. You see the hydraulics struggle. You hear the servo motors whine.
    * *Why:* This reinforces the "Time Cost" of every action. Changing from Travel Mode to Sessile Mode is a commitment.

---

## 4.0 THE USER INTERFACE: TACTILE & DIEGETIC

We avoid "Video Game UI" (floating health bars) in favor of **Instrumentation**.

### 4.1 The Cockpit (Manual Priming)
* **Tactility:** Buttons are physical. To activate the "Winch," the player character's hand flips a safety cover and presses a toggle.
* **The "Click":** Sound design is crucial. Heavy, satisfying mechanical clicks.
* **Manual Priming:** To start the engine, you don't press "E". You look at the dashboard, flip the "Fuel Pump" switch, wait for pressure to build (needle gauge), then press "Ignition".
* **Haptic Feedback:** The UI shakes when the engine struggles. Warnings are auditory (Klaxons), not just visual pop-ups.

### 4.2 The Transcriptome Editor (The CAD Station)
When a player edits a blueprint, the UI shifts to a **Technical Drafting Table**.
* **Visual Style:** ISO Standard fonts, blueprint grids, dimension lines.
* **The "Signature":** The bottom right corner of the screen always displays the **Block Chain Header**: *Author: [User], Gen: [X], Hash: [0x123...]*.
* **Safety Feedback:** If the local AI flags a design, the error appears as a "Compiler Error" in a terminal window: *ERROR 403: Geometry Non-Compliant with Safety Protocols.*

---

## 5.0 TECHNICAL PIPELINE (IMPLEMENTATION)

### 5.1 The "Stalled Weather" Rendering
* **Volumetric Clouds:** We need a solution (like Horizon Zero Dawn’s cloud system) to render massive, stationary super-cells that cast real-time shadows.
* **The "Terminator" Line:** The transition between the Wet Zone and Dry Zone needs a custom blending shader.
    * *Visual:* A wall of rain. On one side, mud and gloom. On the other, cracked earth and blinding sun.

### 5.2 Generative Assets (Efficiency)
* **Problem:** Players need thousands of unique "Junk" parts to build with.
* **Solution:** We build a pipeline where we feed a basic mesh (e.g., "Wheel") into an Image-to-Material AI to generate 50 variants (Rusted, Painted, Rubber-Coated, Spiked) without manual artist labor.

### 5.3 Lidar Shader Tech
* **Implementation:** This is a post-processing effect using the **Depth Buffer** and **Normal Buffer**.
* **Edge Detection:** We run a Sobel filter on the Depth Buffer to create the "Wireframe" look efficiently.
* **Occlusion:** We use a "Pulse" shader that reveals geometry in waves, simulating the speed of the sensor sweep.

---

### DESIGNER'S NOTE ON "THE LOOK"
The critical success factor is **Legibility in Chaos**.
If the player says, "I can't see because it's dark," that is **Atmosphere**.
If the player says, "I can't see because the UI is messy," that is **Failure**.
The "Sensor Overlay" (Mode B) is our safety net. It allows us to make the world (Mode A) aggressively dark and hostile, because the player always has a high-tech flashlight to cut through it.