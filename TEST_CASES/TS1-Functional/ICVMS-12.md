# ICVMS-12

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-12 | TC-CAM-008 \| Camera status reflects ONLINE/OFFLINE | Camera CAM-001 configured with valid RTSP URL. System running. | Action: Connect camera CAM-001 to systemTest Data: RTSP URL is reachableExpected: Camera connects successfully.Action: Send GET /api/v1/cameras/CAM-001Expected: status = ONLINE.Action: Disconnect the physical camera / stop RTSP sourceExpected: Within configured timeout, status changes to OFFLINE.Action: Reconnect cameraExpected: Status returns to ONLINE automatically. | Status accurately reflects ONLINE when connected, OFFLINE when disconnected. | High | To Do |
