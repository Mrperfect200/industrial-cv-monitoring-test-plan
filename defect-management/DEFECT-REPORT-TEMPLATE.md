# Defect Report Template

## Severity Guide

| Severity | Definition | Examples | SLA |
|---|---|---|---|
| Critical | System unusable or data loss | Auth bypass, event loss, RTSP crash kills all cameras, OOM | Fix before next build |
| High | Major feature broken, no workaround | ZONE_ENTER not firing, RBAC not enforced, wrong occupancy count | Fix within 1 sprint |
| Medium | Feature works with limitation | Queue count off by 1, alert delayed, wrong timestamp format | Fix within 2 sprints |
| Low | Minor UI or cosmetic | Wrong icon, label typo, minor color issue | Fix when capacity allows |

---

## Defect Lifecycle

```
New → Assigned → In Progress → Fixed → Re-Test → Closed
                                            ↓
                                        Re-Opened
```

---

## Defect Report

```
Defect ID:        DEF-XXXX
Title:            [Short description — max 80 chars]
Severity:         Critical / High / Medium / Low
Priority:         P1 / P2 / P3 / P4
Status:           New
Reported By:      [Name]
Reported Date:    YYYY-MM-DD
Assigned To:      [Name]

--- Requirements ---
SRS Requirement:  REQ-XXX-000
Test Case ID:     TC-XXX-000
Test Suite:       TS1 / TS2 / TS3 / TS4 / TS5 / TS6 / TS7

--- Environment ---
Environment:      [Dev / Staging / Production]
Build Version:    [e.g. 1.2.3]
Model Version:    [e.g. yolo-v1.0]
OS:               [e.g. Ubuntu 22.04]
GPU:              [e.g. NVIDIA RTX 4090]
Camera ID:        [e.g. CAM-003 — if applicable]
Area:             [e.g. AREA-A — if applicable]

--- Reproduction ---
Steps to Reproduce:
  1.
  2.
  3.

Expected Result:
[What should happen according to SRS]

Actual Result:
[What actually happened]

Frequency:        Always / Intermittent / Once
Reproducible:     Yes / No

--- Evidence ---
Log Excerpt:
[Paste relevant log lines — remove any credentials]

Screenshot/Video: [Attach or link]

--- Resolution ---
Root Cause:       [To be filled by dev]
Fix Description:  [To be filled by dev]
Fixed In Build:   [Build version]
Re-Test Result:   Pass / Fail
Closed Date:      YYYY-MM-DD
```

---

## Defect ID Convention

```
DEF-[SUITE]-[NUMBER]

Examples:
DEF-FUNC-0001    → Functional defect #1
DEF-CV-0001      → Computer Vision defect #1
DEF-API-0001     → API defect #1
DEF-SEC-0001     → Security defect #1
DEF-PERF-0001    → Performance defect #1
DEF-REL-0001     → Reliability defect #1
DEF-SOAK-0001    → Soak test defect #1
```
