# Test Plan — Industrial Computer Vision Monitoring System
**Document Version:** 1.0  
**SRS Reference:** Industrial Computer Vision Monitoring System SRS v1.0  
**Prepared By:** QA Engineering  
**Date:** 2026-09-28  
**Environment:** On-Premise / Factory  
**Classification:** Internal

---

## Table of Contents

1. Document Information
2. Scope & Objectives
3. Test Strategy
4. Requirements Traceability Matrix (RTM)
5. Test Suite 1 — Functional Testing
6. Test Suite 2 — Computer Vision & AI Testing
7. Test Suite 3 — API Testing
8. Test Suite 4 — Security Testing
9. Test Suite 5 — Performance & Load Testing
10. Test Suite 6 — Reliability & Failover Testing
11. Test Suite 7 — Soak Testing
12. Acceptance Criteria & Production Readiness Checklist
13. Entry & Exit Criteria
14. Defect Management
15. Risks & Mitigations

---

## 1. Document Information

| Field | Value |
|---|---|
| Project | Industrial Computer Vision Monitoring System |
| Test Plan Version | 1.0 |
| SRS Version | 1.0 |
| Environment | On-Premise / Factory |
| Camera Scale | Up to 80 cameras |
| Availability Target | 24/7 |
| Architecture | Edge AI + Backend + Database + Web Dashboard |
| Test Plan Author | QA Engineering |
| Review Date | TBD after PoC |

---

## 2. Scope & Objectives

### 2.1 In Scope

| Domain | What We Test |
|---|---|
| Video / RTSP | Stream connection, reconnection, health monitoring, FPS, frame dropping |
| AI / Inference | Detection accuracy, tracking, ROI, line crossing, zone logic |
| Business Logic | Entry/Exit, Occupancy, Queue, Dwell Time, Event generation |
| Backend API | All endpoints: Auth, Cameras, Events, Areas, Zones, Users |
| Dashboard | Live view, camera status, events, analytics, reports |
| Security | AuthN, AuthZ, RBAC, injection, secrets, TLS |
| Performance | FPS, latency, GPU/CPU/RAM under 1→80 camera load |
| Reliability | Camera disconnect, service crash, DB unavailable, power restart |
| Soak | 24h / 72h continuous operation stability |

### 2.2 Out of Scope

- Manufacturing ERP integration
- PLC / machine control
- Physical camera installation
- Facial recognition / biometric identification
- Full video archival system
- Building access-control system

### 2.3 Test Objectives

1. Verify every functional requirement in the SRS produces the correct system behavior.
2. Validate AI detection and tracking accuracy against defined acceptance criteria.
3. Confirm the system handles RTSP failures gracefully and recovers automatically.
4. Verify the API is secure, correct, and performs within latency targets.
5. Validate security controls: RBAC, authentication, injection protection, secrets.
6. Stress the system from 1 to 80+ cameras and measure degradation.
7. Confirm 24/7 stability with no memory leaks, VRAM leaks, or growing queues.
8. Produce a signed Production Readiness Checklist before go-live.

---

## 3. Test Strategy

The system is tested in five mandatory layers. Every layer must pass before Production Readiness is declared.

```
Layer 1 — Model Testing
Layer 2 — Functional Testing
Layer 3 — Integration Testing
Layer 4 — Performance & Reliability Testing
Layer 5 — Production Validation (Soak + Acceptance)
```

### 3.1 Layer Definitions

| Layer | Focus | When |
|---|---|---|
| 1 — Model | Detection accuracy, tracking, edge cases | After every model version |
| 2 — Functional | Every SRS requirement | After each feature sprint |
| 3 — Integration | Camera → AI → Backend → DB → Dashboard | After module integration |
| 4 — Performance / Security | Load, stress, failover, security | Before UAT |
| 5 — Production Validation | Soak test, acceptance criteria, sign-off | Before go-live |

### 3.2 Test Types Summary

| Type | Tool / Method |
|---|---|
| Functional | Manual + automated scripts |
| API Testing | Postman / pytest + requests |
| CV / AI Testing | Labeled test dataset + custom eval script |
| Security Testing | Manual review + OWASP checklist + Burp Suite |
| Load / Performance | k6 / Locust + GPU/CPU monitoring |
| Reliability / Failover | Manual fault injection |
| Soak | Automated monitoring over 24h–72h |

---

## 4. Requirements Traceability Matrix (RTM)

Every test case is mapped to one SRS requirement.

| Req ID | SRS Section | Requirement Summary | Test Suite | Test Case IDs |
|---|---|---|---|---|
| REQ-CAM-001 | §8 | Camera has unique ID, name, IP, RTSP URL, area, status | TS1-Functional | TC-CAM-001 to 010 |
| REQ-CAM-002 | §9 | RTSP stream open, health check, auto-reconnect | TS1-Functional, TS6-Reliability | TC-RTSP-001 to 015 |
| REQ-CAM-003 | §10 | Configurable processing FPS (5/10/15/25) | TS1-Functional | TC-VID-001 to 005 |
| REQ-AI-001 | §11 | Object detection with class, confidence, bbox, timestamp, camera_id | TS2-CV | TC-DET-001 to 020 |
| REQ-AI-002 | §12 | Confidence threshold configurable per class | TS2-CV | TC-DET-021 to 025 |
| REQ-AI-003 | §13 | Object tracking with persistent Track ID | TS2-CV | TC-TRK-001 to 015 |
| REQ-AI-004 | §14 | ROI limiting inference area | TS2-CV | TC-ROI-001 to 008 |
| REQ-AI-005 | §15 | Line crossing detection with direction and event | TS1-Functional, TS2-CV | TC-LINE-001 to 010 |
| REQ-AI-006 | §16 | Zone monitoring (polygon, restricted, production, waiting) | TS1-Functional, TS2-CV | TC-ZONE-001 to 012 |
| REQ-BIZ-001 | §17 | Occupancy: current, max, min, avg + threshold event | TS1-Functional | TC-OCC-001 to 008 |
| REQ-BIZ-002 | §18 | Queue length, count, wait time, threshold | TS1-Functional | TC-QUE-001 to 008 |
| REQ-BIZ-003 | §19 | Dwell time per track ID in zone + alert on threshold | TS1-Functional | TC-DWL-001 to 008 |
| REQ-EVT-001 | §20 | Event schema: ID, type, camera, area, zone, object, timestamp, severity | TS1-Functional | TC-EVT-001 to 015 |
| REQ-EVT-002 | §21 | Extensible event types | TS1-Functional | TC-EVT-016 to 020 |
| REQ-ALT-001 | §22 | Alert routing: dashboard, email, webhook | TS1-Functional | TC-ALT-001 to 010 |
| REQ-API-001 | §23 | All API endpoints functional | TS3-API | TC-API-001 to 060 |
| REQ-API-002 | §24 | Auth, pagination, filtering, rate limiting, versioning | TS3-API, TS4-Security | TC-API-061 to 080 |
| REQ-DB-001 | §25 | All tables exist with correct relationships | TS1-Functional | TC-DB-001 to 010 |
| REQ-DASH-001 | §26 | Dashboard: overview, camera status, live view, events, analytics | TS1-Functional | TC-DASH-001 to 015 |
| REQ-USR-001 | §27 | RBAC: Admin/Supervisor/Operator/Viewer | TS1-Functional, TS4-Security | TC-USR-001 to 020 |
| REQ-SEC-001 | §28 | HTTPS, password hashing, JWT, RBAC, input validation, injection protection | TS4-Security | TC-SEC-001 to 040 |
| REQ-PERF-001 | §34 | Latency targets (post-PoC) | TS5-Performance | TC-PERF-001 to 020 |
| REQ-REL-001 | §35–36 | 24/7 uptime, auto restart, camera reconnect | TS6-Reliability, TS7-Soak | TC-REL-001 to 025 |
| REQ-MON-001 | §36 | Monitoring: camera, RTSP, AI, GPU, CPU, RAM, DB | TS1-Functional | TC-MON-001 to 015 |
| REQ-LOG-001 | §37 | Structured logs with timestamp, severity, component, camera_id | TS1-Functional | TC-LOG-001 to 010 |
| REQ-BAK-001 | §38 | Backup: DB, config, zones, users | TS1-Functional | TC-BAK-001 to 008 |
| REQ-SCL-001 | §33 | Scale from 1 to 80 cameras with measured FPS/latency | TS5-Performance | TC-SCL-001 to 010 |

---

## 5. Test Suite 1 — Functional Testing

### TS1.1 — Camera Management

| TC ID | Test Case | Steps | Expected Result | Priority |
|---|---|---|---|---|
| TC-CAM-001 | Add new camera with all required fields | POST camera with valid payload | Camera saved, returns 201, camera_id assigned | High |
| TC-CAM-002 | Add camera with duplicate camera_id | POST with existing ID | Returns 409 Conflict | High |
| TC-CAM-003 | Add camera with missing required fields | POST without RTSP URL | Returns 400 with field-level errors | High |
| TC-CAM-004 | Update camera configuration | PUT /cameras/{id} with new resolution | Camera updated, returns 200 | Medium |
| TC-CAM-005 | Delete camera | DELETE /cameras/{id} | Camera removed, associated stream stopped | High |
| TC-CAM-006 | Get camera list | GET /cameras | Returns all cameras with correct schema | High |
| TC-CAM-007 | Camera assigned to Area | POST camera with area_id | Camera listed under correct area | High |
| TC-CAM-008 | Camera status reflects ONLINE/OFFLINE | Connect camera → check status | Status = ONLINE; disconnect → OFFLINE | High |
| TC-CAM-009 | Camera with invalid RTSP URL | POST with invalid URL format | Returns 400 validation error | Medium |
| TC-CAM-010 | Camera credentials not returned in API response | GET /cameras/{id} | RTSP credentials absent from response body | High |

### TS1.2 — RTSP Stream

| TC ID | Test Case | Steps | Expected Result | Priority |
|---|---|---|---|---|
| TC-RTSP-001 | Connect to valid RTSP stream | Configure camera with live RTSP URL | Stream opens, FPS reported | High |
| TC-RTSP-002 | Connect to unreachable RTSP URL | Configure camera with unreachable host | System logs error, status = OFFLINE | High |
| TC-RTSP-003 | Auto-reconnect after disconnect | Disconnect camera → wait → reconnect | System retries, reconnects, resumes processing | Critical |
| TC-RTSP-004 | Reconnect uses exponential backoff | Disconnect → observe retry timing | Retry intervals increase progressively | High |
| TC-RTSP-005 | One camera disconnect does not affect others | Disconnect CAM-001 while CAM-002 is active | CAM-002 continues unaffected | Critical |
| TC-RTSP-006 | Frozen stream detection | Feed static frame for >30s | System detects frozen stream, logs event | High |
| TC-RTSP-007 | FPS monitoring reported correctly | Stream at 25 FPS | System reports FPS within ±2 FPS | Medium |
| TC-RTSP-008 | Dropped frames logged | Introduce packet loss | Dropped frames logged with camera_id and timestamp | Medium |
| TC-RTSP-009 | Stream failure generates STREAM_ERROR event | Kill RTSP source | STREAM_ERROR event created with correct camera_id | High |
| TC-RTSP-010 | RTSP credentials not logged | Connect camera with credentials | Credentials absent from all log entries | Critical |
| TC-RTSP-011 | H.264 codec supported | Stream H.264 camera | Decoded successfully | High |
| TC-RTSP-012 | H.265 codec supported | Stream H.265 camera | Decoded successfully | High |
| TC-RTSP-013 | Camera reconnect event logged | Disconnect then reconnect | Log entry with reconnect timestamp and camera_id | Medium |
| TC-RTSP-014 | Stream latency monitored | Check latency metric | Latency value reported per camera | Medium |
| TC-RTSP-015 | CAMERA_OFFLINE event generated | Take camera offline | CAMERA_OFFLINE event in event log | High |

### TS1.3 — Video Processing

| TC ID | Test Case | Steps | Expected Result | Priority |
|---|---|---|---|---|
| TC-VID-001 | Processing FPS = 5 | Set processing_fps = 5 | System processes ~5 frames/sec | High |
| TC-VID-002 | Processing FPS = 10 | Set processing_fps = 10 | System processes ~10 frames/sec | High |
| TC-VID-003 | Processing FPS = 25 | Set processing_fps = 25 | System processes ~25 frames/sec | High |
| TC-VID-004 | Processing FPS change takes effect without restart | Update config via API | New FPS applied within 5 seconds | Medium |
| TC-VID-005 | Frame skipping reduces GPU load | Compare GPU at 5 FPS vs 25 FPS | GPU utilization lower at 5 FPS | High |

### TS1.4 — Zone & Line Management

| TC ID | Test Case | Steps | Expected Result | Priority |
|---|---|---|---|---|
| TC-ZONE-001 | Create polygon zone on camera | POST zone with polygon coordinates | Zone saved and associated with camera | High |
| TC-ZONE-002 | Create restricted zone | POST zone with type = RESTRICTED | Zone marked as restricted | High |
| TC-ZONE-003 | Zone persists after system restart | Create zone → restart service | Zone still active | High |
| TC-ZONE-004 | Delete zone | DELETE /zones/{id} | Zone removed, no more events from it | High |
| TC-ZONE-005 | Update zone polygon | PUT /zones/{id} with new coordinates | New polygon applied | Medium |
| TC-LINE-001 | Create virtual line | POST line with start/end coordinates | Line saved on camera | High |
| TC-LINE-002 | Line crossing generates event | Object crosses line | LINE_CROSSED event with direction, track_id, timestamp | Critical |
| TC-LINE-003 | Direction detected correctly (Entry) | Object crosses line top→bottom | Direction = ENTRY in event | High |
| TC-LINE-004 | Direction detected correctly (Exit) | Object crosses line bottom→top | Direction = EXIT in event | High |
| TC-LINE-005 | Line crossing event includes camera_id and line_id | Cross line on CAM-003 | Event.camera_id = CAM-003, event.line_id correct | High |

### TS1.5 — Business Logic: Occupancy

| TC ID | Test Case | Steps | Expected Result | Priority |
|---|---|---|---|---|
| TC-OCC-001 | Current occupancy increments on ZONE_ENTER | Person enters zone | Occupancy +1 | High |
| TC-OCC-002 | Current occupancy decrements on ZONE_EXIT | Person exits zone | Occupancy -1 | High |
| TC-OCC-003 | Occupancy does not go below 0 | All people exit zone | Occupancy = 0, no negative value | High |
| TC-OCC-004 | OVER_OCCUPANCY event fires when threshold exceeded | Occupancy > threshold | OVER_OCCUPANCY event generated | Critical |
| TC-OCC-005 | OVER_OCCUPANCY event not duplicated per second | Stay over threshold | Event fires once, not repeatedly per frame | High |
| TC-OCC-006 | Max occupancy tracked correctly | Peak of 17 people → drops to 5 | Max = 17 retained | Medium |
| TC-OCC-007 | Average occupancy calculated | 10 readings over time | Average = sum/count correctly | Medium |
| TC-OCC-008 | Occupancy threshold configurable via API | PUT zone with threshold = 20 | Event fires at 21, not before | High |

### TS1.6 — Business Logic: Queue

| TC ID | Test Case | Steps | Expected Result | Priority |
|---|---|---|---|---|
| TC-QUE-001 | Queue count correct | 8 people in queue zone | Count = 8 | High |
| TC-QUE-002 | QUEUE_THRESHOLD event fires | Count exceeds threshold | Event generated with count and threshold | High |
| TC-QUE-003 | Queue waiting time tracked per person | Person enters queue at T0, exits at T1 | Wait time = T1 - T0 | High |
| TC-QUE-004 | Queue length updates in real time | Person leaves queue | Count decremented within 1 inference cycle | Medium |
| TC-QUE-005 | Queue threshold configurable | Set threshold = 5 | Event fires at count = 6 | High |

### TS1.7 — Business Logic: Dwell Time

| TC ID | Test Case | Steps | Expected Result | Priority |
|---|---|---|---|---|
| TC-DWL-001 | Dwell time starts on ZONE_ENTER | Person enters zone at 10:00:00 | Enter timestamp recorded | High |
| TC-DWL-002 | Dwell time stops on ZONE_EXIT | Person exits at 10:05:30 | Dwell = 5m 30s | High |
| TC-DWL-003 | LONG_DWELL alert fires at threshold | Dwell > configured threshold | LONG_DWELL event generated | Critical |
| TC-DWL-004 | Dwell threshold configurable | Set threshold = 300s | Alert fires at 301s, not before | High |
| TC-DWL-005 | Dwell tracked per individual track_id | Two people in zone at same time | Dwell calculated independently per track | High |
| TC-DWL-006 | Dwell recorded if person still in zone at shutdown | System restart while person in zone | Dwell not reset to 0 on restart (or handled gracefully) | Medium |

### TS1.8 — Event Engine

| TC ID | Test Case | Steps | Expected Result | Priority |
|---|---|---|---|---|
| TC-EVT-001 | Event schema complete | Trigger any event | event_id, type, area, zone, camera, timestamp, severity all present | Critical |
| TC-EVT-002 | Event ID is unique | Generate 100 events | No duplicate event_ids | Critical |
| TC-EVT-003 | Event persisted to database | Trigger event → query DB | Event record exists | High |
| TC-EVT-004 | PERSON_DETECTED event generated | Person detected in frame | Event created with confidence and bbox | High |
| TC-EVT-005 | ZONE_ENTER event generated | Person enters polygon zone | ZONE_ENTER event with zone_id and track_id | High |
| TC-EVT-006 | ZONE_EXIT event generated | Person exits polygon zone | ZONE_EXIT event | High |
| TC-EVT-007 | OVER_OCCUPANCY event generated | Zone count > threshold | OVER_OCCUPANCY event with count and threshold | High |
| TC-EVT-008 | LONG_DWELL event generated | Dwell > threshold | LONG_DWELL event with duration | High |
| TC-EVT-009 | QUEUE_THRESHOLD event generated | Queue count > threshold | QUEUE_THRESHOLD event | High |
| TC-EVT-010 | CAMERA_OFFLINE event generated | Camera disconnects | CAMERA_OFFLINE event with camera_id | High |
| TC-EVT-011 | STREAM_ERROR event generated | RTSP error occurs | STREAM_ERROR event with error details | High |
| TC-EVT-012 | AI_ERROR event generated | Inference engine crashes | AI_ERROR event logged | High |
| TC-EVT-013 | Event severity correct per type | OVER_OCCUPANCY vs PERSON_DETECTED | Severity levels differ as configured | Medium |
| TC-EVT-014 | Events queryable by time range | GET /events?from=T1&to=T2 | Only events in range returned | High |
| TC-EVT-015 | Events queryable by camera_id | GET /events?camera_id=CAM-001 | Only CAM-001 events returned | High |

### TS1.9 — Alert System

| TC ID | Test Case | Steps | Expected Result | Priority |
|---|---|---|---|---|
| TC-ALT-001 | Dashboard notification on critical event | Trigger OVER_OCCUPANCY | Notification appears in dashboard | High |
| TC-ALT-002 | Alert not sent for low-severity event (if configured) | Trigger PERSON_DETECTED | No alert if below alert threshold | Medium |
| TC-ALT-003 | Alert rule configurable per event type | Set alert rule for LONG_DWELL | Alert fires only for LONG_DWELL | High |
| TC-ALT-004 | Webhook alert delivers correct payload | Configure webhook endpoint | POST received with correct event JSON | High |
| TC-ALT-005 | Alert delivery failure logged | Webhook endpoint unavailable | Delivery failure logged, event still saved | High |

### TS1.10 — User Management & RBAC

| TC ID | Test Case | Steps | Expected Result | Priority |
|---|---|---|---|---|
| TC-USR-001 | Admin can add camera | Login as Admin → POST /cameras | 201 Created | High |
| TC-USR-002 | Viewer cannot add camera | Login as Viewer → POST /cameras | 403 Forbidden | Critical |
| TC-USR-003 | Viewer cannot delete camera | Login as Viewer → DELETE /cameras/{id} | 403 Forbidden | Critical |
| TC-USR-004 | Operator can manage events | Login as Operator → PUT /events/{id}/status | 200 OK | High |
| TC-USR-005 | Supervisor has limited config access | Login as Supervisor → PUT /configs | Returns 403 for full config | High |
| TC-USR-006 | Admin can create users | POST /users as Admin | 201 Created | High |
| TC-USR-007 | Non-admin cannot create users | POST /users as Operator | 403 Forbidden | Critical |
| TC-USR-008 | User role change takes immediate effect | Change Viewer to Operator → test access | New permissions apply on next request | High |
| TC-USR-009 | Deleted user cannot login | Delete user → attempt login | 401 Unauthorized | High |
| TC-USR-010 | Password change invalidates old sessions | Change password → use old JWT | 401 Unauthorized | High |

### TS1.11 — Dashboard

| TC ID | Test Case | Steps | Expected Result | Priority |
|---|---|---|---|---|
| TC-DASH-001 | Overview shows total cameras count | 80 cameras configured | Total = 80 | High |
| TC-DASH-002 | Online/Offline counts accurate | 4 cameras offline | Online = 76, Offline = 4 | High |
| TC-DASH-003 | Active events count correct | 12 open events | Active Events = 12 | High |
| TC-DASH-004 | Camera status list shows correct states | CAM-003 offline | CAM-003 shows OFFLINE with timestamp | High |
| TC-DASH-005 | Events table shows time, camera, area, severity | Trigger events | All columns populated correctly | High |
| TC-DASH-006 | Dashboard refreshes without full page reload | Events generated | New events appear within configured interval | Medium |
| TC-DASH-007 | Occupancy analytics displayed per zone | Zone with history | Occupancy graph renders correctly | Medium |
| TC-DASH-008 | Reports filterable by date range | Select date range | Only events in range shown | Medium |
| TC-DASH-009 | Dashboard inaccessible without login | Open dashboard URL without session | Redirected to login page | Critical |

### TS1.12 — Monitoring & Logging

| TC ID | Test Case | Steps | Expected Result | Priority |
|---|---|---|---|---|
| TC-MON-001 | GPU utilization reported | Run inference | GPU % visible in monitoring | High |
| TC-MON-002 | VRAM usage reported | Run inference | VRAM MB visible | High |
| TC-MON-003 | Inference FPS reported per camera | Run pipeline | Per-camera inference FPS reported | High |
| TC-MON-004 | CPU utilization reported | Run system | CPU % reported | High |
| TC-MON-005 | RAM usage reported | Run system | RAM MB reported | High |
| TC-LOG-001 | Log entry has timestamp, severity, component | Trigger any event | All fields present in log | High |
| TC-LOG-002 | Log has camera_id on camera events | Camera event triggered | camera_id in log entry | High |
| TC-LOG-003 | No credentials in logs | Connect camera with credentials | Grep logs for password/token → none found | Critical |
| TC-LOG-004 | Log levels work correctly | Set level = WARNING | DEBUG and INFO not logged | Medium |
| TC-LOG-005 | Structured log format (JSON) | Check log output | Logs are valid JSON | Medium |

---

## 6. Test Suite 2 — Computer Vision & AI Testing

### TS2.1 — Detection Accuracy

**Test Dataset Requirements:**
- Minimum 500 labeled frames per class
- Covers: day, night, low light, motion blur, occlusion, crowd, different angles
- Held-out — not used in training

| TC ID | Test Case | Condition | Metric | Acceptance |
|---|---|---|---|---|
| TC-DET-001 | Person detection — normal lighting | Indoor, 1080p, clear | Precision, Recall | Per project targets (post-PoC) |
| TC-DET-002 | Person detection — low light | Night / dim lighting | Precision, Recall | Per project targets |
| TC-DET-003 | Person detection — strong backlight | Window behind subject | Precision, Recall | Per project targets |
| TC-DET-004 | Person detection — partial occlusion | 30–50% occluded | Recall | Per project targets |
| TC-DET-005 | Person detection — heavy occlusion | >50% occluded | Recall | Per project targets |
| TC-DET-006 | Person detection — crowd (high density) | 10+ people in frame | Precision, Recall | Per project targets |
| TC-DET-007 | Person detection — small object (far distance) | Person >10m from camera | Recall | Per project targets |
| TC-DET-008 | Person detection — motion blur | Person moving fast | Recall | Per project targets |
| TC-DET-009 | False positive rate — empty scene | No people present | FP Rate | ≤ project-defined threshold |
| TC-DET-010 | False positive rate — complex background | Machinery, shadows | FP Rate | ≤ project-defined threshold |
| TC-DET-011 | Vehicle detection accuracy | Forklifts, trucks in frame | Precision, Recall | Per project targets |
| TC-DET-012 | Helmet detection accuracy | Workers with/without helmets | Precision, Recall | Per project targets |
| TC-DET-013 | Safety vest detection accuracy | Workers with/without vests | Precision, Recall | Per project targets |
| TC-DET-014 | Detection bounding box format correct | Run inference | bbox = [x1, y1, x2, y2] consistent | Critical |
| TC-DET-015 | Detection includes all required fields | Run inference | class, confidence, bbox, camera_id, timestamp present | Critical |
| TC-DET-016 | Confidence threshold respected per class | Set person threshold = 0.50 | No detections below 0.50 returned | High |
| TC-DET-017 | Per-class threshold configurable without code change | Update config file | New threshold applied without redeploy | High |
| TC-DET-018 | mAP@0.5 on test set | Run eval script | mAP ≥ project-defined target | Critical |
| TC-DET-019 | mAP@0.5:0.95 on test set | Run eval script | mAP ≥ project-defined target | High |
| TC-DET-020 | Per-class AP reported | Run eval script | AP per class available in report | High |

### TS2.2 — Object Tracking

| TC ID | Test Case | Condition | Expected Result | Priority |
|---|---|---|---|---|
| TC-TRK-001 | Track ID persists across frames | Single person walking | Same ID maintained for full track | Critical |
| TC-TRK-002 | Track ID unique per person | Two people in frame | Different IDs assigned | Critical |
| TC-TRK-003 | Track resumes after brief occlusion | Person behind pillar | Same ID re-assigned after occlusion | High |
| TC-TRK-004 | New Track ID on new detection | Person leaves and new person enters | New ID assigned to new person | High |
| TC-TRK-005 | ID switches counted and reported | Run tracking benchmark | ID switch count available in metrics | High |
| TC-TRK-006 | Track fragmentation measured | Long-duration track | Fragment count low per project target | High |
| TC-TRK-007 | IDF1 metric on test sequence | Run tracking eval | IDF1 ≥ project target | High |
| TC-TRK-008 | Tracking continues at configured inference FPS | Set to 5 FPS | Tracks not lost due to low FPS | High |
| TC-TRK-009 | Tracking does not fail on empty frames | Zero detections | No crash, no stale tracks held indefinitely | High |
| TC-TRK-010 | Track disappears after person exits frame | Person exits | Track removed from active tracks | Medium |

### TS2.3 — ROI

| TC ID | Test Case | Expected Result | Priority |
|---|---|---|---|
| TC-ROI-001 | Detection only within ROI | Object outside ROI not detected | High |
| TC-ROI-002 | Object crossing ROI boundary detected when inside | Object enters ROI | Detection fires | High |
| TC-ROI-003 | ROI reduces inference area | Compare full frame vs ROI | GPU load reduced | High |
| TC-ROI-004 | ROI configurable per camera via API | POST ROI coordinates | Applied to correct camera only | High |
| TC-ROI-005 | ROI persists after service restart | Configure ROI → restart | ROI still active | High |

### TS2.4 — Zone Logic (CV Layer)

| TC ID | Test Case | Expected Result | Priority |
|---|---|---|---|
| TC-ZONE-CV-001 | ZONE_ENTER fires when centroid enters polygon | Person walks into zone | Event fired with correct zone_id | Critical |
| TC-ZONE-CV-002 | ZONE_EXIT fires when centroid leaves polygon | Person walks out | Event fired | Critical |
| TC-ZONE-CV-003 | Zone logic works with polygon zones (non-rectangular) | L-shaped zone | Enter/exit correctly detected | High |
| TC-ZONE-CV-004 | Multiple zones on same camera work independently | Two zones on CAM-001 | Events from each zone are separate | High |
| TC-ZONE-CV-005 | Person in two overlapping zones generates events for both | Overlapping polygons | Events for both zone_ids | Medium |

---

## 7. Test Suite 3 — API Testing

### TS3.1 — Authentication

| TC ID | Endpoint | Scenario | Expected | Priority |
|---|---|---|---|---|
| TC-API-001 | POST /api/v1/auth/login | Valid credentials | 200 + JWT token returned | Critical |
| TC-API-002 | POST /api/v1/auth/login | Wrong password | 401 Unauthorized | Critical |
| TC-API-003 | POST /api/v1/auth/login | Non-existent user | 401 Unauthorized (no user enumeration) | Critical |
| TC-API-004 | POST /api/v1/auth/login | Empty body | 400 Bad Request | High |
| TC-API-005 | POST /api/v1/auth/refresh | Valid refresh token | 200 + new access token | High |
| TC-API-006 | POST /api/v1/auth/refresh | Expired refresh token | 401 Unauthorized | High |
| TC-API-007 | POST /api/v1/auth/logout | Valid session | 200, token invalidated | High |
| TC-API-008 | Any endpoint | No token | 401 Unauthorized | Critical |
| TC-API-009 | Any endpoint | Invalid/malformed token | 401 Unauthorized | Critical |
| TC-API-010 | Any endpoint | Expired token | 401 Unauthorized | Critical |

### TS3.2 — Camera Endpoints

| TC ID | Endpoint | Scenario | Expected | Priority |
|---|---|---|---|---|
| TC-API-011 | GET /api/v1/cameras | Admin, valid token | 200 + camera list | High |
| TC-API-012 | GET /api/v1/cameras | Viewer, valid token | 200 + camera list (read only) | High |
| TC-API-013 | GET /api/v1/cameras/{id} | Valid ID | 200 + camera object | High |
| TC-API-014 | GET /api/v1/cameras/{id} | Non-existent ID | 404 Not Found | High |
| TC-API-015 | POST /api/v1/cameras | Admin, valid payload | 201 Created | High |
| TC-API-016 | POST /api/v1/cameras | Viewer (no permission) | 403 Forbidden | Critical |
| TC-API-017 | POST /api/v1/cameras | Missing required field | 400 + field error | High |
| TC-API-018 | PUT /api/v1/cameras/{id} | Admin, valid update | 200 Updated | High |
| TC-API-019 | DELETE /api/v1/cameras/{id} | Admin | 200/204, camera removed | High |
| TC-API-020 | DELETE /api/v1/cameras/{id} | Operator (no permission) | 403 Forbidden | Critical |

### TS3.3 — Events Endpoints

| TC ID | Endpoint | Scenario | Expected | Priority |
|---|---|---|---|---|
| TC-API-021 | GET /api/v1/events | Valid token | 200 + paginated event list | High |
| TC-API-022 | GET /api/v1/events?camera_id=CAM-001 | Filter by camera | Only CAM-001 events | High |
| TC-API-023 | GET /api/v1/events?type=OVER_OCCUPANCY | Filter by type | Filtered results | High |
| TC-API-024 | GET /api/v1/events?from=T1&to=T2 | Filter by time range | Events in range only | High |
| TC-API-025 | GET /api/v1/events?page=2&limit=20 | Pagination | Correct page returned | High |
| TC-API-026 | GET /api/v1/events/{id} | Valid event ID | 200 + full event object | High |
| TC-API-027 | GET /api/v1/events/{id} | Invalid ID | 404 Not Found | Medium |

### TS3.4 — Areas & Zones Endpoints

| TC ID | Endpoint | Scenario | Expected | Priority |
|---|---|---|---|---|
| TC-API-028 | GET /api/v1/areas | Valid token | 200 + areas list | High |
| TC-API-029 | POST /api/v1/areas | Admin, valid payload | 201 Created | High |
| TC-API-030 | POST /api/v1/zones | Admin, valid polygon | 201 Created | High |
| TC-API-031 | POST /api/v1/zones | Invalid polygon coordinates | 400 Bad Request | High |
| TC-API-032 | DELETE /api/v1/zones/{id} | Admin | 200/204 | High |
| TC-API-033 | DELETE /api/v1/zones/{id} | Viewer | 403 Forbidden | Critical |

### TS3.5 — API Non-Functional

| TC ID | Test Case | Expected | Priority |
|---|---|---|---|
| TC-API-040 | API versioning — /api/v1 prefix | All endpoints under /v1 | High |
| TC-API-041 | Rate limiting enforced | Exceed rate limit | 429 Too Many Requests | High |
| TC-API-042 | Rate limit headers present | Normal request | X-RateLimit-Limit, X-RateLimit-Remaining in response | Medium |
| TC-API-043 | Sorting supported on events | GET /events?sort=timestamp:desc | Correctly sorted | Medium |
| TC-API-044 | Error response has consistent schema | Trigger 400 | {error, message, field} structure | High |
| TC-API-045 | Large payload rejected | POST with 100MB body | 413 Request Entity Too Large | Medium |

---

## 8. Test Suite 4 — Security Testing

### TS4.1 — Authentication & Session

| TC ID | Test Case | Expected | Priority |
|---|---|---|---|
| TC-SEC-001 | Password stored as hash (never plaintext) | Inspect DB users table | No plaintext passwords | Critical |
| TC-SEC-002 | JWT signed with strong algorithm | Decode token header | Algorithm = RS256 or HS256 with strong secret | Critical |
| TC-SEC-003 | JWT expiry enforced | Use expired token | 401 Unauthorized | Critical |
| TC-SEC-004 | JWT not accepted after logout | Logout → reuse token | 401 Unauthorized | Critical |
| TC-SEC-005 | Brute force protection | 20 failed logins | Account locked or rate limited | High |
| TC-SEC-006 | Login response time constant | Valid vs invalid user | Response time similar (no timing oracle) | High |

### TS4.2 — Authorization & RBAC

| TC ID | Test Case | Expected | Priority |
|---|---|---|---|
| TC-SEC-007 | Viewer cannot access admin endpoints | Any admin-only endpoint as Viewer | 403 Forbidden | Critical |
| TC-SEC-008 | IDOR — access another user's data | GET /users/{other_user_id} as Operator | 403 Forbidden | Critical |
| TC-SEC-009 | IDOR — access camera from different area | GET /cameras/{id_not_owned} | 403 or 404 | Critical |
| TC-SEC-010 | Privilege escalation via PUT /users/{id} | Operator sets own role to Admin | 403 Forbidden | Critical |
| TC-SEC-011 | Horizontal privilege escalation — events | Operator accesses another operator's resources | 403 Forbidden | High |

### TS4.3 — Injection

| TC ID | Test Case | Expected | Priority |
|---|---|---|---|
| TC-SEC-012 | SQL injection in login | Username = `' OR 1=1 --` | 401 Unauthorized, no DB error | Critical |
| TC-SEC-013 | SQL injection in event filter | `?camera_id=1'; DROP TABLE events;--` | 400 or ignored, no DB change | Critical |
| TC-SEC-014 | XSS in camera name | POST camera with `<script>alert(1)</script>` as name | Stored safely, not executed in dashboard | Critical |
| TC-SEC-015 | XSS in zone name | POST zone with script tag | Not executed | High |
| TC-SEC-016 | Command injection in config fields | Config value with `; rm -rf /` | Rejected or sanitized | Critical |

### TS4.4 — Transport & Secrets

| TC ID | Test Case | Expected | Priority |
|---|---|---|---|
| TC-SEC-017 | API only accessible over HTTPS | HTTP request | Redirected or rejected | Critical |
| TC-SEC-018 | TLS version ≥ 1.2 | TLS scan | TLS 1.0/1.1 disabled | High |
| TC-SEC-019 | RTSP credentials not in source code | Grep source repo | No hardcoded passwords | Critical |
| TC-SEC-020 | DB credentials not in source code | Grep source repo | No hardcoded DB passwords | Critical |
| TC-SEC-021 | API keys not in source code | Grep source repo | No hardcoded secrets | Critical |
| TC-SEC-022 | Secrets loaded from environment or secret manager | Check startup config | Credentials from env vars only | Critical |
| TC-SEC-023 | RTSP credentials not in API response | GET /cameras/{id} | No RTSP password in response | Critical |
| TC-SEC-024 | Credentials not in logs | Run system → grep logs | No passwords in log files | Critical |

### TS4.5 — Input Validation & CSRF

| TC ID | Test Case | Expected | Priority |
|---|---|---|---|
| TC-SEC-025 | Oversized input rejected | 10,000-char camera name | 400 Bad Request | High |
| TC-SEC-026 | Invalid data types rejected | FPS = "abc" | 400 with type error | High |
| TC-SEC-027 | Negative values rejected | threshold = -5 | 400 Bad Request | High |
| TC-SEC-028 | CSRF protection on state-changing endpoints | Cross-origin POST | Rejected | High |

### TS4.6 — Audit Logging

| TC ID | Test Case | Expected | Priority |
|---|---|---|---|
| TC-SEC-029 | Login attempt logged | Successful and failed logins | Both recorded in audit log | High |
| TC-SEC-030 | Camera creation/deletion logged | Admin adds/removes camera | Audit entry with user, action, timestamp | High |
| TC-SEC-031 | User role change logged | Admin changes role | Audit entry with before/after role | High |
| TC-SEC-032 | Zone creation/deletion logged | Any zone change | Audit entry recorded | Medium |

---

## 9. Test Suite 5 — Performance & Load Testing

### TS5.1 — Baseline Single Camera

Run these first before scaling tests. All numbers TBD after PoC.

| TC ID | Test Case | Measure | Target |
|---|---|---|---|
| TC-PERF-001 | Single camera inference latency | ms per frame | ≤ PoC-defined target |
| TC-PERF-002 | Single camera end-to-end latency | Camera event → API | ≤ PoC-defined target |
| TC-PERF-003 | Single camera GPU utilization | GPU % | Measured baseline |
| TC-PERF-004 | Single camera VRAM usage | MB | Measured baseline |
| TC-PERF-005 | API response time — GET /events | ms | ≤ PoC-defined target |

### TS5.2 — Scale Testing

Run each stage, record all metrics before proceeding.

| TC ID | Camera Count | Metrics to Measure |
|---|---|---|
| TC-SCL-001 | 1 | FPS, latency, GPU%, VRAM, CPU%, RAM, dropped frames, event loss |
| TC-SCL-002 | 5 | Same |
| TC-SCL-003 | 10 | Same |
| TC-SCL-004 | 20 | Same |
| TC-SCL-005 | 40 | Same |
| TC-SCL-006 | 60 | Same |
| TC-SCL-007 | 80 | Same |

**Pass criteria per stage:** FPS ≥ configured target, event loss = 0, no OOM, no crashes.

### TS5.3 — Concurrent Events Load

| TC ID | Test Case | Expected | Priority |
|---|---|---|---|
| TC-PERF-010 | 80 cameras all generate events simultaneously | No event loss, DB not overloaded | Critical |
| TC-PERF-011 | 1000 events/minute ingestion | All events persisted | High |
| TC-PERF-012 | API under concurrent user load (50 users) | Response time within target | High |

### TS5.4 — Stress Testing (Beyond Expected Load)

| TC ID | Camera Count | Purpose |
|---|---|---|
| TC-STR-001 | 90 cameras | Find degradation point |
| TC-STR-002 | 100 cameras | Find failure point |
| TC-STR-003 | 120 cameras | Confirm failure behavior is graceful |

**Expected observations:**
- System degrades gracefully (FPS drops, not crashes)
- Error logged with actionable message
- System recovers when load returns to normal
- No data corruption

---

## 10. Test Suite 6 — Reliability & Failover Testing

### TS6.1 — Camera & Network Failures

| TC ID | Fault Injected | Expected Recovery | Priority |
|---|---|---|---|
| TC-REL-001 | Single camera RTSP disconnect | Auto-reconnect within configured timeout | Critical |
| TC-REL-002 | All cameras disconnect simultaneously | System retries all, no crash | Critical |
| TC-REL-003 | Network switch failure (camera subnet) | Cameras go offline, system logs, recovers when network restored | Critical |
| TC-REL-004 | Frozen camera stream | Frozen stream detected, logged, reconnect attempted | High |
| TC-REL-005 | Camera reboot (1–2 min offline) | Stream resumes after camera boots | High |
| TC-REL-006 | NVR reboot | All streams on that NVR recover | High |
| TC-REL-007 | One camera failure during 80-camera load | Other 79 cameras unaffected | Critical |

### TS6.2 — Service Failures

| TC ID | Fault Injected | Expected Recovery | Priority |
|---|---|---|---|
| TC-REL-008 | AI inference service crash | Service auto-restarts, CAMERA_OFFLINE or AI_ERROR event generated | Critical |
| TC-REL-009 | Backend API crash | Service auto-restarts, events buffered or re-sent | Critical |
| TC-REL-010 | Database unavailable (5 min) | System logs, buffers critical events if possible, recovers | Critical |
| TC-REL-011 | Database unavailable (30 min) | No data corruption on recovery | High |
| TC-REL-012 | Full machine restart | All services restart automatically | Critical |
| TC-REL-013 | GPU out of memory (OOM) | Graceful error, service restarts, alert generated | Critical |
| TC-REL-014 | Disk full | System logs CRITICAL, no crash, does not lose events silently | High |

### TS6.3 — Recovery Verification

After every fault injection test, verify:

- [ ] Correct events generated for the failure
- [ ] No events lost from cameras that stayed online
- [ ] No duplicate events generated post-recovery
- [ ] Logs contain root cause
- [ ] Monitoring alerts fired
- [ ] System returns to full operational state

---

## 11. Test Suite 7 — Soak Testing

Soak tests run continuously. Duration depends on project risk level.

| Phase | Duration | When |
|---|---|---|
| Phase 1 | 8 hours | After integration testing passes |
| Phase 2 | 24 hours | Before UAT |
| Phase 3 | 72 hours | Before Production sign-off |

### TS7.1 — Soak Monitoring Checklist

Monitor every 30 minutes during soak:

| Metric | Check | Alert Threshold |
|---|---|---|
| RAM usage | Trending upward (leak)? | >10% growth per hour |
| VRAM usage | Trending upward (leak)? | >5% growth per hour |
| Frame queue depth | Growing unbounded? | Queue > configured max |
| Inference FPS | Degrading over time? | Drop >15% from baseline |
| Dropped frames | Count increasing? | Per-camera rate > threshold |
| Active connections | Connection leak? | Growing without bound |
| Database size | Unexpected growth? | Disk >80% |
| Event latency | Increasing over time? | >2x baseline |
| Reconnect count | Excessive reconnects? | >10 per camera per hour |
| GPU temperature | Thermal throttling? | >85°C sustained |

### TS7.2 — Soak Pass Criteria

- No service crash during full duration
- No OOM conditions
- RAM stable (no unbounded growth)
- VRAM stable
- FPS within ±15% of baseline throughout
- Zero event loss for verifiable events
- All cameras recover from any transient disconnect
- No log errors related to queue overflow

---

## 12. Acceptance Criteria & Production Readiness Checklist

The system is not Production Ready until every item below is checked.

### 12.1 Functional Acceptance

- [ ] All 80 cameras (or configured count) integrated and online
- [ ] All AI use cases validated on production cameras
- [ ] Detection accuracy meets project-defined targets (per SRS §42)
- [ ] Tracking ID persistence verified
- [ ] Zone entry/exit events correct
- [ ] Line crossing events correct
- [ ] Occupancy calculation correct
- [ ] Queue detection correct
- [ ] Dwell time calculation correct
- [ ] All event types generate correctly
- [ ] Alert system delivers notifications

### 12.2 API Acceptance

- [ ] All endpoints return correct response schemas
- [ ] Authentication and authorization verified on all endpoints
- [ ] Pagination, filtering, and sorting working
- [ ] Rate limiting enforced
- [ ] API versioning active (/api/v1)
- [ ] Error responses consistent

### 12.3 Dashboard Acceptance

- [ ] Overview page shows correct counts
- [ ] Camera status accurate in real time
- [ ] Events displayed with correct columns
- [ ] Analytics charts rendering correctly
- [ ] Reports filterable and exportable
- [ ] Dashboard inaccessible without authentication

### 12.4 Security Acceptance

- [ ] Penetration test completed (or security review)
- [ ] No hardcoded secrets in source code
- [ ] No credentials in logs
- [ ] HTTPS enforced
- [ ] RBAC verified for all roles
- [ ] SQL injection protection verified
- [ ] XSS protection verified
- [ ] Audit logs active

### 12.5 Performance Acceptance

- [ ] 80-camera load test passed
- [ ] Inference latency within PoC-defined target
- [ ] Event latency within PoC-defined target
- [ ] API response within PoC-defined target
- [ ] GPU utilization within headroom (not at 100%)
- [ ] No dropped frames under normal load

### 12.6 Reliability Acceptance

- [ ] RTSP auto-reconnect verified
- [ ] All service crash recovery tests passed
- [ ] Database recovery tested
- [ ] Machine restart recovery verified
- [ ] 24h soak test passed
- [ ] 72h soak test passed

### 12.7 Operational Acceptance

- [ ] Monitoring dashboards operational
- [ ] Alerts configured and tested
- [ ] Structured logging active
- [ ] Backup procedure tested with successful restore
- [ ] Disaster recovery procedure documented and tested (RPO/RTO)
- [ ] Operations runbook completed
- [ ] All configuration in version control (except secrets)

---

## 13. Entry & Exit Criteria

### 13.1 Entry Criteria (Before Testing Begins)

| Criterion | Required For |
|---|---|
| SRS approved | All testing |
| Build deployable to test environment | All testing |
| Test cameras available (at least 2) | RTSP, functional, CV tests |
| AI model exported and versioned | CV tests |
| Test dataset labeled and held out | CV accuracy tests |
| API documentation available | API tests |
| Test environment matches production specs | Performance tests |

### 13.2 Exit Criteria (Before Sign-Off)

| Criterion | Required |
|---|---|
| 100% of Critical test cases passed | Yes |
| 100% of High test cases passed or waived with justification | Yes |
| Zero open Critical defects | Yes |
| Zero open High defects (or accepted with mitigation) | Yes |
| All soak tests passed | Yes |
| All acceptance criteria checked | Yes |
| Test report signed by QA Lead and Project Owner | Yes |

---

## 14. Defect Management

### 14.1 Severity Levels

| Severity | Definition | Examples |
|---|---|---|
| Critical | System unusable or data loss | RTSP crash takes down all cameras, event loss, auth bypass |
| High | Major feature broken, workaround unavailable | ZONE_ENTER not firing, RBAC not enforced |
| Medium | Feature works with limitation | Queue count off by 1, alert delayed |
| Low | Minor UI or cosmetic issue | Wrong icon, minor label text |

### 14.2 Defect Lifecycle

```
New → Assigned → In Progress → Fixed → Re-Test → Closed
                                           ↓
                                        Re-Opened
```

### 14.3 Defect Report Fields

| Field | Required |
|---|---|
| Defect ID | Yes |
| Title | Yes |
| Severity | Yes |
| SRS Requirement Ref | Yes |
| Test Case ID | Yes |
| Steps to Reproduce | Yes |
| Expected Result | Yes |
| Actual Result | Yes |
| Environment | Yes |
| Camera ID / Area (if applicable) | Yes |
| Log excerpt | Yes |
| Screenshot / Video | When applicable |

---

## 15. Risks & Mitigations

| Risk | Impact | Mitigation |
|---|---|---|
| Performance targets not defined until after PoC | Test Suite 5 targets TBD | Run PoC first; update Test Plan before load testing |
| Test cameras not available during testing | CV and RTSP tests blocked | Use recorded RTSP streams as fallback |
| GPU hardware not finalized | Cannot run 80-camera load test | Run load test on PoC hardware, extrapolate + caveat |
| Model not trained yet | CV accuracy tests blocked | Use baseline model; update criteria post-training |
| Database schema changes during testing | Test cases may break | Version the schema; regression-test on every schema change |
| Security test requires penetration tester | SEC tests partially manual | Use OWASP checklist + Burp Suite; escalate findings |
| Soak test environment not stable 72h | Soak results inconclusive | Ensure test environment is isolated from dev deployments |

---

*End of Test Plan v1.0*  
*Next step: Review with project team → confirm PoC targets → populate performance thresholds → begin TS1 execution.*
