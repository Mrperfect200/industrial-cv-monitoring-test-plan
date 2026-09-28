# ICVMS-11

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-11 | TC-CAM-005 \| Delete camera stops associated stream | Admin logged in. Camera CAM-005 exists and has an active RTSP stream. | Action: Send DELETE /api/v1/cameras/CAM-005Expected: HTTP 200 or 204.Action: Send GET /api/v1/cameras/CAM-005Expected: HTTP 404 Not Found.Action: Check RTSP stream for CAM-005 is no longer processingTest Data: Check system logs or stream manager statusExpected: No active stream for CAM-005 in logs. | Camera deleted. Stream stopped. Camera not found on subsequent GET. | High | To Do |
