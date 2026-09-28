# ICVMS-50

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-50 | TC-DET-003 \| Person detection — strong backlight | Test dataset with backlit scenes available. Model deployed. | Action: Run inference on backlit imagesTest Data: Window behind subject, strong backlightExpected: Detections generated.Action: Calculate Precision and RecallExpected: Meet project-defined targets.Action: Inspect false negatives visuallyExpected: Identify failure patterns for improvement. | Detection meets targets under backlight. False negatives documented. | High | To Do |
