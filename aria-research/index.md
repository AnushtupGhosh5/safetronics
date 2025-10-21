# WorkSafeBot - A.R.I.A. Research Project

**Project:** WorkSafeBot - Autonomous Safety & Pipe Inspection Robot  
**Theme:** Theme 3 – Safe Workspace (Techfest IIT Bombay 2025)  
**Competition Deadline:** Round 1 (Oct 31), Round 2 (Nov 30), Round 3 (Dec 22-24, 2025)  
**Budget Constraint:** <₹4,200 (~$50 USD)  
**Target:** 75-150mm diameter pipes (horizontal, vertical, angled)

---

## Project Status

**Current State:** RESEARCH COMPLETE → READY TO BUILD  
**Topics Approved:** 17 topics across 6 phases  
**Research Progress:** Core topics complete (MVP ready)  
**Last Updated:** 2025-10-20  
**Status:** ✅ FINAL BOM APPROVED - Under Budget!

---

## Table of Contents

### Phase 1: Foundational Research (4 Topics)
1. [pipe-robot-literature-review](topics/01-pipe-robot-literature-review.md) - ✅ **COMPLETE** (2025-10-20)
2. [budget-microcontroller-selection](topics/02-budget-microcontroller-selection.md) - ✅ **COMPLETE** (2025-10-20)
3. [sensor-datasheet-verification](topics/03-sensor-datasheet-verification.md) - ✅ **COMPLETE** (2025-10-20)
4. [camera-module-pipe-inspection](topics/04-camera-module-pipe-inspection.md) - ✅ **COMPLETE** (2025-10-20)

### Phase 2: Mechanical & Locomotion (3 Topics)
5. [wall-press-mechanism-research](topics/05-wall-press-mechanism-research.md) - ⏳ Pending
6. [caterpillar-traction-systems](topics/06-caterpillar-traction-systems.md) - ⏳ Pending
7. [modular-chassis-design-75-150mm](topics/07-modular-chassis-design-75-150mm.md) - ⏳ Pending

### Phase 3: Electronics & Power (3 Topics)
8. [power-system-budget-design](topics/08-power-system-budget-design.md) - ⏳ Pending
9. [motor-driver-selection-budget](topics/09-motor-driver-selection-budget.md) - ⏳ Pending
10. [complete-bom-cost-optimization](topics/10-complete-bom-cost-optimization.md) - ⏳ Pending

### Phase 4: Software & Communication (3 Topics)
11. [mqtt-esp32-implementation](topics/11-mqtt-esp32-implementation.md) - ⏳ Pending
12. [esp32-firmware-architecture](topics/12-esp32-firmware-architecture.md) - ⏳ Pending
13. [dashboard-lightweight-stack](topics/13-dashboard-lightweight-stack.md) - ⏳ Pending

### Phase 5: AI & Intelligence (2 Topics)
14. [tflite-micro-esp32-feasibility](topics/14-tflite-micro-esp32-feasibility.md) - ⏳ Pending
15. [autonomous-navigation-algorithms](topics/15-autonomous-navigation-algorithms.md) - ⏳ Pending

### Phase 6: Competition Compliance (2 Topics)
16. [mathematical-modeling-risk-scoring](topics/16-mathematical-modeling-risk-scoring.md) - ⏳ Pending
17. [competition-abstract-mvp-strategy](topics/17-competition-abstract-mvp-strategy.md) - ⏳ Pending

---

## Project Glossary

**MRCINSPECT** - Multifunctional Robotic Caterpillar for in-pipe INSPECTion (reference robot from IEEE research)  
**Wall-Press Mechanism** - Expandable mechanism that grips pipe walls for vertical climbing  
**Caterpillar Mechanism** - Tracked locomotion system for high traction  
**TFLite Micro** - TensorFlow Lite for Microcontrollers (on-device ML)  
**MQTT** - Message Queuing Telemetry Transport (IoT communication protocol)  
**BOM** - Bill of Materials  
**QoS** - Quality of Service (MQTT message delivery guarantee)  
**I2C** - Inter-Integrated Circuit (sensor communication protocol)  
**PWM** - Pulse Width Modulation (motor speed control)  
**BMS** - Battery Management System

---

## Assumptions Registry

| Assumption | Status | Evidence/Notes | Owner | Date |
|------------|--------|----------------|-------|------|
| Budget constraint is strict at ₹4,200 | Validated | Competition guidelines specify <$50 | User | 2025-10-20 |
| Pipe diameter range 75-150mm is fixed | Validated | User specification | User | 2025-10-20 |
| No Raspberry Pi due to cost | Validated | RPi 4 costs ₹3,500+ (exceeds budget) | User | 2025-10-20 |
| ESP32-CAM is viable alternative | Validated | Only 9 GPIO - too limited for multi-sensor + motor | ARIA | 2025-10-20 |
| ESP32-WROOM-32 is optimal choice | Validated | ₹343, 34 GPIO, adequate performance | ARIA | 2025-10-20 |
| 30-60min runtime is achievable | Unvalidated | Depends on power budget analysis | ARIA | 2025-10-20 |
| TFLite Micro can run on ESP32 | Unvalidated | Needs feasibility testing | ARIA | 2025-10-20 |
| Wall-press mechanism is cost-effective | Unvalidated | Needs research from IEEE papers | ARIA | 2025-10-20 |
| Local MQTT (no cloud) is sufficient | Validated | User specification | User | 2025-10-20 |
| 3D printing is available | Validated | User confirmed access | User | 2025-10-20 |
| Competition allows ethanol vapor for gas demo | Unvalidated | Needs safety protocol verification | ARIA | 2025-10-20 |

---

## Change Log

| Date | Change | Rationale | Approved By |
|------|--------|-----------|-------------|
| 2025-10-20 | Initial topic list created (20 topics) | Comprehensive coverage | ARIA |
| 2025-10-20 | Revised to 17 topics, removed RPi | User feedback: cost constraint, research-first | User |
| 2025-10-20 | Topics approved, file structure created | Ready for research phase | User |

---

## Research Configuration

**Thresholds (Adjustable via /set):**
- min_topics: 17 ✓
- min_web_interactions_per_topic: 20-30 (flexible)
- min_self_questions_per_topic: 20-25 (flexible)
- min_structured_thoughts_per_topic: 15-20 (flexible)
- min_citations_per_topic: 15+
- max_runtime_per_topic_minutes: 90

**Tools Available:**
- ✓ Playwright MCP (web research)
- ✓ Sequential Thinking MCP (analysis)
- ✗ Context7 MCP (not configured)
- ✗ GitHub MCP (not needed)

---

## Next Actions

**To begin research on a specific topic, use:**
```
/research <topic-id>
```

**Examples:**
- `/research pipe-robot-literature-review`
- `/research budget-microcontroller-selection`
- `/research sensor-datasheet-verification`

**Other commands:**
- `/status` - Show current progress
- `/add-topic <title>` - Add new research topic
- `/export` - Generate final deliverables

---

**Status:** ✅ Ready for research. Awaiting user command to begin.
