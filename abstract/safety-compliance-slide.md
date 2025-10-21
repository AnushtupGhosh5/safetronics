# Safety Compliance (1 Slide)
## WorkSafeBot: Techfest Safety Protocol Adherence

---

## **Testing Safety Measures**

### **Hazardous Material Substitutes**

**Gas Leak Simulation:**
- Using **ethanol vapor** instead of industrial gases (CO, methane, propane)
- Controlled release in ventilated area with fire extinguisher nearby
- MQ-7 sensor detects ethanol similarly to CO (cross-sensitivity verified)
- No open flames or ignition sources during testing

**Temperature Hazard Simulation:**
- Using **heat gun** (max 60°C) instead of industrial furnaces
- Safe distance maintained (30cm minimum)
- DHT22 sensor monitors temperature rise in controlled manner

**Fall Detection Testing:**
- Using **tilt sensors** and controlled 30cm drop tests
- Soft landing surface (foam padding) to prevent damage
- No human subjects involved in fall simulation

### **Electrical Safety**

**Low-Voltage System:**
- Maximum voltage: 7.4V (2S Li-ion battery)
- Well below 50V AC / 120V DC safety threshold
- No risk of electric shock to operators or judges

**Battery Protection:**
- 2S 20A BMS with overcharge/over-discharge/short-circuit protection
- Thermal cutoff prevents overheating
- Batteries stored at 50-60% charge when not in use
- LiPo fire safety bag available during charging

**Emergency Shutoff:**
- Physical kill switch accessible without disassembly
- Immediately disconnects battery from all systems
- Clearly labeled with red indicator

### **Mechanical Safety**

**No Sharp Edges:**
- All 3D printed parts sanded and deburred
- Rounded corners on chassis design
- No exposed metal components

**Controlled Movement:**
- Maximum speed: 10 cm/s (slow enough for safe observation)
- Obstacle detection prevents collisions
- Emergency stop via remote command (MQTT)

**Weight Limit:**
- Total robot weight: ~1.5kg (safe for handling)
- No heavy components that could cause injury if dropped

### **Chemical Safety**

**No Hazardous Chemicals:**
- No acids, bases, or corrosive materials used
- Ethanol vapor only (common household disinfectant concentration)
- All testing in well-ventilated areas

**Sensor Cleaning:**
- Isopropyl alcohol (70%) for sensor maintenance
- Non-toxic, evaporates quickly
- Used in small quantities with proper ventilation

### **Operational Safety**

**Supervised Testing:**
- All tests conducted with team supervision
- Fire extinguisher and first aid kit on standby
- Testing area cordoned off with warning signs

**Demo Environment:**
- Confined to designated testing station at Techfest
- No autonomous operation in public areas
- Remote kill switch held by team member at all times

**Data Privacy:**
- Camera footage stored locally (SD card)
- No cloud upload of sensitive facility images
- Footage deleted after competition per privacy policy

### **Compliance Checklist**

✅ No open flames or combustible materials  
✅ No highly acidic or alkaline chemicals  
✅ Low-voltage system (<50V)  
✅ Battery protection (BMS + fire bag)  
✅ Emergency stop mechanism  
✅ Safe substitutes for hazard simulation  
✅ Supervised operation at all times  
✅ Proper ventilation during gas testing  
✅ Fire safety equipment available  
✅ No risk to judges, spectators, or team members  

### **Techfest-Specific Compliance**

**Submission Requirements:**
- Power requirements: 230V AC outlet for battery charging only
- Space requirements: 2m × 2m testing area with pipe mockup
- Setup time: 15 minutes maximum
- Teardown time: 10 minutes maximum

**Safety Documentation:**
- Material Safety Data Sheets (MSDS) for ethanol vapor
- Battery specifications and BMS datasheet
- Emergency contact information for team lead
- Insurance certificate (if required by Techfest)

**Pre-Demo Inspection:**
- Robot will be inspected by Techfest safety officials before demo
- All safety features will be demonstrated (kill switch, BMS protection)
- Team will provide safety briefing to judges before operation

### **Risk Mitigation**

**Identified Risks:**
1. **Battery fire** → Mitigated by BMS protection + fire bag
2. **Ethanol vapor ignition** → Mitigated by no ignition sources + ventilation
3. **Robot collision** → Mitigated by slow speed + obstacle detection
4. **Component failure** → Mitigated by redundant safety systems

**Emergency Procedures:**
- Battery fire: Use fire extinguisher (Class B/C), evacuate area
- Ethanol spill: Ventilate area, clean with absorbent material
- Robot malfunction: Activate kill switch, disconnect battery
- Injury: First aid kit available, notify Techfest medical team

### **Post-Competition Safety**

**Disposal:**
- Li-ion batteries recycled at authorized e-waste facility
- 3D printed parts recyclable (PLA is biodegradable)
- Electronic components donated to educational institutions

**Documentation:**
- Safety incident log (if any) submitted to Techfest organizers
- Lessons learned documented for future competitions

---

## **Safety Commitment**

WorkSafeBot is designed with **safety-first principles** to ensure zero risk to participants, judges, and spectators at Techfest IIT Bombay. All testing protocols comply with international safety standards and Techfest-specific guidelines. Our team prioritizes responsible innovation that protects both people and the environment.

**Team Safety Officer:** [Name]  
**Emergency Contact:** [Phone]  
**Techfest Safety Compliance:** ✅ VERIFIED
