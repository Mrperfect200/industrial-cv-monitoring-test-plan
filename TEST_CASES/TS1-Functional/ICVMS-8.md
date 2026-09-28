# ICVMS-8

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-8 | TC-CAM-001 \| Add new camera with all required fields | Admin user is logged in. System is running. Valid RTSP URL is available. | Action: Send POST /api/v1/cameras with full valid payloadTest Data: {"name":"Cam1","area":"AREA-A","rtsp_url":"rtsp://192.168.1.10/stream","fps":25,"codec":"H264","resolution":"1920x1080"}Expected: HTTP 201 Created. Response body contains camera_id.Action: Send GET /api/v1/cameras/{camera_id}Test Data: Use camera_id from step 1Expected: HTTP 200. All submitted fields returned correctly.Action: Check camera appears in GET /api/v1/cameras listExpected: Camera present in list with correct area and status. | Camera saved with unique ID. All fields correct. Camera visible in list. | High | To Do |
