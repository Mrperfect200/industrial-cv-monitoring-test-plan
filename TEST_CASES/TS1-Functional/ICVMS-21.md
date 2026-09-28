# ICVMS-21

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-21 | TC-VID-003 \| Processing FPS = 25 configurable | Camera streaming at 25 FPS. System running. | Action: Set processing_fps = 25Test Data: {"processing_fps": 25}Expected: Configuration accepted.Action: Monitor frame processing rate for 30 secondsExpected: ~25 frames processed per second (±2). | System processes ~25 FPS matching camera output. | High | To Do |
