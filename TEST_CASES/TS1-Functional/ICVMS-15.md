# ICVMS-15

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-15 | TC-RTSP-003 \| Auto-reconnect after disconnect | Camera CAM-001 is actively streaming. System running normally. | Action: Physically disconnect camera or stop RTSP sourceExpected: System detects disconnection within configured timeout.Action: Wait for first retry attemptExpected: System logs retry attempt with camera_id and timestamp.Action: Wait for second retry attemptExpected: Retry interval is longer than first (exponential backoff).Action: Reconnect camera / restart RTSP sourceExpected: Stream resumes. Processing continues from where it left off. | Auto-reconnect occurs. Exponential backoff observed. Stream resumes on reconnection. | Highest | To Do |
