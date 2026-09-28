# ICVMS-20

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-20 | TC-VID-001 \| Processing FPS = 5 configurable | Camera streaming at 25 FPS. System running. | Action: Set processing_fps = 5 via configurationTest Data: {"processing_fps": 5}Expected: Configuration accepted.Action: Monitor frame processing rate for 30 secondsTest Data: Check inference logs or metrics endpointExpected: ~5 frames processed per second (±1).Action: Compare GPU utilization vs 25 FPSExpected: GPU utilization lower at 5 FPS. | System processes ~5 FPS. GPU load reduced compared to 25 FPS. | High | To Do |
