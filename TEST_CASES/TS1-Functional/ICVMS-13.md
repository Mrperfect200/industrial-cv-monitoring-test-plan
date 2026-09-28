# ICVMS-13

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-13 | TC-CAM-010 \| Camera credentials not returned in API response | Camera configured with RTSP credentials (username/password). Admin logged in. | Action: Send GET /api/v1/cameras/{id}Expected: HTTP 200.Action: Inspect full response bodyExpected: Fields rtsp_password, password, credentials, secret are absent.Action: Send GET /api/v1/cameras (list endpoint)Expected: RTSP credentials absent from all camera objects in list. | No RTSP credentials present in any API response. Only non-sensitive fields returned. | Highest | To Do |
