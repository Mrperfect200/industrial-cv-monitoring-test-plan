# ICVMS-14

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-14 | TC-RTSP-001 \| Connect to valid RTSP stream | Camera with valid RTSP URL configured in system. | Action: System attempts to open RTSP stream on startupTest Data: rtsp_url is valid and reachableExpected: Stream opens. FPS reported within ±2 of camera FPS.Action: Check stream health statusTest Data: GET /api/v1/cameras/{id}Expected: status = ONLINE. fps_actual reported. | RTSP stream opens successfully. FPS monitored and reported. | High | To Do |
