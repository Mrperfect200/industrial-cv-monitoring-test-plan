# ICVMS-123

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-123 | TC-STR-001 \| Stress test — 90 cameras graceful degradation | System running at 80 cameras. k6 or load testing tool available. | Action: Ramp cameras to 90 (10 above expected max)Expected: System accepts additional load.Action: Monitor for degradationTest Data: FPS, GPU%, error rateExpected: FPS may drop but system stays up.Action: Record degradation behaviorExpected: Graceful degradation documented (FPS drops, not crashes).Action: Return to 80 camerasExpected: System recovers to normal metrics within 60 seconds. | System degrades gracefully at 90 cameras. No crash. Recovers when load normalizes. | High | To Do |
