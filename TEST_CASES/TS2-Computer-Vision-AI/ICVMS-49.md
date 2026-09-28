# ICVMS-49

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-49 | TC-DET-002 \| Person detection — low light / night | Labeled night/low-light test dataset available. Model deployed. | Action: Run inference on 100 low-light test imagesTest Data: Night footage, dim indoor lightingExpected: Detections generated.Action: Calculate Precision and RecallExpected: Meet project-defined targets for low-light.Action: Compare vs normal lighting baselineExpected: Understand degradation under low light. | Precision and Recall meet project targets under low-light conditions. | High | To Do |
