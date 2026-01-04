Here is the **Prototype Bill of Materials (BOM)** for the Iron Heart Mark II.

To keep this realistic for a first build (and mindful of your "garage engineering" context), I have sourced components that are available from industrial suppliers like McMaster-Carr, Grainger, or surplus outlets.

**Total Budget Estimate:** ~$3,500 - $4,500 (Assuming some fabrication skills and scavenging).

---

### **1. Zone 1: The Combustion Head (The "Hot" Zone)**

*This is the most critical safety component. It must withstand the 2500°C thermal shock and the 20+ Bar pressure spike.*

| Item | Component | Specification | Source/Notes | Est. Cost |
| --- | --- | --- | --- | --- |
| **C-200** | **Pressure Vessel Body** | 6" Schedule 80 Carbon Steel Pipe (1 ft length) + Class 300 Flanges | **McMaster-Carr.** The thick walls are essential for safety. | $450 |
| **C-Liner** | **Refractory Liner** | Castable Alumina Refractory (3000°F rated) | **Foundry Supply.** You will cast this *inside* the steel pipe to protect it. | $150 |
| **CUP-1** | **Suspension Cup** | Silicon Carbide (SiC) Crucible | **Kiln/Ceramic Supply.** Drill holes for suspension. This holds the pebble. | $80 |
| **V-101** | **Rotary Feeder** | Custom Steel Drum + NEMA 23 Stepper Motor | **Make.** 3D print the housing, but the drum *must* be metal (thermite is abrasive). | $150 |
| **IGN-202** | **Ignition System** | 10kV Oil Burner Transformer + Tungsten Electrodes | **HVAC Surplus.** Reliable, continuous arc capable. | $75 |
| **S-100** | **Blast Shield** | 1/4" Polycarbonate Sheet | **Local Supplier.** Do not run this without a blast shield. | $100 |

### **2. Zone 2: The Engine Body (The "Pressure" Zone)**

*This handles the water piston dynamics. We use standard piping to act as our cylinder.*

| Item | Component | Specification | Source/Notes | Est. Cost |
| --- | --- | --- | --- | --- |
| **U-300** | **U-Tube Assembly** | 6" Sch 80 Steel Pipe (4 ft total) + (2) 6" 90° Weld Elbows | **Local Metal/Pipe Yard.** Welding required. Flange the top for easy cleaning. | $600 |
| **V-203** | **Exhaust Valve** | 1" NPT Solenoid Valve (Steam Rated, Normally Closed) | **Automation Direct.** Must handle 180°C steam and open in <50ms. | $250 |
| **CV-301** | **Check Valve** | 1" Swing Check Valve (Brass or Stainless) | **Grainger.** Prevents the accumulator from back-driving the piston. | $80 |
| **E-400** | **Condenser** | 50ft of 1/2" Soft Copper Coil | **Home Depot.** Submerge this in a 55-gallon drum of cooling water. Simple. | $120 |
| **PT-201** | **Sensors** | 0-50 Bar Pressure Transducer + Optical Level Sensor | **Amazon/eBay.** For the control loop. | $150 |

### **3. Zone 3: Power & Hydraulics (The "Harvest" Zone)**

*This converts the water pressure into electricity.*

| Item | Component | Specification | Source/Notes | Est. Cost |
| --- | --- | --- | --- | --- |
| **A-500** | **Accumulator** | 1-Gallon Bladder Accumulator (3000 PSI rated) | **Hydraulic Surplus.** Essential for smoothing the 1Hz pulse. | $350 |
| **T-600** | **Turbine Nozzle** | 1/2" Adjustable Pelton Nozzle | **Micro-Hydro Supply.** Targets the jet at the wheel. | $60 |
| **T-WHEEL** | **Impulse Runner** | Pelton Wheel (4-6" diameter) | **eBay / Micro-Hydro.** Don't print this; the water hammer will shatter plastic. | $150 |
| **G-601** | **Generator** | Permanent Magnet Alternator (PMA) or Scooter Motor | **Surplus.** Look for low RPM / high torque (Wind turbine parts work well). | $200 |

### **4. Zone 4: The Slag Trap (The "Chemistry" Zone)**

*For the prototype, we are going to simplify the "Double Dump" valve to save $2,000. We will use a "Batch" collection system first.*

| Item | Component | Specification | Source/Notes | Est. Cost |
| --- | --- | --- | --- | --- |
| **V-302** | **Isolation Valve** | 2" Full Port Ball Valve (Stainless) | **Industrial Supply.** Manual operation for Prototype 1. Open only when system is OFF. | $120 |
| **R-700** | **Slag Pot** | Modified Propane Tank or Steel Pipe Cap | **Scrap/Make.** A catch-pot bolted to the bottom of the U-tube. | $50 |

### **5. Controls & Consumables**

| Item | Component | Specification | Source/Notes | Est. Cost |
| --- | --- | --- | --- | --- |
| **CPU** | **Controller** | Arduino Mega or ESP32 | **Electronics.** Needed for the precise 1Hz timing logic. | $30 |
| **FUEL** | **Thermite Mix** | Iron Oxide (Red) + Aluminum Powder (325 mesh) | **Chemical Supply / Paint Supply.** Buy in bulk (50 lbs) for testing. | $200 |
| **GAS** | **Nitrogen Tank** | Small Welding Tank | **Airgas.** To pre-charge the accumulator. | $100 |

---

### **Critical Build Notes for the "Texas Garage" Approach**

1. **The "Sch 80" Rule:** Do not use Schedule 40 pipe. Do not use PVC. The steam explosion creates a shockwave. Schedule 80 steel has the wall thickness to handle the fatigue of thousands of pulses.
2. **The "Slag" Reality:** In this prototype BOM, I swapped the automated slag airlock for a manual valve (**V-302**).
* *Why:* Automated high-temp abrasive valves cost $2,000+.
* *Operation:* For the first run, let the slag accumulate in the bottom "trap." After 50 pulses, stop the engine, close the safety valves, and empty the trap manually. Once the engine proves itself, we buy the expensive valves.


3. **The Welds:** The U-Tube (Zone 2) requires full-penetration welds. If you aren't a certified pipe welder, tack it together and take it to a local fab shop to have them run the final beads. A blown weld at 20 Bar is a pipe bomb.
