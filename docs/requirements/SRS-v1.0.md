# Software Requirements Specification (SRS)
**Project:** Industrial Computer Vision Monitoring System  
**Version:** 1.0  
**Environment:** On-Premise / Factory  
**Camera Scale:** Up to 80 cameras  
**Availability:** 24/7  
**Architecture:** Edge/On-Premise AI + Backend + Database + Web Dashboard  

---

## 2. System Purpose

The system is a Computer Vision platform that receives video streams from factory cameras, processes them using AI models to detect required events, then converts AI results into Business Events stored in a database, displayed on a Dashboard, and exposed via APIs.

### High-Level Flow

```
IP Cameras → RTSP → Stream Ingestion → Video Processing → AI Inference
→ Detection → Tracking → Zones / Lines / ROIs → Business Logic
→ Events → Database + Alert System → Backend API → Web Dashboard
```

---

## 3. Business Objectives

- Monitor factory areas using cameras
- Detect required persons/objects
- Track objects across frames
- Calculate Entry/Exit counts
- Monitor Zones
- Calculate Occupancy
- Calculate Queue Length
- Calculate Dwell Time
- Generate Events when conditions are met
- Display events in Dashboard
- Provide Historical Data
- Provide APIs for external systems
- Operate 24/7
- Scale from few cameras to ~80
- Minimize CPU/GPU/RAM consumption
- Run fully inside the factory network

---

## 4. Scope

### 4.1 In Scope

**Video:** RTSP streams, camera configuration, stream health, FPS monitoring, resolution monitoring, reconnection, frame drop handling.

**AI:** Object Detection, Object Tracking, Classification (when needed), ROI detection, Line crossing, Zone monitoring.

**Business Intelligence:** Entry/Exit, Occupancy, Queue, Dwell Time, Alerts, Event generation.

**Backend:** REST APIs, Authentication, Authorization, Camera/Zone/Event/User/Configuration management.

**Database:** Cameras, Areas, Zones, Events, Users, Configurations, System logs.

**Dashboard:** Live status, Camera status, Events, Statistics, Reports, Configuration.

### 4.2 Out of Scope (unless added as Change Request)

- Manufacturing ERP
- PLC / machine control
- Physical camera installation / network cabling
- Building access-control system
- Full video archival system
- Facial recognition / biometric identification

---

## 5. System Architecture

Modular architecture:

```
Cameras (1–80) → RTSP → Stream Manager → Frame Processor → AI Inference Engine
→ [Detection | Tracking | Classification] → Business Logic → Events
→ Backend/API → [Database | Alerts] → Web Dashboard
```

---

## 6. Factory Hierarchy

```
Factory
 ├── Area A
 │    ├── Camera 01 ... Camera N
 ├── Area B
 │    ├── Camera 10 ... Camera N
 └── Area C
      └── Camera 20 ... Camera N
```

---

## 7. Camera Requirements

Each camera must have: Unique ID, Name, IP address, RTSP URL, Resolution, FPS, Codec, Location, Area, Status, Model, Manufacturer, Stream credentials, Connection status.

Example:
```json
{
  "camera_id": "CAM-001",
  "name": "Production Line 1",
  "area": "AREA-A",
  "resolution": "1920x1080",
  "fps": 25,
  "codec": "H264",
  "status": "ONLINE"
}
```

---

## 8. RTSP Requirements

- Support RTSP streams
- Open stream and verify availability
- Auto-reconnect with exponential backoff on disconnect
- Log stream failures
- Monitor FPS, latency, dropped frames
- Generate CAMERA_OFFLINE and STREAM_ERROR events
- One camera failure must NOT crash other streams

---

## 9. Video Processing Requirements

Processing FPS must be configurable: 5 / 10 / 15 / 25 FPS (camera may run at 25 FPS; AI processes at lower rate to reduce GPU/CPU load).

---

## 10. AI Model Requirements

Object Detection output per detection:
```json
{
  "class": "person",
  "confidence": 0.94,
  "bbox": [120, 80, 300, 500],
  "camera_id": "CAM-001",
  "timestamp": "2026-09-28T10:20:30"
}
```

Supported classes (configurable): Person, Vehicle, Worker, Product, Pallet, Helmet, Safety Vest.

---

## 11. Confidence Threshold

Configurable per class — never hardcoded:
- Person: 0.50 (example)
- Helmet: 0.65 (example)
- Vehicle: 0.70 (example)

---

## 12. Object Tracking

Track ID must persist per object across frames. Each unique object gets a unique Track ID.

---

## 13. ROI

Configurable Region of Interest per camera. AI must NOT process entire frame if ROI is defined.

---

## 14. Line Crossing

Virtual line crossing generates an event with: Camera ID, Track ID, Direction (ENTRY/EXIT), Timestamp, Line ID.

---

## 15. Zone Monitoring

Supported zone types: Polygon, Restricted, Production, Waiting, Entry.  
Zone events: ZONE_ENTER, ZONE_EXIT triggered when object centroid crosses polygon boundary.

---

## 16. Occupancy

Per zone: Current / Maximum / Minimum / Average occupancy.  
OVER_OCCUPANCY event fires when Current > Threshold (configurable).

---

## 17. Queue Detection

Queue Length, count, waiting time, configurable threshold.  
QUEUE_THRESHOLD event fires on exceed.

---

## 18. Dwell Time

Per Track ID inside Zone: Enter timestamp → Exit timestamp = Dwell duration.  
LONG_DWELL alert fires when Dwell > Threshold (configurable).

---

## 19. Event Engine

Every event must contain:

```json
{
  "event_id": "EVT-00001",
  "type": "ZONE_OVER_OCCUPANCY",
  "area": "AREA-A",
  "zone": "ZONE-01",
  "camera": "CAM-001",
  "count": 23,
  "threshold": 20,
  "timestamp": "2026-09-28T10:30:00"
}
```

Required fields: event_id, type, camera_id, area_id, zone_id, object_id, timestamp, confidence, severity, status, metadata.

---

## 20. Event Types

```
PERSON_DETECTED, OBJECT_DETECTED, LINE_CROSSED, ZONE_ENTER, ZONE_EXIT,
OVER_OCCUPANCY, LONG_DWELL, QUEUE_THRESHOLD, CAMERA_OFFLINE,
STREAM_ERROR, AI_ERROR, SYSTEM_ERROR
```

System must support adding new event types.

---

## 21. Alert System

Event → Rule Engine → Alert  
Alert channels: Dashboard notification, Email, Webhook, External API (per final scope).

---

## 22. Backend API

### Auth
- POST /api/v1/auth/login
- POST /api/v1/auth/logout
- POST /api/v1/auth/refresh

### Cameras
- GET/POST /api/v1/cameras
- GET/PUT/DELETE /api/v1/cameras/{id}

### Events
- GET /api/v1/events
- GET /api/v1/events/{id}

### Areas
- GET/POST /api/v1/areas
- PUT /api/v1/areas/{id}

### Zones
- GET/POST /api/v1/zones
- PUT/DELETE /api/v1/zones/{id}

---

## 23. API Non-Functional Requirements

Authentication, Authorization, Validation, Pagination, Filtering, Sorting, Rate limiting, Error handling, Logging, API versioning (/api/v1).

---

## 24. Database Tables

Users, Roles, Areas, Cameras, Zones, Lines, Events, Alerts, Configurations, SystemLogs, AuditLogs.

Relationships: Factory → Areas → (Cameras, Zones, Lines).

---

## 25. Dashboard

- Overview: total cameras, online/offline counts, active events, areas count
- Camera status list
- Live view (on demand)
- Events table: time, camera, area, event, severity, status
- Analytics: Occupancy, Entry/Exit, Queue, Dwell Time, Events
- Reports (filterable)
- Configuration

---

## 26. User Roles (RBAC)

| Role | Cameras | Configuration | Users | Events |
|---|---|---|---|---|
| Admin | Full | Full | Full | Full |
| Supervisor | View | Limited | No | Full |
| Operator | View | No | No | Manage |
| Viewer | View | No | No | View |

---

## 27. Security Requirements

HTTPS, Password hashing, JWT/session security, RBAC, Input validation, SQL injection protection, XSS protection, CSRF protection, Secure RTSP credentials, Secrets outside source code, Audit logging.

---

## 28. Network Architecture

```
Camera Network → AI/Edge Network → Application Network → Database
```

Cameras must NOT be directly exposed to the Internet.

---

## 29. Performance Requirements

Targets defined after PoC benchmark. Never invented upfront.  
Example placeholders:
- Inference latency ≤ X ms
- Event latency ≤ X seconds
- API response ≤ X ms
- Camera recovery ≤ X seconds

---

## 30. Reliability

- 24/7 operation
- Auto restart for all services
- Camera reconnect
- Model/DB recovery
- Single-component failure must not cascade

---

## 31. Monitoring

Camera health, RTSP health, AI service, Inference FPS, GPU, CPU, RAM, Disk, Database, API, Network.

---

## 32. Logging

Structured JSON logs:
```json
{
  "timestamp": "2026-09-28T10:30:00Z",
  "service": "inference",
  "severity": "ERROR",
  "component": "tracker",
  "message": "Track ID assignment failed",
  "camera_id": "CAM-007",
  "trace_id": "abc-123"
}
```
Levels: DEBUG / INFO / WARNING / ERROR / CRITICAL. No credentials in logs.

---

## 33. Backup

Backup scope: Database, Configuration, Zones, Lines, Users, System settings.  
Policy (to define): Frequency, Retention, Storage location, Recovery procedure.

---

## 34. Disaster Recovery

RPO and RTO to be defined and tested with actual restore procedure.

---

## 35. Scalability Test Plan (Reference)

| Stage | Cameras | Measure |
|---|---|---|
| 1 | 1 | FPS, latency, GPU, CPU, RAM |
| 2 | 5 | Same |
| 3 | 10 | Same |
| 4 | 20 | Same |
| 5 | 40 | Same |
| 6 | 60 | Same |
| 7 | 80 | Same |

---

## 36. PoC Requirement

Before buying hardware or building production architecture, a PoC must be completed:

```
Real Camera → Real RTSP → Real Model → Real Hardware → Benchmark
```

Starting from 1 camera → 2 → 5 → 10, then extrapolate to 80.

---

*SRS v1.0 — basis for RTM and Test Plan*
