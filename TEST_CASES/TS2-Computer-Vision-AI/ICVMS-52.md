# ICVMS-52

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-52 | TC-DET-006 \| Person detection — high density crowd | High-density crowd test dataset (10+ people per frame) available. | Action: Run inference on crowd scenesTest Data: 10-15 people in single frameExpected: All persons detected.Action: Calculate Precision and RecallExpected: Meet targets for high-density scenes.Action: Check for duplicate detections on same personExpected: No duplicate bounding boxes on single person. | Detection meets targets in high-density crowd scenes. No duplicate detections. | High | To Do |
