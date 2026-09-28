# ICVMS-77

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-77 | TC-API-011 \| GET /cameras — returns paginated camera list | Admin logged in. System running. | Action: GET /api/v1/cameras with valid Admin tokenExpected: HTTP 200. Full camera list returned.Action: Check response schema for each cameraExpected: camera_id, name, area, status, fps, resolution present.Action: Verify RTSP credentials absentExpected: No rtsp_password field in any camera object. | Camera list returns correct schema. RTSP credentials never exposed. | High | To Do |
