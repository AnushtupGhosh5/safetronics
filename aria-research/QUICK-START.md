# A.R.I.A. Quick Start Guide

Welcome to the WorkSafeBot research project powered by A.R.I.A. (Autonomous Research & Intelligence Agent).

---

## 🚀 Getting Started

### Current Status
✅ **17 topics created and approved**  
✅ **File structure initialized**  
⏳ **Ready for deep research**

---

## 📋 Available Commands

### Start Research on a Topic
```
/research <topic-id>
```

**Examples:**
```
/research pipe-robot-literature-review
/research budget-microcontroller-selection
/research sensor-datasheet-verification
```

### Check Progress
```
/status
```

### Manage Topics
```
/add-topic <title> [notes]
/edit-topic <id> <new_title> [notes]
/remove-topic <id>
/merge-topics <id1,id2> <new_title>
```

### Export Results
```
/export
```

### Other Commands
```
/pause    - Pause after current step
/resume   - Resume from pause
/reset    - Reset agent state (with confirmation)
```

---

## 📁 File Structure

```
aria-research/
├── index.md                          # Project overview & status
├── QUICK-START.md                    # This file
├── topics/                           # 17 research topic files
│   ├── 01-pipe-robot-literature-review.md
│   ├── 02-budget-microcontroller-selection.md
│   ├── 03-sensor-datasheet-verification.md
│   └── ... (14 more)
├── sources/                          # Source note cards
│   └── README.md
├── evidence/                         # Claim-evidence mapping
│   └── claim-evidence-matrix.md
└── logs/                             # Research audit trail
    ├── research-log.md               # Web interactions
    ├── structure-log.md              # Thinking sessions
    └── self-questions.md             # Q&A log
```

---

## 🎯 Recommended Research Order

### Phase 1: Foundation (Start Here)
1. **pipe-robot-literature-review** - Understand existing designs
2. **sensor-datasheet-verification** - Verify component specs
3. **budget-microcontroller-selection** - Choose compute platform
4. **camera-module-pipe-inspection** - Select vision system

### Phase 2: Mechanical Design
5. **wall-press-mechanism-research**
6. **caterpillar-traction-systems**
7. **modular-chassis-design-75-150mm**

### Phase 3: Electronics
8. **power-system-budget-design**
9. **motor-driver-selection-budget**
10. **complete-bom-cost-optimization**

### Phase 4: Software
11. **mqtt-esp32-implementation**
12. **esp32-firmware-architecture**
13. **dashboard-lightweight-stack**

### Phase 5: Intelligence
14. **tflite-micro-esp32-feasibility**
15. **autonomous-navigation-algorithms**

### Phase 6: Competition
16. **mathematical-modeling-risk-scoring**
17. **competition-abstract-mvp-strategy**

---

## 📊 Research Quality Standards

Each topic research will include:

✅ **20-30 web interactions** (Playwright MCP)  
✅ **20-25 self-clarification questions**  
✅ **15-20 structured thoughts** (Sequential Thinking MCP)  
✅ **15+ citations** with full references  
✅ **Evidence matrix** with confidence levels  
✅ **Risks & mitigations** documented  
✅ **Implementation guidance** (primary + fallback)

---

## 💡 Tips for Effective Research

1. **Start with foundational topics** - They inform later decisions
2. **Review findings regularly** - Check index.md for progress
3. **Adjust thresholds if needed** - Use `/set` command
4. **Cross-reference topics** - Dependencies are documented
5. **Export early and often** - Generate deliverables incrementally

---

## 🔍 What Happens During Research?

When you run `/research <topic-id>`, A.R.I.A. will:

1. **Plan** - Define sub-questions, hypotheses, search strategy
2. **Search** - Use Playwright MCP for extensive web research
3. **Analyze** - Use Sequential Thinking MCP to process findings
4. **Verify** - Vet sources for credibility and reliability
5. **Document** - Create detailed findings with citations
6. **Synthesize** - Generate implementation guidance
7. **STOP** - Await your next command

---

## 📝 Key Project Constraints

- **Budget:** <₹4,200 (~$50 USD)
- **Pipe Diameter:** 75-150mm
- **Orientations:** Horizontal, vertical, angled
- **Runtime:** 30-60 minutes target
- **Weight:** ≤3kg
- **Deadline:** Round 1 (Oct 31), Round 2 (Nov 30), Finals (Dec 22-24)

---

## 🎓 Competition Evaluation Criteria

- **Innovation & Relevance:** 30%
- **Functionality & Robustness:** 25%
- **Mathematical Integration:** 20%
- **Physical AI:** 20%
- **Usability & Scalability:** 5%

---

## 🚨 Important Notes

- **No Raspberry Pi** - Too expensive (₹3,500+)
- **Research-first approach** - Evidence drives decisions
- **Budget-conscious** - Every component must justify cost
- **Safety compliance** - Techfest protocols (ethanol vapor for gas demos)
- **Local operation** - No cloud, MQTT local only

---

## 📞 Need Help?

- Check **index.md** for project overview
- Review **assumptions registry** for validated/unvalidated items
- Check **change log** for project evolution
- Use `/status` to see current progress

---

**Ready to begin? Start with:**
```
/research pipe-robot-literature-review
```

This will kick off comprehensive research on existing pipe inspection robot designs from IEEE papers.

---

**Last Updated:** 2025-10-20  
**Status:** ✅ Ready for Research
