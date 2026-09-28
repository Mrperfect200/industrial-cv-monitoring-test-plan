# Test Cases Summary Table

| TC ID | Title | Suite | Priority |
|-------|-------|-------|----------|
| ICVMS-8 | Add new camera with all required fields | TS1-Functional | High |
| ICVMS-9 | Add camera with duplicate camera_id → 409 | TS1-Functional | High |
| ICVMS-10 | Add camera with missing required fields → 400 | TS1-Functional | High |
| ICVMS-11 | Delete camera stops associated stream | TS1-Functional | High |
| ICVMS-12 | Camera status reflects ONLINE/OFFLINE | TS1-Functional | High |
| ICVMS-13 | Camera credentials not returned in API response | TS1-Functional | Critical |
| ICVMS-14 | Connect to valid RTSP stream | TS1-Functional | High |
| ICVMS-15 | Auto-reconnect after disconnect | TS1-Functional | Critical |
| ICVMS-16 | One camera disconnect does not affect others | TS1-Functional | Critical |
| ICVMS-17 | Frozen stream detection | TS1-Functional | High |
| ICVMS-18 | RTSP failure generates STREAM_ERROR event | TS1-Functional | High |
| ICVMS-19 | RTSP credentials not logged | TS1-Functional | Critical |
| ICVMS-20 | Processing FPS = 5 configurable | TS1-Functional | High |
| ICVMS-21 | Processing FPS = 25 configurable | TS1-Functional | High |
| ICVMS-22 | Frame skipping reduces GPU load | TS1-Functional | High |
| ICVMS-23 | Create polygon zone on camera | TS1-Functional | High |
| ICVMS-24 | Zone persists after system restart | TS1-Functional | High |
| ICVMS-25 | Line crossing generates LINE_CROSSED event | TS1-Functional | Critical |
| ICVMS-26 | Entry direction detected correctly | TS1-Functional | High |
| ICVMS-27 | Exit direction detected correctly | TS1-Functional | High |
| ICVMS-28 | Occupancy increments on ZONE_ENTER | TS1-Functional | High |
| ICVMS-29 | OVER_OCCUPANCY event fires at threshold | TS1-Functional | Critical |
| ICVMS-30 | Occupancy threshold configurable via API | TS1-Functional | High |
| ICVMS-31 | Queue count correct | TS1-Functional | High |
| ICVMS-32 | QUEUE_THRESHOLD event fires | TS1-Functional | High |
| ICVMS-33 | Dwell time calculated correctly | TS1-Functional | High |
| ICVMS-34 | LONG_DWELL alert fires at threshold | TS1-Functional | Critical |
| ICVMS-35 | Event schema complete (all required fields) | TS1-Functional | Critical |
| ICVMS-36 | Event ID is unique | TS1-Functional | Critical |
| ICVMS-37 | Event persisted to database | TS1-Functional | High |
| ICVMS-38 | Dashboard notification on critical event | TS1-Functional | High |
| ICVMS-39 | Webhook alert delivers correct payload | TS1-Functional | High |
| ICVMS-40 | Viewer cannot add camera (403) | TS1-Functional | Critical |
| ICVMS-41 | Viewer cannot delete camera (403) | TS1-Functional | Critical |
| ICVMS-42 | Non-admin cannot create users (403) | TS1-Functional | Critical |
| ICVMS-43 | Overview shows correct camera counts | TS1-Functional | High |
| ICVMS-44 | Online/Offline counts accurate | TS1-Functional | High |
| ICVMS-45 | Dashboard inaccessible without login | TS1-Functional | Critical |
| ICVMS-46 | GPU utilization reported | TS1-Functional | High |
| ICVMS-47 | No credentials in logs | TS1-Functional | Critical |
| ICVMS-48 | Person detection — normal indoor lighting | TS2-Computer-Vision-AI | High |
| ICVMS-49 | Person detection — low light / night | TS2-Computer-Vision-AI | High |
| ICVMS-50 | Person detection — strong backlight | TS2-Computer-Vision-AI | High |
| ICVMS-51 | Person detection — partial occlusion 30-50% | TS2-Computer-Vision-AI | High |
| ICVMS-52 | Person detection — high density crowd | TS2-Computer-Vision-AI | High |
| ICVMS-53 | Person detection — small object far distance | TS2-Computer-Vision-AI | High |
| ICVMS-54 | Person detection — motion blur | TS2-Computer-Vision-AI | High |
| ICVMS-55 | False positive rate — empty scene | TS2-Computer-Vision-AI | High |
| ICVMS-56 | Bounding box format correct xyxy consistent | TS2-Computer-Vision-AI | Critical |
| ICVMS-57 | Detection includes all required output fields | TS2-Computer-Vision-AI | Critical |
| ICVMS-58 | Confidence threshold respected per class | TS2-Computer-Vision-AI | High |
| ICVMS-59 | Per-class threshold configurable without code change | TS2-Computer-Vision-AI | High |
| ICVMS-60 | mAP@0.5 on held-out test set meets target | TS2-Computer-Vision-AI | Critical |
| ICVMS-61 | Track ID persists across frames for same object | TS2-Computer-Vision-AI | Critical |
| ICVMS-62 | Track ID unique per individual person | TS2-Computer-Vision-AI | Critical |
| ICVMS-63 | Track resumes same ID after brief occlusion | TS2-Computer-Vision-AI | High |
| ICVMS-64 | ID switches counted and reported in metrics | TS2-Computer-Vision-AI | High |
| ICVMS-65 | IDF1 metric meets project-defined target | TS2-Computer-Vision-AI | High |
| ICVMS-66 | Detection only within configured ROI | TS2-Computer-Vision-AI | High |
| ICVMS-67 | ROI reduces GPU inference area vs full frame | TS2-Computer-Vision-AI | High |
| ICVMS-68 | ZONE_ENTER fires when centroid enters polygon | TS2-Computer-Vision-AI | Critical |
| ICVMS-69 | ZONE_EXIT fires when centroid leaves polygon | TS2-Computer-Vision-AI | Critical |
| ICVMS-70 | Multiple zones on same camera work independently | TS2-Computer-Vision-AI | High |
| ICVMS-71 | POST /auth/login — valid credentials returns JWT | TS3-API | Critical |
| ICVMS-72 | POST /auth/login — wrong password returns 401 | TS3-API | Critical |
| ICVMS-73 | POST /auth/login — no user enumeration on invalid user | TS3-API | Critical |
| ICVMS-74 | Any endpoint — no token returns 401 | TS3-API | Critical |
| ICVMS-75 | Any endpoint — invalid token returns 401 | TS3-API | Critical |
| ICVMS-76 | Any endpoint — expired token returns 401 | TS3-API | Critical |
| ICVMS-77 | GET /cameras — returns paginated camera list | TS3-API | High |
| ICVMS-78 | POST /cameras — Admin creates camera returns 201 | TS3-API | High |
| ICVMS-79 | POST /cameras — Viewer gets 403 Forbidden | TS3-API | Critical |
| ICVMS-80 | POST /cameras — missing required field returns 400 | TS3-API | High |
| ICVMS-81 | DELETE /cameras/{id} — Admin succeeds 204 | TS3-API | High |
| ICVMS-82 | DELETE /cameras/{id} — Operator gets 403 | TS3-API | Critical |
| ICVMS-83 | GET /events — returns paginated event list | TS3-API | High |
| ICVMS-84 | GET /events?camera_id — filters by camera correctly | TS3-API | High |
| ICVMS-85 | GET /events?from&to — filters by time range correctly | TS3-API | High |
| ICVMS-86 | GET /events — pagination returns correct page | TS3-API | High |
| ICVMS-87 | DELETE /zones/{id} — Viewer gets 403 | TS3-API | Critical |
| ICVMS-88 | API versioning /api/v1 prefix active on all endpoints | TS3-API | High |
| ICVMS-89 | Rate limiting returns 429 on exceed | TS3-API | High |
| ICVMS-90 | Error responses have consistent JSON schema | TS3-API | High |
| ICVMS-91 | Passwords stored as hash — no plaintext in DB | TS4-Security | Critical |
| ICVMS-92 | JWT signed with strong algorithm RS256/HS256 | TS4-Security | Critical |
| ICVMS-93 | JWT expiry enforced — expired token rejected | TS4-Security | Critical |
| ICVMS-94 | JWT not accepted after logout | TS4-Security | Critical |
| ICVMS-95 | Brute force protection — lockout after failed attempts | TS4-Security | High |
| ICVMS-96 | Viewer cannot access admin-only endpoints → 403 | TS4-Security | Critical |
| ICVMS-97 | IDOR — access another user data blocked → 403 | TS4-Security | Critical |
| ICVMS-98 | Privilege escalation via PUT /users blocked → 403 | TS4-Security | Critical |
| ICVMS-99 | SQL injection in login username field blocked | TS4-Security | Critical |
| ICVMS-100 | SQL injection in event query filter blocked | TS4-Security | Critical |
| ICVMS-101 | XSS in camera name stored safely not executed | TS4-Security | Critical |
| ICVMS-102 | API only accessible over HTTPS — HTTP rejected | TS4-Security | Critical |
| ICVMS-103 | TLS 1.2+ enforced — TLS 1.0/1.1 disabled | TS4-Security | High |
| ICVMS-104 | RTSP credentials not hardcoded in source code | TS4-Security | Critical |
| ICVMS-105 | DB credentials not hardcoded in source code | TS4-Security | Critical |
| ICVMS-106 | All secrets loaded from environment variables only | TS4-Security | Critical |
| ICVMS-107 | RTSP credentials absent from all API responses | TS4-Security | Critical |
| ICVMS-108 | No credentials present in any log files | TS4-Security | Critical |
| ICVMS-109 | Login attempts (success+fail) in audit log | TS4-Security | High |
| ICVMS-110 | Camera create/delete changes recorded in audit log | TS4-Security | High |
| ICVMS-111 | Baseline: single camera inference latency (ms) | TS5-Performance-Load | High |
| ICVMS-112 | Baseline: single camera end-to-end event latency | TS5-Performance-Load | High |
| ICVMS-113 | Baseline: single camera GPU utilization % | TS5-Performance-Load | High |
| ICVMS-114 | Baseline: API response time GET /events | TS5-Performance-Load | High |
| ICVMS-115 | Scale test — 1 camera: FPS/latency/GPU/CPU/RAM | TS5-Performance-Load | High |
| ICVMS-116 | Scale test — 5 cameras: all metrics measured | TS5-Performance-Load | High |
| ICVMS-117 | Scale test — 10 cameras: all metrics measured | TS5-Performance-Load | High |
| ICVMS-118 | Scale test — 20 cameras: all metrics measured | TS5-Performance-Load | High |
| ICVMS-119 | Scale test — 40 cameras: all metrics measured | TS5-Performance-Load | High |
| ICVMS-120 | Scale test — 60 cameras: all metrics measured | TS5-Performance-Load | High |
| ICVMS-121 | Scale test — 80 cameras: full production load | TS5-Performance-Load | Critical |
| ICVMS-122 | 80 cameras simultaneous events — zero event loss | TS5-Performance-Load | Critical |
| ICVMS-123 | Stress test — 90 cameras graceful degradation | TS5-Performance-Load | High |
| ICVMS-124 | Stress test — 100 cameras find failure point | TS5-Performance-Load | High |
| ICVMS-125 | Stress test — 120 cameras confirm graceful behavior | TS5-Performance-Load | High |
| ICVMS-126 | Single camera RTSP disconnect → auto-reconnect | TS6-Reliability-Failover | Critical |
| ICVMS-127 | All cameras disconnect simultaneously → no crash | TS6-Reliability-Failover | Critical |
| ICVMS-128 | Frozen camera stream detected and logged | TS6-Reliability-Failover | High |
| ICVMS-129 | Camera reboot → stream resumes automatically | TS6-Reliability-Failover | High |
| ICVMS-130 | One camera failure does NOT affect other 79 cameras | TS6-Reliability-Failover | Critical |
| ICVMS-131 | AI inference service crash → auto-restart verified | TS6-Reliability-Failover | Critical |
| ICVMS-132 | Backend API crash → auto-restart verified | TS6-Reliability-Failover | Critical |
| ICVMS-133 | Database unavailable 5 min → full recovery verified | TS6-Reliability-Failover | Critical |
| ICVMS-134 | Database unavailable 30 min → no data corruption | TS6-Reliability-Failover | High |
| ICVMS-135 | Full machine restart → all services restart automatically | TS6-Reliability-Failover | Critical |
| ICVMS-136 | GPU OOM → graceful error no data corruption | TS6-Reliability-Failover | Critical |
| ICVMS-137 | Disk full → CRITICAL log no silent event loss | TS6-Reliability-Failover | High |
| ICVMS-138 | 8-hour soak test — no crashes no memory leaks | TS7-Soak | Critical |
| ICVMS-139 | 24-hour soak test — FPS stable VRAM stable | TS7-Soak | Critical |
| ICVMS-140 | 72-hour soak test — full production validation sign-off | TS7-Soak | Critical |
| ICVMS-141 | Monitor RAM/VRAM/FPS/queues every 30 min during soak | TS7-Soak | High |
| ICVMS-142 | Verify camera auto-recovery during soak duration | TS7-Soak | High |