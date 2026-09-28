# Industrial Computer Vision Monitoring System — Test Plan

> QA documentation for an Industrial Computer Vision platform monitoring up to 80 factory cameras 24/7.

## Repository Structure
|
```
├── docs/
│   └── requirements/          # SRS and supporting requirements docs
├── test-plan/                 # Master Test Plan document
├── test-suites/
│   ├── 01-functional/         # Camera, RTSP, zones, events, dashboard, RBAC
│   ├── 02-computer-vision-ai/ # Detection accuracy, tracking, ROI, zone logic
│   ├── 03-api/                # All REST API endpoints
│   ├── 04-security/           # AuthN, AuthZ, injection, secrets, TLS
│   ├── 05-performance-load/   # Scale 1→80 cameras, stress, concurrent events
│   ├── 06-reliability-failover/ # Camera/service/DB/power failure recovery
│   └── 07-soak/               # 8h / 24h / 72h stability testing
├── TEST_CASES/                # Corporate formatted test case files (one per TC ID)
│   ├── TS1-Functional/        # ICVMS-08.md … ICVMS-47.md
│   ├── TS2-Computer-Vision-AI/ # ICVMS-48.md … ICVMS-70.md
│   ├── TS3-API/               # ICVMS-71.md … ICVMS-90.md
│   ├── TS4-Security/          # ICVMS-91.md … ICVMS-110.md
│   ├── TS5-Performance-Load/  # ICVMS-111.md … ICVMS-125.md
│   ├── TS6-Reliability-Failover/ # ICVMS-126.md … ICVMS-137.md
│   └── TS7-Soak/              # ICVMS-138.md … ICVMS-142.md
├── rtm/                       # Requirements Traceability Matrix
├── acceptance-criteria/       # Production Readiness Checklist
├── defect-management/         # Defect report template + severity guide
├── checklists/                # Quick-reference checklists
└── reports/
    └── templates/             # Test execution report templates
```
## Test Strategy — 5 Layers

| Layer | Focus | Mandatory |
|---|---|---|
| 1 — Model | Detection accuracy, tracking metrics | ✅ |
| 2 — Functional | Every SRS requirement | ✅ |
| 3 — Integration | Camera → AI → Backend → DB → Dashboard | ✅ |
| 4 — Performance & Security | Load 1→80 cameras, security controls | ✅ |
| 5 — Production Validation | 72h soak, acceptance sign-off | ✅ |

## Test Suites Summary

| Suite | Test Cases | Priority |
|---|---|---|
| TS1 — Functional | ~100 TCs | Critical/High |
| TS2 — Computer Vision & AI | ~45 TCs | Critical/High |
| TS3 — API | ~50 TCs | Critical/High |
| TS4 — Security | ~35 TCs | Critical |
| TS5 — Performance & Load | ~25 TCs | High |
| TS6 — Reliability & Failover | ~25 TCs | Critical |
| TS7 — Soak | 3 phases (8h/24h/72h) | Critical |

## Key Decisions

- Performance thresholds (latency, FPS targets) are **TBD after PoC** — never invented upfront.
- All test cases are mapped to SRS requirements via the RTM.
- Production Readiness requires **all Critical items checked** before go-live.

## System Under Test

| Component | Technology |
|---|---|
| Stream Ingestion | RTSP, H.264/H.265 |
| AI Inference | PyTorch / ONNX / TensorRT (post-PoC decision) |
| Object Tracking | ByteTrack / BoT-SORT (post-PoC decision) |
| Backend | REST API with JWT auth |
| Database | TBD |
| Dashboard | Web UI |
| Deployment | On-Premise / Edge Server |
| Camera Scale | Up to 80 cameras |
| Availability | 24/7 |

## Documents

| Document | Path |
|---|---|
| SRS | `docs/requirements/SRS-v1.0.md` |
| Master Test Plan | `test-plan/TEST-PLAN-v1.0.md` |
| RTM | `rtm/RTM-v1.0.md` |
| Production Readiness Checklist | `acceptance-criteria/PRODUCTION-READINESS-CHECKLIST.md` |
| Defect Report Template | `defect-management/DEFECT-REPORT-TEMPLATE.md` |

## Status

| Phase | Status |
|---|---|
| SRS | ✅ Complete |
| Test Plan | ✅ Complete |
| RTM | ✅ Complete |
| Test Execution | ⏳ Pending PoC |
| PoC Benchmark | ⏳ Pending hardware |
| Production Sign-off | ⏳ Pending |
