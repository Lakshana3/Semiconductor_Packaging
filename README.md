# Semiconductor_Packaging

A documentation of my learnings and hands-on projects from the **workshop on Packaging Fundamentals of Design and Technology** organized by **VSD-IAT**. This repository includes notes, lab exercises, and simulation outputs using ANSYS tools.

---

## Workshop Overview

This workshop bridges the gap between chip design and advanced semiconductor packaging technologies. Topics covered include:

- Packaging evolution: From traditional wire bonding to 2.5D/3D chiplet-based solutions
- Thermal simulations using ANSYS Electronics Desktop
- Reliability testing and failure analysis
- Package modeling and design using AEDT
- OSAT/ATMP plant processes and automation

---

## What I’m Learning

- Semiconductor package design fundamentals
- Flip-chip and wire-bonding assembly processes
- Thermal and mechanical reliability analysis
- Hands-on ANSYS simulations for package performance
- Real-world workflows in OSAT/ATMP plants

---

## Tools Used

- **ANSYS Electronics Desktop (AEDT)**
- **ANSYS Icepak**
- **ANSYS Q3D**
- **PCB Simulation and Analysis**

---

## Module-wise Documentation

| Module | Description |
|--------|-------------|
| Module 1 | Packaging Evolution & Fundamentals |
| Module 2 | Assembly & Manufacturing | 
| Module 3 | Thermal Simulations using ANSYS | 
| Module 4 | Package Reliability Testing | 
| Module 5 | Full Package Modeling & Design |

---

## Labs and Projects

- ⏳ **Flip-Chip BGA Thermal Simulation**
- ⏳ **Power Distribution on PCB**
- ⏳ **Chip-to-Board Integration**
- ⏳ **Signal and Power Integrity Design**

---

## Module 1 - Packaging Evolution: From Basics to 3D Integration

### L1 - Introduction To Semiconductor Packaging And Industry Overview

Semiconductor packaging is what transitions a delicate silicon die from a cleanroom environment into the real world—where it must withstand heat, moisture, physical stress, and electrical demands. It prepares the die for integration into electronic systems by offering protection, mechanical support, and electrical connectivity.

Without packaging, the tiny, fragile silicon chip cannot be connected to a PCB or used reliably in any application. For example, Ball Grid Array (BGA) packages are widely used in smartphones and laptops because they provide a compact, high-density way to mount chips with excellent electrical and thermal performance.

As technology advances, packaging has become critical to pushing performance boundaries while ensuring reliability.

![image](/Images/M1/L1/1.png)

In the semiconductor world, multiple players work together to bring a chip from concept to reality:
- Fabless companies like Qualcomm and AMD design chips but don’t manufacture them.
- Foundries such as TSMC and Samsung fabricate the chips on silicon wafers.
- Once wafers are ready, they go to OSAT (Outsourced Semiconductor Assembly and Test) companies like ASE, Amkor, and JCET for packaging and testing.

![image](/Images/M1/L1/2.png)

### L2 - Understanding Package Requirements And Foundational Package Types

![image](/Images/M1/L2/1.png)

Choosing the right semiconductor package depends on a mix of performance needs, form factor, thermal requirements, cost, and application type. For example, high-performance chips like processors may need flip-chip BGA for better thermal and electrical performance, while simpler applications can use QFN or SOIC for lower cost.

Key factors include:
- Electrical performance (signal integrity, power delivery)
- Thermal dissipation needs
- Size and footprint constraints
- Mechanical reliability
- Cost and manufacturing complexity

The goal is to strike the right balance between functionality, reliability, and economics while aligning with the end-use application.

![image](/Images/M1/L2/2.png)

A semiconductor package protects the integrated circuit (IC), provides electrical connections, and helps manage heat. Key components include:
1. Die (Chip): The silicon-based core that performs the circuit function.
2. Die Attach: Binds the die to the substrate or lead frame and aids heat transfer.
3. Substrate/Lead Frame: Provides mechanical support and routes electrical signals.
4. Wire Bonds/Solder Bumps: Connect the die to the substrate (wire bonds for traditional, solder bumps for flip-chip).
5. Molding Compound: Encapsulates and protects the die from environmental stress.
6. External Contacts (Pins/Balls): Enable connection to the PCB (e.g., pins in QFP, balls in BGA).
7. Thermal Solutions: Heat sinks or thermal pads may be added for high-power chips.
8. Marking: Labels like part numbers and logos for identification.

![image](/Images/M1/L2/3.png)

Semiconductor packages are broadly classified based on how they are mounted onto the PCB: Through-Hole Mounting and Surface-Mount Technology (SMT). The choice depends on performance needs, space constraints, and manufacturing considerations.

🔹 Through-Hole Mounting Packages
These have leads inserted into drilled PCB holes and soldered from the other side, offering strong mechanical bonds.
- Dual In-line Package (DIP)
- Pin Grid Array (PGA)
- Single In-line Package (SIP)
- Transistor Outline (TO) – Common for discrete devices like transistors and power ICs

🔹 Surface-Mount Technology (SMT) Packages
Mounted directly onto the PCB surface, enabling compact, high-density designs.
- Small Outline IC (SOIC)
- Quad Flat Package (QFP)
- Ball Grid Array (BGA) – Variants include Plastic BGA (PBGA), LGA (Land Grid Array)
- Chip Scale Package (CSP)
- Quad Flat No-Lead (QFN) – Excellent thermal and electrical performance in a compact form
- Flip Chip – Direct bump connections for high performance
- Package-on-Package (PoP) – Stacked packages, useful in mobile devices
- Multi-Chip Module (MCM) – Integrates multiple dies in one package
- CoWoS (Chip-on-Wafer-on-Substrate) – 2.5D/3D advanced packaging for high-end computing

### L3 - Evolving Package Architectures - From Single Chip To Multi-Chip Modules

🔹 Carrier and Interconnection Options
- Lead Frames – Used in DIP, QFP, SOIC
- Organic Substrates – Used in BGA, PoP, LGA
- Ceramic Substrates – For high reliability and thermal performance
- Interconnects – Wire bonds, solder bumps, TSVs (Through-Silicon Vias), and microbumps are used based on the package type and performance goals

Each package is selected based on application needs such as size, power, thermal performance, and assembly complexity. For example, CoWoS is suited for AI and HPC chips, while QFN fits compact consumer electronics.

![image](/Images/M1/L3/1.png)

Semiconductor packages are built using different base structures depending on the application, performance requirements, and integration complexity. These structures include leadframes, laminate substrates, and advanced package substrates.

1. Leadframe-Based Packages
Leadframes are metal frames (usually copper-based) used for simpler, cost-effective packages.

Examples:
- QFN (Quad Flat No-lead)
- DIP (Dual In-line Package)
  
Key Features:
- Good for low to medium pin count devices
- Used for analog, power, and general-purpose ICs
- Wire bonding used to connect the die to leads
- Efficient heat dissipation through exposed pads (in QFN)

2. Laminate-Based Packages
Laminate substrates are multi-layer organic PCBs with traces that route signals between the die and the external interface.

Examples:
- Wirebond PBGA (Plastic Ball Grid Array)
- Flip Chip PBGA
- LGA (Land Grid Array)
- FC-CSP (Flip Chip Chip-Scale Package)

Key Features:
- More routing capability than leadframes
- Supports higher I/O counts and finer pitch
- Flip chip and wire bond both supported
- Common in mobile, networking, and consumer electronics

3. Advanced Package Substrates
Used for high-performance and heterogeneous integration, especially in AI, HPC, and networking chips.

Types:
- 2D: Multiple chips side by side on the same substrate
- 2.1D: 2D packaging with passive interposers or bridge chips for enhanced routing
- 2.3D: Slightly elevated interconnect complexity with embedded dies or RDL (redistribution layers)
- 2.5D: Uses silicon interposers (e.g., CoWoS – Chip-on-Wafer-on-Substrate by TSMC) to connect multiple high-bandwidth dies
- 3D: Vertical die stacking using Through-Silicon Vias (TSVs)

Key Features:
- Enables chiplet-based designs
- High bandwidth, low latency interconnects
- Expensive but essential for advanced computing applications

Each of these architectures forms the physical backbone of the IC package, determining its performance, size, thermal behavior, and integration capability.

![image](/Images/M1/L3/2.png)

### L4 - Interposers Re-distribution Layers And 2.5D/3D Packaging Approaches

As chips become more powerful and compact, advanced packaging methods like 2.5D and 3D integration help overcome traditional limits. These rely on interposers and redistribution layers (RDLs) for high-density, high-performance interconnects.

🔹 Interposers
Interposers are intermediate substrates (silicon, glass, or organic) used to route signals between dies or to the package. Common in 2.5D packaging, they allow multiple chips (like logic and memory) to sit side-by-side on a shared platform.
Example: TSMC’s CoWoS (used in GPUs with HBM).

🔹 Redistribution Layers (RDLs)
RDLs are added metal layers that reroute chip I/Os, enabling finer-pitch connections. They’re essential in fan-out packages and advanced RDL interposers (used in 2.1D/2.3D packages).

🔹 2.5D vs 3D Packaging
- 2.5D: Uses interposers to connect side-by-side dies with high bandwidth.
- 3D: Stacks dies vertically with Through-Silicon Vias (TSVs), saving space and improving performance.

| Approach  | Key Element            | Example       |
| --------- | ---------------------- | ------------- |
| 2.1D/2.3D | RDL on substrate       | TSMC InFO     |
| 2.5D      | Silicon Interposer     | CoWoS, EMIB   |
| 3D        | Die stacking with TSVs | Intel Foveros |

![image](/Images/M1/L4/1.png)

![image](/Images/M1/L4/2.png)

### L5 - Comparative Analysis And Selecting The Right Packaging Solution

![image](/Images/M1/L5/1.png)

![image](/Images/M1/L5/2.png)

---
  
## Module2 - From Wafer to Package: Assembly and Manufacturing Essentials

### L1 - Setting The Stage - Supply Chain And Facilities

The semiconductor supply chain flows through several specialized stages, each with distinct inputs and outputs:
1. Design House
📍 Function: Develops the chip’s architecture and RTL.
🔧 Input: Product requirements, IP blocks
📤 Output: GDSII layout files for fabrication
2. Wafer Fabrication (Foundry)
📍 Function: Translates design into silicon wafers using photolithography and deposition.
🔧 Input: GDSII files, silicon wafers, process recipes
📤 Output: Processed wafers with individual dies
3. Package Assembly and Test (OSAT)
📍 Function: Cuts wafers, packages dies, and performs electrical testing.
🔧 Input: Known Good Dies (KGD)
📤 Output: Packaged and tested chips ready for integration
4. Board Assembly and Test (EMS/ODM)
📍 Function: Mounts chips and components onto printed circuit boards (PCBs).
🔧 Input: Packaged ICs, passive components, PCBs
📤 Output: Fully assembled and tested circuit boards
5. Product Assembly and Test (OEM)
📍 Function: Integrates PCBs into the final device (e.g., smartphones, laptops).
🔧 Input: Assembled boards, enclosures, batteries, displays
📤 Output: Finished electronic products, tested and ready for shipment
This global supply chain spans fabless companies, foundries, OSATs, EMS providers, and OEMs, each playing a vital role in bringing semiconductor products to life.

![image](/Images/M2/L1/1.png)

ATMP (Assembly, Testing, Marking, and Packaging) units are specialized facilities where semiconductor dies are packaged, tested, and prepared for system integration.
These units handle processes like:
- Die attach and wire bonding or flip chip assembly
- Encapsulation, marking, and package singulation
- Electrical testing to ensure functionality and reliability

Organization & Layout:

A typical ATMP facility is divided into:
- Material prep & backend zones: for wafer inspection, dicing, die attach
- Cleanroom area: for fine-pitch assembly and wire bonding
- Testing zones: for final electrical and thermal testing

![image](/Images/M2/L1/2.png)

### L2 - Wafer Pre-Preparation - Grinding And Dicing

Inside the Cleanroom:

The cleanroom maintains a highly controlled environment (e.g., ISO Class 5–7) to prevent contamination during sensitive processes such as:
- Die placement
- Precision bonding
- Micro soldering and underfill dispensing
These controlled conditions are crucial for yield, especially in high-density packages like BGA and 2.5D/3D ICs.

![image](/Images/M2/L2/1.png)

### L3 - Wire Bond Packaging - Die Attach To Molding

Cleanroom Activities in Wire Bond Packaging: 

Inside the cleanroom, the wire bond packaging process involves a series of precise and contamination-sensitive steps:
- Die Attach – The silicon die is carefully placed onto the substrate or lead frame using adhesive.
- Curing – The adhesive is cured (usually thermally) to firmly bond the die.
- Wire Bonding – Ultra-fine gold or copper wires connect the die pads to the package leads using thermosonic bonding.
- Molding – An encapsulant material is applied to protect the die and wires from mechanical and environmental stress.
- Marking – The packaged units are labeled with ID codes or logos for traceability.
- Singulation – The molded packages are cut from the panel or strip into individual units.
  
All these steps are performed in a cleanroom to avoid dust or particle contamination, which can severely impact yield and reliability in high-density semiconductor packages.

![image](/Images/M2/L3/1.png)

![image](/Images/M2/L3/2.png)

### L4 - Flip Chip Assembly - Bump Formation And Underfill

Cleanroom Activities in Flip-Chip Packaging:

In flip-chip packaging, the die is mounted face-down directly onto the substrate, enabling high-density interconnections and better performance. Inside the cleanroom, the process includes:
- Bump Formation – Tiny solder bumps are created on the die pads using techniques like electroplating or solder paste printing.
- Reflow – The bumped die is flipped and aligned with the substrate; then heat is applied to reflow the solder and form robust electrical and mechanical connections.
- Underfill Dispensing – An epoxy is applied between the die and substrate to absorb mechanical stress and enhance reliability.
- Curing – The underfill is thermally cured to harden and fix in place.
- Encapsulation (Optional) – Additional protection may be applied, depending on the package type.
- Inspection & Testing – Optical or X-ray inspection ensures alignment, bump integrity, and connection quality.

These steps are performed in a cleanroom to prevent contamination, which is critical for maintaining precision alignment and avoiding solder defect issues.

![image](/Images/M2/L4/1.png)

### L5 - Wafer Level Packaging And Conclusion

Cleanroom Activities in Wafer Level Packaging:

Fan-Out Wafer-Level Packaging (FOWLP) involves reconstitution and redistribution layers (RDL) preparation. Inside the cleanroom, the key activities for FOWLP include:

1. Reconstitution: The wafer is reconstituted by attaching multiple chips to a carrier wafer, creating a large surface area for the redistribution layer. This step helps in accommodating more I/O connections compared to traditional wafer-level packages.
2. RDL (Redistribution Layer) Preparation: After reconstitution, RDL is applied to connect the I/O pads of the die to the external leads or bumps. This involves photolithography, deposition of conductive materials (like copper), and etching processes to form the interconnects.
3. Die Attach: The individual dies are placed on the reconstituted wafer, and adhesive or solder is used to bond them to the carrier wafer.
4. Molding and Encapsulation: A protective molding compound is applied over the entire assembly, ensuring protection and mechanical support for the dies.
5. Testing and Inspection: The package undergoes testing and inspection to verify functionality, electrical performance, and quality.
6. Singulation: After the package has been molded and cured, the reconstituted wafer is diced into individual packages.

FOWLP enables higher performance, smaller form factors, and more I/O options, making it suitable for advanced semiconductor applications like mobile devices and high-performance computing.

![image](/Images/M2/L5/1.png)

![image](/Images/M2/L5/2.png)

---

## Module 3 - Labs: Thermal Simulation of Semiconductor Packages with ANSYS

### L1 - Introduction And Getting Started With ANSYS Electronics Desktop

ANSYS Electronics Desktop provides several tools for designing, analyzing, and optimizing electronic systems. 

Download, install and open Ansys Electronics Desktop Student 2024 R2.

Key tools include:
1. HFSS: 3D electromagnetic simulation for high-frequency components like antennas and RF circuits.
2. Maxwell: Electromagnetic field simulation for low-frequency components such as motors and transformers.
3. Q3D Extractor: Extracts parasitic RLC values for interconnects, analyzing signal and power integrity.
4. Icepak: Thermal simulation for electronics, optimizing cooling systems and heat management.
5. Simplorer: Multi-domain simulation for integrated systems, including electrical, mechanical, and thermal systems.
These tools enable efficient design and optimization of a wide range of electronic devices and systems.

Here we'll use Icepak to do thermal analysis of packages. 

![image](/Images/M3/L1/1.png)

Select Icepak tool. 
Under project manager window these can be found:
- 3D Components: Import or create electronic components for thermal simulation.
- Model: Define system geometry and component placement.
- Thermal: Assign thermal properties, power dissipation, and boundary conditions.
- Monitor: Track temperature and thermal metrics during simulation.
- Solar Loading: Simulate effects of solar radiation on the system.
- Mesh: Generate computational mesh for accurate heat transfer and airflow simulation.
- Analysis: Set solver options and run thermal simulations (steady-state/transient).
- Optometrics: Study parametric variations and radiation/optical effects.
- Results: Visualize simulation outputs like temperature maps.
- Field Overlays: Add visual data (contours, vectors) onto geometry for interpretation.

![image](/Images/M3/L1/3.png)

Import the in-built package FlipChip_BGA. 

![image](/Images/M3/L1/4.png)

### L2 - Setting Up A Flip-Chip BGA Package

When creating a Flip Chip BGA (FCBGA) package in Ansys Icepak or similar EDA tools, the following key elements can be defined:

🔹 1. Package Dimensions
- Package body size (length × width × height)
- Ball pitch and ball array size
- Standoff height (distance from substrate to die or board)
- Die placement (centered or offset)

![image](/Images/M3/L2/1.png)

🔹 2. Substrate
- Material (e.g., BT resin, ABF, ceramic)
- Layer stack-up (number of layers, thicknesses)
- Thermal conductivity
- Via structure and routing design
- CTE matching (to die and board)

![image](/Images/M3/L2/2.png)

🔹 3. Solder Bumps / Balls
- Bump material (e.g., SnAgCu, SAC305)
- Bump height and diameter
- Ball array layout (full, partial, or custom)
- Underfill material (optional, for reliability)

![image](/Images/M3/L2/3.png)

🔹 4. Die
- Die size (length × width × thickness)
- Material (typically silicon)
- Power dissipation (W)
- Power map (uniform or localized hot spots)
- Bump map (custom or standard layout)

![image](/Images/M3/L2/4.png)

![image](/Images/M3/L2/5.png)

![image](/Images/M3/L2/6.png)

![image](/Images/M3/L2/7.png)

![image](/Images/M3/L2/8.png)

![image](/Images/M3/L2/9.png)

![image](/Images/M3/L2/10.png)

![image](/Images/M3/L2/11.png)

![image](/Images/M3/L2/12.png)

![image](/Images/M3/L2/13.png)

### L3 - Material Definitions And Thermal Power Sources

Clicking Model shows the design list. 

![image](/Images/M3/L3/1.png)

Mention thermal condition for die source as boundary condition. 

![image](/Images/M3/L3/2.png)

![image](/Images/M3/L3/3.png)

Mention source boundary condition on the substrate.

![image](/Images/M3/L3/4.png)

![image](/Images/M3/L3/5.png)

![image](/Images/M3/L3/6.png)

![image](/Images/M3/L3/7.png)

Remove boundary source as it overlaps.

![image](/Images/M3/L3/9.png)

![image](/Images/M3/L3/10.png)

Add monitor on substrate.

![image](/Images/M3/L3/11.png)

![image](/Images/M3/L3/12.png)

![image](/Images/M3/L3/13.png)

Add monitor on die.

![image](/Images/M3/L3/14.png)

![image](/Images/M3/L3/15.png)

Assign monitor on die underfill.

![image](/Images/M3/L3/16.png)

Select Temperature.  

![image](/Images/M3/L3/17.png)

![image](/Images/M3/L3/18.png)

### L4 - Meshing And Running The Thermal Analysis

Go to simulation and generate mesh. 

![image](/Images/M3/L4/1.png)

![image](/Images/M3/L4/2.png)

Save project.

![image](/Images/M3/L4/3.png)

Mesh is being generated.

![image](/Images/M3/L4/4.png)

Mesh is visualized. 

![image](/Images/M3/L4/6.png)

Mesh quality is visualized through 3 bar charts - face alignment, volume and skewness.

![image](/Images/M3/L4/7.png)

![image](/Images/M3/L4/8.png)

![image](/Images/M3/L4/9.png)

Mesh operation is done.

![image](/Images/M3/L4/10.png)

For analysis, add a solution step. 

![image](/Images/M3/L4/11.png)

![image](/Images/M3/L4/12.png)

![image](/Images/M3/L4/13.png)

![image](/Images/M3/L4/14.png)

![image](/Images/M3/L4/15.png)

![image](/Images/M3/L4/16.png)

Validate check.

![image](/Images/M3/L4/17.png)

To fix the warning, assign mesh to the object.

![image](/Images/M3/L4/18.png)

![image](/Images/M3/L4/19.png)

![image](/Images/M3/L4/20.png)

![image](/Images/M3/L4/21.png)

![image](/Images/M3/L4/22.png)

![image](/Images/M3/L4/23.png)

![image](/Images/M3/L4/24.png)

![image](/Images/M3/L4/25.png)

![image](/Images/M3/L4/26.png)

![image](/Images/M3/L4/27.png)

![image](/Images/M3/L4/28.png)

### L5 - Viewing Results And Exploring Other Package Types

![image](/Images/M3/L5/1.png)

FlipChip_BGA mesh evealuation is shown after deleting the mesh region and rerunning generate mesh.

![image](/Images/M3/L5/2.png)

![image](/Images/M3/L5/3.png)

![image](/Images/M3/L5/4.png)

![image](/Images/M3/L5/5.png)

Check validation. 

![image](/Images/M3/L5/6.png)

![image](/Images/M3/L5/7.png)

Click Analyze all. 

![image](/Images/M3/L5/8.png)

![image](/Images/M3/L5/9.png)

Add plot fields for the entire package. 

![image](/Images/M3/L5/10.png)

Create field plot for temperature.

![image](/Images/M3/L5/11.png)

![image](/Images/M3/L5/12.png)

![image](/Images/M3/L5/13.png)

The thermal map for FLiChip_BGA package is shown.

![image](/Images/M3/L5/14.png)

![image](/Images/M3/L5/15.png)

![image](/Images/M3/L5/16.png)

---

## Module 4 - Ensuring Package Reliability: Testing and Performance Validation

### L1 - Introduction to Package Testing and Electrical Functionality Checks

Testing is crucial to ensure semiconductor packages function reliably. It occurs at different stages of the manufacturing process: during wafer fabrication at the foundry and after packaging at the OSAT (Outsourced Semiconductor Assembly and Test) facility.

Foundry Testing

1. Wafer Probe Testing: Electrical testing of individual chips on the wafer.
2. Parametric Testing: Measurement of electrical characteristics like voltage and current.
3. Burn-In Testing: Exposure to elevated temperature and voltage to detect early failures.
4. Die Sorting: Categorizing good and bad dies based on test results.

OSAT Testing

1. Package-Level Electrical Testing: Ensures proper electrical connections in the package.
2. X-ray/Visual Inspection: Detects internal and external defects.
3. Mechanical Stress Testing: Simulates mechanical forces to check package robustness.
4. Thermal Cycling/Shock Testing: Simulates temperature extremes to test thermal durability.
5. Burn-In Testing (Continued): Tests package reliability under full operational conditions.
6. Functional Testing: Verifies the chip’s intended functions.
7. Reliability Testing: Includes ESD, humidity, and pressure testing to ensure durability.
8. Final Inspection/Marking: Ensures the package is free of defects and properly labeled.

These testing stages ensure the semiconductor package's performance, reliability, and durability before reaching the customer.

![image](/Images/M4/L1/1.png)

Package Testing

1. AOST (Automated Optical and Scan Testing): Inspects packages for defects like misalignment, wire bond issues, and solder defects using automated systems.
2. Burn-in Testing: Exposes packages to high temperatures and voltages to identify early failures and ensure long-term reliability.
3. Final Test: Verifies the electrical functionality and performance of the package under normal conditions, ensuring it meets quality standards.

These tests ensure the reliability and functionality of the semiconductor package throughout its lifecycle.

![image](/Images/M4/L1/2.png)

![image](/Images/M4/L1/3.png)

### L2 - Reliability and Performance Testing of Semiconductor Packages

![image](/Images/M4/L2/1.png)

![image](/Images/M4/L2/2.png)

![image](/Images/M4/L2/3.png)

---

## Module 5 - Package Design and Modeling: Building a Semiconductor Package from Scratch

### L1 - Introduction to Package Cross-Section Modeling in ANSYS Electronics Desktop (AEDT)

In this lab, we create a semiconductor package cross-section inAnsys AEDT.

![image](/Images/M5/L1/1.png)

### L2 - Creating the Die and Substrate in AEDT

Create a die of 3mm x 3mm at (0,0,0) with thickness 0.2mm.
First create a rectangle, and modify the dimensions. 
![image](/Images/M5/L2/1.png)

![image](/Images/M5/L2/2.png)

![image](/Images/M5/L2/3.png)

![image](/Images/M5/L2/4.png)

![image](/Images/M5/L2/5.png)

Thicken the sheet by 0.2mm.

![image](/Images/M5/L2/6.png)

![image](/Images/M5/L2/7.png)

![image](/Images/M5/L2/8.png)

Modify the material. 

![image](/Images/M5/L2/9.png)

![image](/Images/M5/L2/10.png)

Create another rectangle for substrate and assign thickness 0.5mm.

![image](/Images/M5/L2/11.png)

![image](/Images/M5/L2/12.png)

![image](/Images/M5/L2/13.png)

![image](/Images/M5/L2/14.png)

![image](/Images/M5/L2/15.png)

![image](/Images/M5/L2/16.png)

Modify dimensions to have die on top of substrate.

![image](/Images/M5/L2/17.png)

![image](/Images/M5/L2/18.png)

![image](/Images/M5/L2/19.png)

### L3 - Adding Die Attach Material and Bond Pads

Add die attach material made of epoxy and assign thickness 0.1mm. 

![image](/Images/M5/L3/1.png)

![image](/Images/M5/L3/2.png)

![image](/Images/M5/L3/3.png)

![image](/Images/M5/L3/4.png)

![image](/Images/M5/L3/5.png)

![image](/Images/M5/L3/6.png)

![image](/Images/M5/L3/7.png)

![image](/Images/M5/L3/8.png)

![image](/Images/M5/L3/9.png)

![image](/Images/M5/L3/10.png)

Substrate:

![image](/Images/M5/L3/11.png)

Die Underfill:

![image](/Images/M5/L3/12.png)

Die:

![image](/Images/M5/L3/13.png)

Create die bond pads with a thickness of 0.005mm.

![image](/Images/M5/L3/14.png)

![image](/Images/M5/L3/15.png)

![image](/Images/M5/L3/16.png)

![image](/Images/M5/L3/17.png)

Create substrate bond pads and name each accordingly.

![image](/Images/M5/L3/18.png)

![image](/Images/M5/L3/19.png)

![image](/Images/M5/L3/20.png)

![image](/Images/M5/L3/21.png)

![image](/Images/M5/L3/22.png)

Choose bond wire to make a connection between substrate and die. 

![image](/Images/M5/L3/23.png)

### L4 - Wire Bond Creation and Material Assignment

Click and drag bond wire from dice to substrate.
![image](/Images/M5/L4/1.png)

![image](/Images/M5/L4/2.png)

![image](/Images/M5/L4/3.png)

![image](/Images/M5/L4/4.png)

![image](/Images/M5/L4/5.png)

![image](/Images/M5/L4/6.png)

![image](/Images/M5/L4/7.png)

![image](/Images/M5/L4/8.png)

![image](/Images/M5/L4/9.png)

![image](/Images/M5/L4/10.png)

![image](/Images/M5/L4/11.png)

![image](/Images/M5/L4/12.png)

![image](/Images/M5/L4/13.png)

### L5 - Applying Mold Compound and Finalizing the Package Model

![image](/Images/M5/L5/1.png)

![image](/Images/M5/L5/2.png)

![image](/Images/M5/L5/3.png)

![image](/Images/M5/L5/4.png)

![image](/Images/M5/L5/5.png)

![image](/Images/M5/L5/6.png)

---

## Acknowledgements

I extend my sincere gratitude to Mr. Kunal Ghosh for providing this opportunity to participate in the Packaging Fundamentals of Design and Technology workshop and to Dr. Tarun Kumar Agarwal and his dedicated team for sharing their profound expertise throughout the workshop.
