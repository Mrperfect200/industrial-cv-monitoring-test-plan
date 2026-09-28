# ICVMS-16

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-16 | TC-RTSP-005 \| One camera disconnect does not affect others | CAM-001 and CAM-002 both actively streaming and processing. | Action: Disconnect CAM-001 (stop its RTSP source)Expected: CAM-001 goes OFFLINE.Action: Check CAM-002 status and inference FPSExpected: CAM-002 remains ONLINE. Inference FPS unchanged.Action: Check system logs for any cascading errorsExpected: No errors referencing CAM-002 due to CAM-001 failure. | CAM-002 completely unaffected by CAM-001 disconnection. | Highest | To Do |
