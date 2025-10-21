# Mechanical Team - Task Distribution Document
## WorkSafeBot: Pipe Inspection Robot

**Project:** WorkSafeBot - Autonomous Safety & Pipe Inspection Robot  
**Competition:** Techfest IIT Bombay 2025 - Safetronics Challenge  
**Theme:** Theme 3 – Safe Workspace  
**Document Version:** 1.0  
**Date:** October 21, 2025

---

## 1. Overview & Objectives

### 1.1 Project Context
A modular pipe inspection robot is being developed to navigate through industrial pipelines (75-150mm diameter) for safety monitoring and defect detection. The robot must operate autonomously in horizontal, vertical, and angled pipe orientations while carrying sensors, camera modules, and electronics within strict weight and budget constraints.

### 1.2 Mechanical Team Responsibilities
The mechanical subsystem is responsible for the structural design, locomotion mechanisms, sensor housing, and physical integration of all components. All mechanical designs must be optimized for manufacturability, cost-effectiveness, and seamless integration with the electronics and AI/ML subsystems.

### 1.3 Primary Objectives
- A lightweight chassis (≤3kg total robot weight) must be designed and fabricated
- Adaptability to pipe diameters ranging from 75mm to 150mm must be achieved
- Reliable locomotion in horizontal, vertical, and angled orientations must be ensured
- Secure mounting points for sensors, camera, microcontroller, and power system must be provided
- Modular design philosophy must be maintained for easy assembly, maintenance, and upgrades
- Budget allocation of approximately ₹500 for mechanical components must be adhered to

---

## 2. Design Requirements & Constraints

### 2.1 Dimensional Specifications
- **Pipe Diameter Range:** 75mm to 150mm (3 to 6 inches)
- **Robot Length:** 150mm to 200mm (compact design for maneuverability)
- **Robot Width:** Adjustable based on pipe diameter (collapsible/expandable mechanism)
- **Ground Clearance:** Minimal (≤10mm) for low-profile navigation

### 2.2 Weight & Load Specifications
- **Total Robot Weight:** ≤3kg (including all subsystems)
- **Mechanical Subsystem Target Weight:** ≤800g
- **Payload Capacity:** 500g minimum (for sensors, electronics, battery)
- **Safety Factor:** 1.5x for structural components

### 2.3 Performance Requirements
- **Operating Orientations:** Horizontal, vertical (±90°), angled (±45°)
- **Traction Force:** Sufficient to climb vertical pipes without slipping
- **Speed:** 5-10 cm/s (adjustable based on inspection requirements)
- **Runtime:** 30-60 minutes per charge (mechanical design must minimize friction losses)
- **Turning Radius:** Capable of navigating 90° bends (miter bends) in pipes

### 2.4 Material & Budget Constraints
- **Budget Allocation:** ₹500 maximum for mechanical components
- **Material Preference:** Lightweight aluminum, acrylic, PLA/PETG (3D printing), or ABS
- **Fabrication Methods:** 3D printing, laser cutting, basic machining (drilling, tapping)
- **Fasteners:** Standard M3/M4 bolts, nuts, washers (readily available)

### 2.5 Environmental Considerations
- **Pipe Materials:** Metal (steel, aluminum) and PVC pipes must be accommodated
- **Surface Conditions:** Smooth, rough, corroded, or wet pipe interiors
- **Temperature Range:** 10°C to 50°C (industrial environment)
- **Dust/Debris:** Design must prevent debris accumulation in moving parts

---

## 3. Chassis Design & Structure

### 3.1 Main Chassis Frame
A central chassis frame must be designed to serve as the structural backbone of the robot. The following specifications must be met:

- **Material:** Lightweight aluminum extrusion (20x20mm or 15x15mm) or 3D-printed PLA/PETG
- **Configuration:** Rectangular or cylindrical frame with mounting points for all subsystems
- **Modularity:** Detachable sections for easy access to electronics and sensors
- **Rigidity:** Sufficient stiffness to prevent flexing under load (FEA analysis recommended)
- **Cable Management:** Internal channels or clips for routing sensor cables and power wires

### 3.2 Modular Design Philosophy
The chassis must be designed with modularity in mind:

- **Sensor Mounting Plates:** Removable plates for VL53L0X, MQ sensors, DHT11, MPU6050
- **Camera Module Housing:** Adjustable front-mounted bracket for ESP32-CAM or endoscope camera
- **Electronics Bay:** Enclosed compartment for microcontroller, motor drivers, and wiring
- **Battery Compartment:** Secure, accessible housing for Li-ion battery pack (hot-swap capability preferred)
- **Expansion Slots:** Provision for future sensor additions or upgrades

### 3.3 Structural Analysis
Before fabrication, the following analyses must be conducted:

- **Finite Element Analysis (FEA):** Stress distribution under maximum load conditions
- **Weight Optimization:** Topology optimization to reduce material usage while maintaining strength
- **Center of Gravity (CoG):** CoG must be positioned centrally for balanced locomotion
- **Vibration Analysis:** Natural frequencies must be identified to avoid resonance with motor vibrations

---

## 4. Locomotion System Design

### 4.1 Drive Mechanism Selection
A differential drive or caterpillar traction system must be implemented:

#### 4.1.1 Differential Drive Configuration
- **Motor Placement:** Two high-torque geared DC motors (100-300 RPM) mounted on opposite sides
- **Wheel Design:** Rubber or silicone wheels (40-60mm diameter) for high traction
- **Wheel Mounting:** Direct shaft coupling or hub-based mounting with set screws
- **Turning Mechanism:** Differential speed control for in-place rotation

#### 4.1.2 Caterpillar/Track System (Alternative)
- **Track Material:** Rubber or silicone tracks with textured surface for grip
- **Sprocket Design:** 3D-printed or machined sprockets with appropriate tooth profile
- **Tensioning Mechanism:** Adjustable tensioners to maintain track tightness
- **Advantages:** Better traction on rough surfaces, distributed load

### 4.2 Motor Mounting & Coupling
- **Motor Brackets:** Custom-designed brackets to securely mount motors to chassis
- **Alignment:** Precise alignment to prevent binding or uneven load distribution
- **Vibration Dampening:** Rubber grommets or dampers to isolate motor vibrations
- **Shaft Couplers:** Flexible couplers to accommodate minor misalignments

### 4.3 Gear Reduction & Torque Transmission
- **Gear Ratio:** Appropriate gear reduction (10:1 to 50:1) for sufficient torque
- **Gearbox Selection:** Planetary or spur gearboxes based on space and torque requirements
- **Lubrication:** Grease or oil lubrication for smooth operation and longevity

---

## 5. Wall-Press Mechanism for Vertical Climbing

### 5.1 Mechanism Overview
A wall-press mechanism must be designed to maintain contact with pipe walls during vertical navigation. This mechanism is critical for preventing slippage and ensuring stable locomotion.

### 5.2 Design Approaches

#### 5.2.1 Spring-Loaded Arm System
- **Configuration:** Two or four spring-loaded arms extending radially from the chassis
- **Spring Selection:** Compression springs with appropriate stiffness (force calculation required)
- **Contact Pads:** Rubber or silicone pads at arm ends for friction and grip
- **Adjustability:** Mechanism must adapt to different pipe diameters (75-150mm range)

#### 5.2.2 Servo-Actuated Expandable Frame
- **Actuation:** Servo motors (MG90S or similar) to actively adjust arm extension
- **Control:** Feedback from VL53L0X sensors to maintain optimal wall contact force
- **Advantages:** Active control, better adaptability, real-time adjustment

#### 5.2.3 Scissor Mechanism
- **Design:** Scissor-linkage mechanism for radial expansion/contraction
- **Actuation:** Single servo or lead screw for synchronized arm movement
- **Compactness:** Folds into compact configuration for narrow pipes

### 5.3 Force Calculations
The following calculations must be performed:

- **Normal Force:** Minimum force required to prevent slippage (F_normal = μ × F_gravity / sin(θ))
- **Spring Constant:** Appropriate spring stiffness to maintain contact without excessive force
- **Friction Coefficient:** Material selection based on pipe surface (rubber on metal: μ ≈ 0.6-0.8)
- **Safety Margin:** 1.5x safety factor for vertical climbing

### 5.4 Material Selection for Contact Pads
- **Material:** High-friction rubber, silicone, or TPU (3D-printable)
- **Durability:** Abrasion-resistant for extended use
- **Compliance:** Soft enough to conform to pipe surface irregularities

---

## 6. Pipe Diameter Adaptability Mechanism

### 6.1 Adjustable Chassis Width
A mechanism for adapting to different pipe diameters must be implemented:

- **Telescoping Frame:** Sliding rails or telescoping tubes for width adjustment
- **Locking Mechanism:** Quick-release pins or clamps to secure at desired width
- **Calibration Marks:** Visual indicators for common pipe sizes (75mm, 100mm, 125mm, 150mm)

### 6.2 Sensor-Based Auto-Adjustment (Advanced)
- **Feedback Loop:** VL53L0X ToF sensors measure distance to pipe walls
- **Servo Control:** Servos adjust wall-press arms to maintain optimal contact
- **Algorithm Integration:** Coordination with AI/ML team for autonomous adjustment logic

---

## 7. Sensor & Electronics Housing

### 7.1 Sensor Mounting Requirements
Secure and accessible mounting points must be provided for the following sensors:

#### 7.1.1 VL53L0X Time-of-Flight Sensors (2-3 units)
- **Placement:** Front, sides, or radial arrangement for obstacle detection and centering
- **Mounting:** Adjustable brackets with ±15° tilt capability
- **Protection:** Transparent acrylic or polycarbonate covers to prevent damage

#### 7.1.2 MQ Gas Sensors (MQ-2 or MQ-9)
- **Placement:** Front-facing for gas leak detection
- **Ventilation:** Open design to allow airflow for accurate readings
- **Isolation:** Separated from heat-generating components (motors, electronics)

#### 7.1.3 DHT11 Temperature & Humidity Sensor
- **Placement:** Exposed to ambient air, away from heat sources
- **Mounting:** Snap-fit or screw-mounted bracket

#### 7.1.4 MPU6050 IMU (Inertial Measurement Unit)
- **Placement:** Centrally located on chassis for accurate orientation sensing
- **Vibration Isolation:** Foam or rubber dampers to minimize motor vibration interference

#### 7.1.5 ESP32-CAM or Endoscope Camera
- **Placement:** Front-mounted with adjustable tilt (±30°)
- **Protection:** Transparent dome or lens cover
- **Illumination:** Provision for LED ring light or strip for low-light conditions

### 7.2 Electronics Bay Design
- **Enclosure:** Dust-proof compartment for microcontroller, motor drivers, and wiring
- **Access:** Hinged or removable cover for easy maintenance
- **Cooling:** Ventilation slots or small fan for heat dissipation
- **Cable Routing:** Organized cable management with strain relief

### 7.3 Power System Housing
- **Battery Compartment:** Secure housing for 2S or 3S Li-ion battery pack
- **Hot-Swap Design:** Quick-release mechanism for battery replacement without disassembly
- **Safety:** Insulated compartment to prevent short circuits
- **Weight Distribution:** Battery placement to optimize CoG

---

## 8. Material Selection & Sourcing

### 8.1 Recommended Materials

| Component | Material | Justification | Estimated Cost |
|-----------|----------|---------------|----------------|
| Main Chassis | Aluminum Extrusion (20x20mm) | Lightweight, rigid, easy to machine | ₹150-200 |
| Mounting Plates | 3mm Acrylic Sheet | Transparent, laser-cuttable, affordable | ₹50-80 |
| Wall-Press Arms | 3D-Printed PLA/PETG | Customizable, lightweight, cost-effective | ₹30-50 |
| Contact Pads | Silicone or TPU | High friction, durable, compliant | ₹40-60 |
| Wheels/Tracks | Rubber or Silicone | High traction, wear-resistant | ₹60-100 |
| Fasteners | M3/M4 Bolts, Nuts, Washers | Standard, readily available | ₹30-50 |
| Springs | Compression Springs (various sizes) | Force adjustment for wall-press | ₹20-40 |
| **Total** | | | **₹380-580** |

### 8.2 Sourcing Recommendations
- **Local Hardware Stores:** Fasteners, aluminum extrusions, springs
- **Online Suppliers:** Amazon India, Robu.in, RoboticsDNA for specialized components
- **3D Printing Services:** Local makerspaces or online services (if in-house printing unavailable)
- **Acrylic Sheets:** Local plastic suppliers or laser-cutting services

---

## 9. Fabrication & Assembly

### 9.1 CAD Modeling
Detailed 3D CAD models must be created using:

- **Software:** SolidWorks, Fusion 360, or FreeCAD (open-source)
- **Assembly Model:** Complete robot assembly with all components
- **Part Drawings:** Individual part drawings with dimensions, tolerances, and material specifications
- **Bill of Materials (BOM):** Comprehensive list of all parts with quantities and sources

### 9.2 Prototyping
A functional prototype must be fabricated for testing:

- **3D Printing:** PLA or PETG for chassis components, brackets, and custom parts
- **Laser Cutting:** Acrylic sheets for mounting plates and covers
- **Machining:** Drilling, tapping, and cutting of aluminum extrusions
- **Assembly:** Step-by-step assembly following documented procedures

### 9.3 Tolerances & Fit
- **Clearance Fits:** 0.2-0.5mm clearance for sliding parts
- **Press Fits:** 0.05-0.1mm interference for permanent joints
- **Thread Engagement:** Minimum 1.5x bolt diameter for secure fastening

### 9.4 Surface Finishing
- **Deburring:** Remove sharp edges from cut or machined parts
- **Sanding:** Smooth 3D-printed surfaces for better aesthetics and fit
- **Painting/Coating:** Optional protective coating for aluminum parts

---

## 10. Testing & Validation

### 10.1 Mechanical Testing
The following tests must be conducted before integration:

#### 10.1.1 Load Testing
- **Static Load:** Apply maximum expected load (500g) and verify no deformation
- **Dynamic Load:** Simulate operational loads during movement and climbing

#### 10.1.2 Traction Testing
- **Horizontal Surface:** Verify sufficient traction on smooth and rough surfaces
- **Vertical Climbing:** Test wall-press mechanism on vertical pipes (75mm, 100mm, 150mm)
- **Slippage Test:** Measure maximum angle before slippage occurs

#### 10.1.3 Durability Testing
- **Cyclic Loading:** 100+ cycles of expansion/contraction for wall-press mechanism
- **Vibration Test:** Operate motors at full speed for 30 minutes, check for loosening or wear

#### 10.1.4 Dimensional Verification
- **Pipe Diameter Range:** Verify adaptability across 75-150mm range
- **Clearance Checks:** Ensure no interference between moving parts

### 10.2 Integration Testing
- **Electronics Integration:** Mount all sensors, microcontroller, and battery; verify fit and accessibility
- **Cable Management:** Ensure cables do not interfere with moving parts
- **Weight Verification:** Confirm total weight ≤3kg

### 10.3 Field Testing
- **Horizontal Pipe Navigation:** Test in straight and curved pipes
- **Vertical Pipe Climbing:** Test in vertical pipes with different surface finishes
- **Obstacle Navigation:** Test response to bends, joints, and minor obstructions

---

## 11. Integration Points with Other Teams

### 11.1 Electronics Team Interface
- **Motor Mounting:** Provide precise mounting points for motors with specified dimensions
- **Sensor Brackets:** Deliver sensor mounting brackets with documented positions and orientations
- **Cable Routing:** Coordinate cable paths and lengths with electronics team
- **Power System:** Ensure battery compartment dimensions match selected battery pack

### 11.2 AI/ML Team Interface
- **Sensor Placement:** Confirm sensor positions align with AI/ML algorithms (e.g., VL53L0X for centering)
- **Camera Field of View:** Ensure camera mounting provides required FOV for visual inspection
- **IMU Orientation:** Document IMU mounting orientation for accurate motion sensing

### 11.3 Dashboard Team Interface
- **Physical Dimensions:** Provide CAD models and dimensions for digital twin visualization
- **Sensor Locations:** Document sensor positions for accurate data overlay on dashboard

---

## 12. Deliverables & Timeline

### 12.1 Phase 1: Design & CAD Modeling (Week 1-2)
**Deliverables:**
- Complete 3D CAD assembly model
- Individual part drawings with dimensions and tolerances
- Bill of Materials (BOM) with cost estimates
- FEA analysis report (stress, weight optimization)
- Design review presentation

### 12.2 Phase 2: Prototyping & Fabrication (Week 3-4)
**Deliverables:**
- 3D-printed chassis components
- Laser-cut acrylic mounting plates
- Machined aluminum frame (if applicable)
- Assembled mechanical subsystem (without electronics)
- Fabrication documentation (assembly instructions)

### 12.3 Phase 3: Testing & Validation (Week 5-6)
**Deliverables:**
- Mechanical testing report (load, traction, durability)
- Dimensional verification report
- Integration test results with electronics
- Identified issues and proposed solutions

### 12.4 Phase 4: Final Integration & Optimization (Week 7-8)
**Deliverables:**
- Fully integrated robot (mechanical + electronics + AI)
- Field testing results (horizontal, vertical, angled pipes)
- Final weight and performance metrics
- Maintenance and assembly manual
- Competition-ready prototype

---

## 13. Risk Assessment & Mitigation

### 13.1 Identified Risks

| Risk | Impact | Probability | Mitigation Strategy |
|------|--------|-------------|---------------------|
| Insufficient traction on smooth pipes | High | Medium | Use high-friction materials (silicone, rubber); increase wall-press force |
| Excessive weight (>3kg) | High | Medium | Conduct weight optimization; use lightweight materials; minimize fasteners |
| Wall-press mechanism failure | High | Low | Conduct durability testing; use safety factor of 1.5x; backup spring design |
| Budget overrun (>₹500) | Medium | Medium | Source cost-effective materials; use 3D printing; reuse available components |
| Inadequate pipe diameter adaptability | Medium | Low | Design telescoping mechanism with wide adjustment range; test across full range |
| Motor mounting misalignment | Medium | Low | Use precise CAD modeling; conduct fit checks during assembly |
| Cable interference with moving parts | Low | Medium | Plan cable routing in CAD; use cable ties and strain relief |

### 13.2 Contingency Plans
- **Backup Locomotion Design:** If caterpillar tracks fail, revert to wheeled differential drive
- **Simplified Wall-Press:** If servo-actuated system is too complex, use spring-loaded passive system
- **Material Substitution:** If aluminum is too expensive, use 3D-printed structural components

---

## 14. Documentation Requirements

### 14.1 Technical Documentation
The following documents must be prepared and maintained:

- **Design Specification Document:** Detailed design rationale, calculations, and decisions
- **CAD Files:** SolidWorks/Fusion 360 files with version control
- **Assembly Instructions:** Step-by-step guide with photos/diagrams
- **Testing Reports:** Results from all mechanical tests with data and analysis
- **Maintenance Manual:** Procedures for disassembly, cleaning, and repairs

### 14.2 Collaboration Documentation
- **Integration Notes:** Coordination points with electronics, AI/ML, and dashboard teams
- **Change Log:** Record of design changes, reasons, and approvals
- **Meeting Minutes:** Notes from team meetings and design reviews

---

## 15. Key Success Criteria

The mechanical subsystem will be considered successful when:

- ✅ Total robot weight is ≤3kg
- ✅ Robot successfully navigates pipes from 75mm to 150mm diameter
- ✅ Vertical climbing is achieved without slippage
- ✅ All sensors and electronics are securely mounted and accessible
- ✅ Mechanical budget is ≤₹500
- ✅ Prototype is completed within 8-week timeline
- ✅ All testing and validation criteria are met
- ✅ Integration with other subsystems is seamless
- ✅ Documentation is complete and comprehensive

---

## 16. References & Resources

### 16.1 Design References
- IEEE papers on pipe inspection robots (see aria-research/topics/)
- Caterpillar traction system research
- Wall-press mechanism designs from literature

### 16.2 CAD & Simulation Tools
- SolidWorks (preferred) or Fusion 360 (free for students)
- FreeCAD (open-source alternative)
- ANSYS or SolidWorks Simulation for FEA

### 16.3 Fabrication Resources
- Local makerspaces for 3D printing and laser cutting
- Online tutorials for aluminum extrusion assembly
- YouTube channels: How To Mechatronics, DroneBot Workshop

### 16.4 Supplier Links
- Robu.in - Electronics and mechanical components
- Amazon India - General hardware and materials
- Local hardware stores - Fasteners, aluminum, acrylic

---

## 17. Contact & Coordination

### 17.1 Team Coordination
- **Weekly Meetings:** Design reviews and progress updates
- **Shared Drive:** CAD files, documentation, and test results
- **Communication Channel:** WhatsApp/Slack for quick coordination

### 17.2 Inter-Team Dependencies
- **Electronics Team:** Motor specifications, sensor mounting requirements
- **AI/ML Team:** Sensor placement, camera FOV requirements
- **Dashboard Team:** Physical dimensions for digital twin

---

**Document Status:** ✅ Ready for Implementation  
**Next Steps:** Begin CAD modeling and design review with team

---

*This document is maintained by the Mechanical Team and updated as the project progresses.*  
*Last Updated: October 21, 2025*
