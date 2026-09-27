# Requirements Traceability Matrix (RTM)
**Project:** Industrial Computer Vision Monitoring System  
**SRS Version:** 1.0  
**RTM Version:** 1.0  
**Date:** 2026-09-27  

---

## How to Read This Matrix

| Column | Meaning |
|---|---|
| Req ID | Unique requirement identifier |
| SRS Section | Section number in SRS v1.0 |
| Requirement Summary | One-line description |
| Priority | Critical / High / Medium |
| Test Suite | Which TS covers it |
| Test Case IDs | Specific TC references |
| Status | Not Started / In Progress / Pass / Fail |

---

## RTM Table

| Req ID | SRS § | Requirement Summary | Priority | Test Suite | Test Case IDs | Status |
|---|---|---|---|---|---|---|
| REQ-CAM-001 | 8 | Camera has unique ID, name, IP, RTSP URL, area, status | High | TS1 | TC-CAM-001 to 010 | Not Started |
| REQ-CAM-002 | 9 | RTSP stream open, health check, auto-reconnect | Critical | TS1, TS6 | TC-RTSP-001 to 015 | Not Started |
| REQ-CAM-003 | 10 | Configurable processing FPS (5/10/15/25) | High | TS1 | TC-VID-001 to 005 | Not Started |
| REQ-AI-001 | 11 | Object detection with class, confidence, bbox, timestamp, camera_id | Critical | TS2 | TC-DET-001 to 020 | Not Started |
| REQ-AI-002 | 12 | Confidence threshold configurable per class | High | TS2 | TC-DET-016 to 020 | Not Started |
| REQ-AI-003 | 13 | Object tracking with persistent Track ID | Critical | TS2 | TC-TRK-001 to 010 | Not Started |
| REQ-AI-004 | 14 | ROI limiting inference area | High | TS2 | TC-ROI-001 to 005 | Not Started |
| REQ-AI-005 | 15 | Line crossing detection with direction and event | Critical | TS1, TS2 | TC-LINE-001 to 005 | Not Started |
| REQ-AI-006 | 16 | Zone monitoring (polygon, restricted, production, waiting) | Critical | TS1, TS2 | TC-ZONE-001 to 005, TC-ZONE-CV-001 to 005 | Not Started |
| REQ-BIZ-001 | 17 | Occupancy: current, max, min, avg + threshold event | High | TS1 | TC-OCC-001 to 008 | Not Started |
| REQ-BIZ-002 | 18 | Queue length, count, wait time, threshold | High | TS1 | TC-QUE-001 to 005 | Not Started |
| REQ-BIZ-003 | 19 | Dwell time per track ID in zone + alert on threshold | High | TS1 | TC-DWL-001 to 006 | Not Started |
| REQ-EVT-001 | 20 | Event schema: ID, type, camera, area, zone, object, timestamp, severity | Critical | TS1 | TC-EVT-001 to 015 | Not Started |
| REQ-EVT-002 | 21 | Extensible event types | Medium | TS1 | TC-EVT-016 to 020 | Not Started |
| REQ-ALT-001 | 22 | Alert routing: dashboard, email, webhook | High | TS1 | TC-ALT-001 to 005 | Not Started |
| REQ-API-001 | 23 | All API endpoints functional | Critical | TS3 | TC-API-001 to 045 | Not Started |
| REQ-API-002 | 24 | Auth, pagination, filtering, rate limiting, versioning | High | TS3, TS4 | TC-API-040 to 045 | Not Started |
| REQ-DB-001 | 25 | All tables exist with correct relationships | High | TS1 | TC-DB-001 to 010 | Not Started |
| REQ-DASH-001 | 26 | Dashboard: overview, camera status, live view, events, analytics | High | TS1 | TC-DASH-001 to 009 | Not Started |
| REQ-USR-001 | 27 | RBAC: Admin/Supervisor/Operator/Viewer | Critical | TS1, TS4 | TC-USR-001 to 010 | Not Started |
| REQ-SEC-001 | 28 | HTTPS, password hashing, JWT, RBAC, injection, XSS, CSRF | Critical | TS4 | TC-SEC-001 to 032 | Not Started |
| REQ-NET-001 | 29 | Network segmentation: camera → AI → app → DB | High | TS4 | TC-SEC-017 to 024 | Not Started |
| REQ-DEP-001 | 30 | On-premise deployment supported | High | TS5 | TC-SCL-001 to 007 | Not Started |
| REQ-PERF-001 | 34 | Latency targets (post-PoC) | Critical | TS5 | TC-PERF-001 to 012 | Not Started |
| REQ-REL-001 | 35 | 24/7 uptime, auto restart, camera reconnect | Critical | TS6, TS7 | TC-REL-001 to 014 | Not Started |
| REQ-MON-001 | 36 | Monitoring: camera, RTSP, AI, GPU, CPU, RAM, DB | High | TS1 | TC-MON-001 to 005 | Not Started |
| REQ-LOG-001 | 37 | Structured logs: timestamp, severity, component, camera_id | High | TS1 | TC-LOG-001 to 005 | Not Started |
| REQ-BAK-001 | 38 | Backup: DB, config, zones, users | High | TS1 | TC-BAK-001 to 008 | Not Started |
| REQ-DR-001 | 39 | Disaster recovery: RPO/RTO defined and tested | High | TS6 | TC-REL-010 to 014 | Not Started |
| REQ-SCL-001 | 33 | Scale from 1 to 80 cameras with measured FPS/latency | Critical | TS5 | TC-SCL-001 to 007 | Not Started |
| REQ-SOAK-001 | 35 | 24/7 stability: no leaks, no degradation | Critical | TS7 | Soak Phase 1-3 | Not Started |

---

## Coverage Summary

| Test Suite | Requirements Covered | TCs |
|---|---|---|
| TS1 — Functional | REQ-CAM-001/002/003, REQ-AI-005/006, REQ-BIZ-001/002/003, REQ-EVT-001/002, REQ-ALT-001, REQ-DB-001, REQ-DASH-001, REQ-USR-001, REQ-MON-001, REQ-LOG-001, REQ-BAK-001 | ~100 |
| TS2 — CV & AI | REQ-AI-001/002/003/004/005/006 | ~45 |
| TS3 — API | REQ-API-001/002 | ~50 |
| TS4 — Security | REQ-USR-001, REQ-SEC-001, REQ-NET-001, REQ-API-002 | ~35 |
| TS5 — Performance | REQ-PERF-001, REQ-DEP-001, REQ-SCL-001 | ~25 |
| TS6 — Reliability | REQ-REL-001, REQ-DR-001, REQ-CAM-002 | ~25 |
| TS7 — Soak | REQ-SOAK-001, REQ-REL-001 | 3 phases |

**Total Requirements:** 31  
**Total Test Cases:** ~280+  
**Coverage:** 100% of SRS requirements mapped
