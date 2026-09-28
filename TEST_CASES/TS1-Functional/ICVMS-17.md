# ICVMS-17

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-17 | TC-RTSP-006 \| Frozen stream detection and logging | Camera streaming. System configured to detect frozen streams. | Action: Feed a static (frozen) frame repeatedly for 30+ secondsTest Data: Simulate frozen camera by repeating same frameExpected: System detects stream as frozen within configured timeout.Action: Check system logsExpected: Log entry: frozen stream detected, camera_id, timestamp.Action: Check eventsExpected: STREAM_ERROR or CAMERA_OFFLINE event generated. | Frozen stream detected. Event generated. Logged with camera_id. | High | To Do |
