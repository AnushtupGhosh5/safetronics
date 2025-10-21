# Topic 04: Camera Module for Pipe Inspection

**Status:** ✅ COMPLETE  
**Research Date:** 2025-10-20  
**Confidence Level:** HIGH (90%)

---

## Executive Summary

**RECOMMENDATION: Dual-ESP32 Architecture**

**Primary MCU:** ESP32-WROOM-32 (₹343) - sensors + motors + navigation  
**Camera MCU:** ESP32-CAM with OV2640 (₹450-₹650) - camera + image processing  
**Communication:** ESP-NOW (peer-to-peer, no router needed)  
**Total Cost:** ₹893 (~21% of budget)

This architecture solves the GPIO limitation problem identified in Topic 02 while providing integrated camera capability.

---

## Key Findings

### 1. ESP32-CAM Pricing (India, October 2025)

| Retailer | Price (₹) | Notes |
|----------|-----------|-------|
| eBhoot Electronics | ₹450 | Best price |
| Electroboat.in | ₹546 | 4.6★ (172 reviews) |
| robozip.in | ₹580 | 4.7★ (14 reviews) |
| Probots | ₹599 | In stock |
| Engineer Store | ₹620 | Free delivery |
| Robu.in | ₹649 | Trusted retailer |
| Amazon.in | ₹829 | EmbeTronicX brand |

**Average:** ₹550-650  
**Recommended:** ₹450-580 range

### 2. ESP32-CAM Specifications

- **Camera:** OV2640 2MP sensor
- **Resolution:** Up to 1600×1200 (UXGA)
- **WiFi:** 802.11 b/g/n 2.4GHz
- **Bluetooth:** 4.2
- **Processor:** Dual-core ESP32-S 240MHz
- **PSRAM:** 4MB
- **Flash:** 4MB
- **GPIO:** 9-10 usable pins
- **Power:** ~160-260mA active
- **Size:** 27mm × 40.5mm (compact!)

### 3. ESP-NOW Communication Protocol

**Key Features:**
- Peer-to-peer communication (no WiFi router needed)
- Uses MAC addresses for device identification
- Low latency (suitable for real-time robotics)
- Up to 20 peer devices per ESP32
- Range: ~200m line-of-sight, ~50m indoors
- Packet size: Up to 250 bytes
- Encrypted communication supported

**Perfect for WorkSafeBot:**
- ESP32-WROOM sends sensor data to dashboard
- ESP32-CAM sends camera frames to dashboard
- Both communicate via ESP-NOW for coordination
- No WiFi router needed inside pipe!

---

## Architecture Comparison

### Option A: Single ESP32-CAM (REJECTED)
- **Cost:** ₹627 (with programmer)
- **GPIO:** 9-10 pins (TOO LIMITED)
- **Problem:** Can't fit 6 sensors + 4 motors + extras
- **Verdict:** ❌ Insufficient GPIO

### Option B: ESP32-WROOM + External Camera Module
- **Cost:** ₹343 + ₹300-400 = ₹643-743
- **GPIO:** 34 pins (8-10 used by camera = 24-26 free)
- **Problem:** Complex wiring, camera setup difficult
- **Verdict:** ⚠️ Viable but complex

### Option C: Dual-ESP32 Architecture (RECOMMENDED)
- **Cost:** ₹343 + ₹550 = ₹893
- **GPIO:** 34 pins (WROOM) + 9 pins (CAM) = 43 total
- **Benefits:**
  - Separate processing (no resource contention)
  - Modular design (test independently)
  - Fault isolation (camera failure doesn't stop navigation)
  - ESP-NOW communication (low latency)
  - Compact (ESP32-CAM is 27×40mm)
- **Verdict:** ✅ OPTIMAL SOLUTION

---

## Dual-ESP32 Architecture Details

### ESP32-WROOM-32 (Main Controller)
**Responsibilities:**
- Read 6 sensors via I2C (VL53L0X, MPU-6050, BMP180, QMC5883L, DHT22, MQ-7)
- Control 4 motors via PWM
- Run navigation algorithms
- Sensor fusion and decision making
- MQTT communication to dashboard
- ESP-NOW communication with ESP32-CAM

**GPIO Usage:**
- I2C: 2 pins (SDA, SCL)
- Motors: 4 pins (PWM)
- ESP-NOW: Built-in WiFi (no extra pins)
- Extras: 28 pins available

### ESP32-CAM (Vision Module)
**Responsibilities:**
- Capture camera frames (OV2640)
- Basic image processing (if needed)
- Send frames via ESP-NOW or MQTT
- LED control for illumination
- Optional: TFLite Micro for crack detection

**GPIO Usage:**
- Camera: 8-10 pins (internal)
- LED: 1 pin (built-in flash)
- ESP-NOW: Built-in WiFi
- Extras: 8-9 pins available

### Communication Flow
```
ESP32-WROOM ←→ ESP-NOW ←→ ESP32-CAM
      ↓                           ↓
   MQTT Broker ←→ Dashboard ←→ MQTT Broker
```

---

## Implementation Plan

### Phase 1: MVP (Round 1 - Oct 31)
**Option 1: No Camera**
- Use only ESP32-WROOM (₹343)
- Focus on locomotion and sensors
- Defer camera to Phase 2
- **Pros:** Lowest cost, simplest
- **Cons:** May not meet competition requirements

**Option 2: Dual-ESP32 from Start**
- ESP32-WROOM + ESP32-CAM (₹893)
- Full system integration
- **Pros:** Complete solution, impressive demo
- **Cons:** More complex, higher cost

**Recommendation:** Check competition rules first!

### Phase 2: Camera Integration (Round 2 - Nov 30)
1. Purchase ESP32-CAM (₹450-580)
2. Test camera capture and streaming
3. Implement ESP-NOW communication
4. Integrate with main controller
5. Test in pipe environment (low light)

### Phase 3: Optimization (Round 3 - Dec 22-24)
1. Add LED illumination for dark pipes
2. Implement basic image processing
3. Optional: TFLite Micro for crack detection
4. Optimize frame rate and resolution
5. Power optimization

---

## Camera Requirements for Pipe Inspection

### Resolution
- **Minimum:** VGA (640×480) for basic inspection
- **Recommended:** SVGA (800×600) or XGA (1024×768)
- **OV2640 Capability:** Up to UXGA (1600×1200) ✅

### Frame Rate
- **Minimum:** 5 FPS for slow-moving robot
- **Recommended:** 10-15 FPS for smooth video
- **OV2640 Capability:** Up to 30 FPS at lower resolutions ✅

### Low-Light Performance
- **Challenge:** Pipes are dark inside
- **Solution:** ESP32-CAM has built-in flash LED
- **Alternative:** Add external LED strip (₹50-100)
- **OV2640:** Decent low-light performance ✅

### Field of View
- **OV2640:** ~66° diagonal FOV
- **Adequate for:** 75-150mm pipe inspection ✅
- **Alternative:** Wide-angle lens module (160°) available

---

## Budget Impact

### Dual-ESP32 Architecture Cost
| Component | Price (₹) | % of Budget |
|-----------|-----------|-------------|
| ESP32-WROOM-32 | ₹343 | 8.2% |
| ESP32-CAM | ₹550 | 13.1% |
| **Total MCU** | **₹893** | **21.3%** |
| **Remaining** | **₹3,307** | **78.7%** |

**Comparison to Alternatives:**
- vs Single ESP32-CAM: +₹266 (+42%) but solves GPIO problem
- vs ESP32-WROOM + external camera: Similar cost, much easier
- vs ESP32-S3-DevKit: -₹531 savings!

**Verdict:** Excellent value for capability provided

---

## Risks & Mitigation

### Risk 1: ESP-NOW Latency Too High
**Likelihood:** LOW  
**Impact:** MEDIUM  
**Mitigation:** ESP-NOW has <10ms latency (tested in robotics projects). Adequate for our use case.

### Risk 2: Two ESP32s = Double Power Consumption
**Likelihood:** HIGH  
**Impact:** MEDIUM  
**Mitigation:** 
- ESP32-CAM can sleep when not capturing
- Capture frames at 5-10 FPS (not continuous)
- Total: ~400mA (both active) vs ~200mA (single)
- Still within power budget

### Risk 3: Physical Space in 75mm Pipe
**Likelihood:** MEDIUM  
**Impact:** HIGH  
**Mitigation:**
- ESP32-CAM is compact (27×40mm)
- Mount vertically or at angle
- Test fit in 75mm pipe mockup early

### Risk 4: ESP-NOW Setup Complexity
**Likelihood:** LOW  
**Impact:** LOW  
**Mitigation:**
- Well-documented (Random Nerd Tutorials, DroneBot Workshop)
- Arduino library available
- Test communication before integration

---

## Citations

1. **Robu.in** - ESP32-CAM pricing (₹649)
2. **eBhoot Electronics** - ESP32-CAM pricing (₹450)
3. **Random Nerd Tutorials** - "ESP-NOW Two-Way Communication Between ESP32"
4. **DroneBot Workshop** - "ESP NOW - Peer to Peer ESP32 Communications"
5. **Arduino Forum** - "Minimizing Latency in ESP-NOW Communication for Robot Control"
6. **ThinkRobotics.com** - "ESP-NOW Tutorial for Long-Range Communication"
7. **Arduino Docs** - "Device to Device Communication with ESP-NOW"
8. **ResearchGate** - "Real-Time Peer-to-Peer Communication via ESP-NOW"

---

## Recommendations

### Primary Recommendation
**Implement Dual-ESP32 Architecture:**
1. ESP32-WROOM-32 (₹343) for main control
2. ESP32-CAM (₹450-580) for vision
3. ESP-NOW for inter-MCU communication
4. Total cost: ₹893 (21% of budget)

### Alternative (Budget-Constrained)
**Defer Camera to Phase 2:**
1. Start with ESP32-WROOM-32 only (₹343)
2. Add ESP32-CAM for Round 2 if we advance
3. Phased approach reduces initial risk

### NOT Recommended
- Single ESP32-CAM: GPIO too limited
- External camera on WROOM: Complex wiring
- USB webcam: Won't work (no USB host)

---

## Next Steps

1. ✅ Topic 04 complete
2. 📋 **ACTION:** Review competition rules for camera requirements
3. 📋 **ACTION:** Decide: MVP with or without camera?
4. 📋 **ACTION:** If camera needed: Purchase ESP32-CAM (₹450-580)
5. 📋 **ACTION:** Test ESP-NOW communication between two ESP32s
6. ⏳ **NEXT:** Topic 05 - Wall-Press Mechanism Research

---

**Research Completed:** 2025-10-20  
**Web Interactions:** 2  
**Citations:** 8  
**Confidence:** HIGH (90%)  
**Status:** ✅ READY FOR DECISION
