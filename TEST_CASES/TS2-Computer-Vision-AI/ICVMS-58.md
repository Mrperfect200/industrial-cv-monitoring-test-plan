# ICVMS-58

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-58 | TC-DET-016 \| Confidence threshold respected per class | Model deployed. person confidence threshold set to 0.50 in config. | Action: Run inference on test datasetExpected: Detections returned.Action: Filter detections with confidence < 0.50Expected: Zero detections below threshold in output.Action: Verify threshold read from config not hardcodedTest Data: grep -r '0.50' src/Expected: Threshold value only in config file, not in source code. | No detections returned below configured threshold. Threshold read from config. | High | To Do |
