# ICVMS-9

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-9 | TC-CAM-002 \| Add camera with duplicate camera_id → 409 | Admin logged in. Camera CAM-001 already exists in the system. | Action: Send POST /api/v1/cameras with camera_id = CAM-001 (duplicate)Test Data: {"camera_id":"CAM-001","name":"Duplicate","rtsp_url":"rtsp://x/y"}Expected: HTTP 409 Conflict.Action: Check error response bodyExpected: Error message references duplicate camera_id.Action: Verify original CAM-001 is unchangedTest Data: GET /api/v1/cameras/CAM-001Expected: Original camera data intact. | HTTP 409 returned. No duplicate created. Original camera unaffected. | High | To Do |
