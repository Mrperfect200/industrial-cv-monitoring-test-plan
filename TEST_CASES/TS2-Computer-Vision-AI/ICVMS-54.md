# ICVMS-54

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-54 | TC-DET-008 \| Person detection — motion blur | Test dataset with motion blur (fast-moving persons) available. | Action: Run inference on motion-blurred framesTest Data: Person moving fast, blurred frameExpected: System attempts detection.Action: Calculate RecallExpected: Meets project target for motion blur.Action: Inspect false negativesExpected: Identify blur threshold causing failures. | Recall meets project target under motion blur. Failure threshold documented. | High | To Do |
