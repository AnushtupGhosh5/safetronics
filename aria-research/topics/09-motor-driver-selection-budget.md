# Topic 09: Motor Driver Selection & Budget

**Topic ID:** 09-motor-driver-selection-budget  
**Status:** ✅ COMPLETE  
**Priority:** CRITICAL  
**Research Date:** 2025-10-20  
**Document Created:** 2025-10-21  
**Researcher:** A.R.I.A. (Autonomous Research & Intelligence Agent)

---

## Executive Summary

This document formalizes the motor driver selection for the WorkSafeBot pipe inspection robot. After evaluating multiple options against budget, current capacity, and feature requirements, the **L298N Dual H-Bridge Motor Driver** was selected at ₹199, paired with **2× N20 6V 100RPM motors with encoders** at ₹1,052 total.

### Key Decision

**Selected:** L298N Motor Driver Module  
**Cost:** ₹199  
**Retailer:** Robu.in  
**Rating:** 4.9★  

**Motors:** 2× N20 6V 100RPM with Encoders  
**Cost:** ₹526 each (₹1,052 total)  
**Retailer:** Robu.in  

**Total Motors & Driver Budget:** ₹1,251 (29.8% of ₹4,200 total budget)

### Why L298N?

1. **Adequate Current:** 2A per channel (motors need <1A each)
2. **Dual Channel:** Perfect for 2-motor differential drive
3. **PWM Support:** Built-in speed control capability
4. **Proven Reliability:** Widely used, 4.9★ rating
5. **Cost-Effective:** ₹199 vs ₹300+ for alternatives
6. **Easy Integration:** Simple 6-pin control interface

### Alternatives Considered

| Driver | Cost | Current/Ch | Pros | Cons | Decision |
|--------|------|------------|------|------|----------|
| **L298N** | **₹199** | **2A** | **Proven, cheap, adequate** | **Lower efficiency** | **✅ SELECTED** |
| TB6612FNG | ₹300+ | 1.2A | Higher efficiency, smaller | More expensive, lower current | ❌ Rejected |
| DRV8833 | ₹250+ | 1.5A | Compact, efficient | More expensive | ❌ Rejected |
| L293D | ₹150 | 600mA | Cheaper | Insufficient current | ❌ Rejected |

---

## Purpose & Scope

### Research Objectives
1. Select motor driver capable of handling N20 motor current requirements
2. Ensure dual-channel capability for differential drive
3. Verify PWM speed control support
4. Stay within ₹200-300 budget allocation
5. Ensure availability from Indian suppliers

### Key Questions Answered
- ✅ What current capacity is needed? **Answer:** 2A per channel (motors draw <1A)
- ✅ How many channels required? **Answer:** 2 channels for 2 motors
- ✅ Is PWM control needed? **Answer:** Yes, for speed control
- ✅ What's the budget? **Answer:** ₹199 (under ₹300 target)
- ✅ Is it available locally? **Answer:** Yes, Robu.in with 4.9★ rating


---

## Findings

### 1. Motor Specifications (N20 6V 100RPM)

**Selected Motors:**
- **Model:** N20 Micro Metal Gear Motor with Encoder
- **Voltage:** 6V nominal
- **Speed:** 100 RPM (geared)
- **Current:** <1A per motor (typical 500-800mA under load)
- **Shaft:** D-shaft for secure wheel mounting
- **Encoder:** Yes (for odometry and position control)
- **Gear Type:** Metal gears (durable)
- **Size:** 12mm diameter (fits in 75mm pipe)
- **Cost:** ₹526 each
- **Quantity:** 2 motors
- **Total Cost:** ₹1,052

**Why N20 Motors?**
1. **Compact Size:** 12mm diameter fits in 75-150mm pipes
2. **Good Torque:** 100 RPM gearing provides climbing power
3. **Encoders Included:** Enable odometry and precise control
4. **Metal Gears:** More durable than plastic for industrial use
5. **D-Shaft:** Secure wheel mounting without slippage
6. **Proven Design:** Widely used in robotics projects

### 2. Motor Driver Requirements Analysis

**Current Requirements:**
- **Per Motor:** 500-800mA typical, up to 1A peak
- **Both Motors:** 1-2A combined
- **Safety Margin:** Need 2A+ per channel for reliability
- **Conclusion:** Driver must support 2A continuous per channel

**Control Requirements:**
- **Direction Control:** Forward/reverse for each motor
- **Speed Control:** PWM for variable speed (0-100%)
- **Channels:** 2 independent channels (differential drive)
- **Logic Level:** 3.3V compatible (ESP32 GPIO)

**Physical Requirements:**
- **Size:** Compact enough for robot chassis
- **Mounting:** Standard PCB with mounting holes
- **Connectors:** Screw terminals for motor wires
- **Heat Dissipation:** Adequate for continuous operation

### 3. L298N Motor Driver Specifications

**Technical Specifications:**
- **Chip:** L298N Dual H-Bridge
- **Channels:** 2 independent channels
- **Current:** 2A continuous per channel, 3A peak
- **Voltage Range:** 5-35V input
- **Logic Voltage:** 5V (compatible with 3.3V via level shifter or direct)
- **PWM Frequency:** Up to 40kHz
- **Protection:** Flyback diodes included
- **Size:** 43mm × 43mm × 27mm
- **Weight:** ~30g

**Pin Configuration:**
- **Motor A:** OUT1, OUT2
- **Motor B:** OUT3, OUT4
- **Control:** IN1, IN2, IN3, IN4 (direction)
- **PWM:** ENA, ENB (speed control)
- **Power:** VCC (motor voltage), GND, 5V output

**Features:**
- Built-in 5V regulator (can power logic)
- LED indicators for each channel
- Screw terminals for easy wiring
- Mounting holes for chassis integration
- Flyback diodes for motor protection

**Efficiency:**
- **Typical:** 70-80% (lower than modern drivers)
- **Heat Generation:** Moderate (may need heatsink for continuous use)
- **Voltage Drop:** ~2V across H-bridge
- **Note:** Lower efficiency acceptable given budget constraints

### 4. Integration with ESP32-WROOM

**GPIO Requirements:**
- **Motor A Direction:** 2 GPIO (IN1, IN2)
- **Motor B Direction:** 2 GPIO (IN3, IN4)
- **Motor A Speed:** 1 GPIO PWM (ENA)
- **Motor B Speed:** 1 GPIO PWM (ENB)
- **Total:** 6 GPIO pins

**ESP32-WROOM GPIO Allocation:**
- GPIO 25: Motor A IN1 (direction)
- GPIO 26: Motor A IN2 (direction)
- GPIO 27: Motor A ENA (PWM speed)
- GPIO 14: Motor B IN3 (direction)
- GPIO 12: Motor B IN4 (direction)
- GPIO 13: Motor B ENB (PWM speed)

**Control Logic:**
```
Forward:  IN1=HIGH, IN2=LOW,  ENA=PWM
Reverse:  IN1=LOW,  IN2=HIGH, ENA=PWM
Brake:    IN1=HIGH, IN2=HIGH, ENA=LOW
Coast:    IN1=LOW,  IN2=LOW,  ENA=LOW
```

**Power Connection:**
- **Motor Voltage (VCC):** 7.4V from 2S 18650 battery
- **Logic Power:** 5V from L298N onboard regulator or ESP32
- **Ground:** Common ground between ESP32 and L298N


### 5. Alternative Drivers Evaluated

#### TB6612FNG Dual Motor Driver
**Specifications:**
- Current: 1.2A continuous, 3.2A peak per channel
- Voltage: 4.5-13.5V
- Efficiency: 90%+ (much better than L298N)
- Size: Smaller footprint
- Cost: ₹300-400

**Pros:**
- Higher efficiency (less heat, longer battery life)
- Smaller and lighter
- Better for battery-powered applications

**Cons:**
- More expensive (₹300+ vs ₹199)
- Lower continuous current (1.2A vs 2A)
- Less common in India (availability concerns)

**Decision:** ❌ Rejected due to higher cost and lower current capacity

#### DRV8833 Dual Motor Driver
**Specifications:**
- Current: 1.5A continuous, 2A peak per channel
- Voltage: 2.7-10.8V
- Efficiency: 85-90%
- Size: Very compact
- Cost: ₹250-350

**Pros:**
- Good efficiency
- Compact size
- Adequate current

**Cons:**
- More expensive than L298N
- Voltage range doesn't fully cover 7.4V battery
- Less common availability

**Decision:** ❌ Rejected due to cost and voltage range concerns

#### L293D Quadruple Half-H Driver
**Specifications:**
- Current: 600mA continuous, 1.2A peak per channel
- Voltage: 4.5-36V
- Efficiency: 60-70%
- Cost: ₹150-180

**Pros:**
- Cheaper than L298N
- Widely available
- Simple to use

**Cons:**
- Insufficient current (600mA < 1A motor requirement)
- Lower efficiency
- Would need parallel channels for adequate current

**Decision:** ❌ Rejected due to insufficient current capacity

### 6. Cost-Benefit Analysis

**L298N Selection Justification:**

| Factor | Weight | L298N Score | TB6612FNG Score | DRV8833 Score | L293D Score |
|--------|--------|-------------|-----------------|---------------|-------------|
| Current Capacity | 30% | 10/10 | 6/10 | 8/10 | 3/10 |
| Cost | 25% | 10/10 | 5/10 | 7/10 | 10/10 |
| Availability | 20% | 10/10 | 6/10 | 7/10 | 9/10 |
| Efficiency | 15% | 5/10 | 10/10 | 9/10 | 4/10 |
| Ease of Use | 10% | 9/10 | 8/10 | 8/10 | 9/10 |
| **Weighted Total** | | **8.65** | **6.65** | **7.60** | **6.25** |

**Winner:** L298N with highest weighted score of 8.65/10

**Key Decision Factors:**
1. **Current Capacity (30%):** L298N's 2A per channel provides safety margin
2. **Cost (25%):** ₹199 is excellent value, ₹100+ cheaper than alternatives
3. **Availability (20%):** Readily available from Robu.in with good ratings
4. **Proven Reliability:** 4.9★ rating, widely used in robotics community

**Trade-off Accepted:**
- Lower efficiency (70-80% vs 85-90%) is acceptable given:
  - Budget constraints (₹100+ savings)
  - Adequate battery capacity (2500-3500mAh)
  - Intermittent motor operation (not continuous)
  - Can add heatsink if needed (₹20-30)


---

## Implementation Guidance

### 1. Wiring Diagram

```
ESP32-WROOM-32          L298N Motor Driver          N20 Motors
-----------------       ------------------          -----------
GPIO 25 ------------>   IN1 (Motor A Dir)
GPIO 26 ------------>   IN2 (Motor A Dir)
GPIO 27 (PWM) ------>   ENA (Motor A Speed)
                        OUT1 ------------------>    Motor A (+)
                        OUT2 ------------------>    Motor A (-)

GPIO 14 ------------>   IN3 (Motor B Dir)
GPIO 12 ------------>   IN4 (Motor B Dir)
GPIO 13 (PWM) ------>   ENB (Motor B Speed)
                        OUT3 ------------------>    Motor B (+)
                        OUT4 ------------------>    Motor B (-)

GND --------------->    GND
                        VCC <------------------>    7.4V Battery (+)
                        GND <------------------>    Battery (-)
```

### 2. Power Considerations

**Voltage Supply:**
- **Motor Voltage (VCC):** 7.4V from 2S 18650 battery
- **Logic Voltage:** 5V from L298N onboard regulator OR separate 5V supply
- **ESP32 Power:** 3.3V from separate regulator (not from L298N)

**Current Draw:**
- **Both Motors Running:** 1-2A from battery
- **L298N Quiescent:** ~50mA
- **Total Peak:** ~2.1A

**Battery Impact:**
- **Continuous Operation:** 2500mAh / 2100mA = 70 minutes
- **Intermittent (40% duty):** 2500mAh / 1150mA = 130 minutes
- **Conclusion:** Adequate for 30-60 minute requirement ✅

### 3. Thermal Management

**Heat Generation:**
- L298N generates heat due to ~70-80% efficiency
- Voltage drop: ~2V across H-bridge
- Power dissipation: 2V × 1A = 2W per motor (4W total)

**Cooling Strategy:**
- **Passive:** L298N has built-in heatsink
- **Active (if needed):** Add small heatsink (₹20-30)
- **Airflow:** Ensure ventilation in chassis design
- **Monitoring:** Check temperature during testing

**Temperature Limits:**
- **Operating:** -25°C to +130°C
- **Safe Continuous:** <80°C recommended
- **Action:** Add heatsink if >70°C during testing

### 4. Software Control (Arduino/ESP32)

**Basic Motor Control Code:**
```cpp
// PWM settings
#define PWM_FREQ 1000  // 1kHz
#define PWM_RESOLUTION 8  // 8-bit (0-255)

// Motor A pins
#define MOTOR_A_IN1 25
#define MOTOR_A_IN2 26
#define MOTOR_A_ENA 27

// Motor B pins
#define MOTOR_B_IN3 14
#define MOTOR_B_IN4 12
#define MOTOR_B_ENB 13

void setup() {
  // Configure motor pins
  pinMode(MOTOR_A_IN1, OUTPUT);
  pinMode(MOTOR_A_IN2, OUTPUT);
  pinMode(MOTOR_B_IN3, OUTPUT);
  pinMode(MOTOR_B_IN4, OUTPUT);
  
  // Configure PWM channels
  ledcSetup(0, PWM_FREQ, PWM_RESOLUTION);  // Motor A
  ledcSetup(1, PWM_FREQ, PWM_RESOLUTION);  // Motor B
  ledcAttachPin(MOTOR_A_ENA, 0);
  ledcAttachPin(MOTOR_B_ENB, 1);
}

void motorA_forward(int speed) {  // 0-255
  digitalWrite(MOTOR_A_IN1, HIGH);
  digitalWrite(MOTOR_A_IN2, LOW);
  ledcWrite(0, speed);
}

void motorA_reverse(int speed) {
  digitalWrite(MOTOR_A_IN1, LOW);
  digitalWrite(MOTOR_A_IN2, HIGH);
  ledcWrite(0, speed);
}

void motor_stop() {
  digitalWrite(MOTOR_A_IN1, LOW);
  digitalWrite(MOTOR_A_IN2, LOW);
  ledcWrite(0, 0);
  digitalWrite(MOTOR_B_IN3, LOW);
  digitalWrite(MOTOR_B_IN4, LOW);
  ledcWrite(1, 0);
}

// Similar functions for Motor B
```

### 5. Testing Procedures

**Phase 1: Bench Testing (No Load)**
1. Connect L298N to power supply (7.4V)
2. Connect ESP32 control pins
3. Test forward/reverse for each motor
4. Test PWM speed control (0-255)
5. Verify direction control logic
6. Check for motor overheating (should be minimal)

**Phase 2: Load Testing**
1. Mount motors on chassis with wheels
2. Test on flat surface
3. Measure current draw (should be <1A per motor)
4. Test climbing on incline
5. Monitor temperature (should be <70°C)
6. Verify encoder signals

**Phase 3: Integration Testing**
1. Test with full robot weight
2. Test in pipe mockup (75-150mm)
3. Test wall-press mechanism with motors
4. Verify battery runtime (target: 60+ minutes)
5. Test emergency stop functionality 


---

## Conclusion

The L298N motor driver at ₹199 from robu.in provides the optimal balance of cost, performance, and reliability for the WorkSafeBot project. Combined with 2× N20 6V 100RPM motors with encoders at ₹526 each (₹1,052 total), the complete motor system costs ₹1,251, representing 29.8% of the ₹4,200 total budget.

### Key Advantages of Selected Solution:
1. **Adequate Current Capacity**: 2A per channel handles motor requirements with safety margin
2. **Cost-Effective**: ₹199 is ₹100+ cheaper than alternatives while meeting all requirements
3. **Proven Reliability**: 4.88★ rating on robu.in with positive user feedback
4. **Easy Integration**: Simple 6-pin control interface with ESP32
5. **Local Availability**: In stock at robu.in with fast delivery

### Trade-offs Accepted:
- Lower efficiency (70-80%) vs alternatives (85-90%)
- Slightly larger size vs modern drivers
- Higher heat generation (manageable with passive cooling)

### Next Steps:
1. Order L298N motor driver from robu.in (SKU: 51971)
2. Order 2× N20 6V 100RPM motors with encoders (SKU: 476645)
3. Proceed with power system design (Topic 08)
4. Begin chassis design incorporating motor mounting
5. Prepare for bench testing upon component arrival

**Document Status:** ✅ COMPLETE  
**Pricing Verified:** 2025-10-21 (robu.in)  
**Ready for Implementation:** YES
