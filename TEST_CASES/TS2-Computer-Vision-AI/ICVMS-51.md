# ICVMS-51

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-51 | TC-DET-004 \| Person detection — partial occlusion 30-50% | Test dataset with partial occlusion (30-50%) available. Model deployed. | Action: Run inference on partially occluded person imagesTest Data: Person 30-50% behind objectExpected: Detections generated.Action: Calculate Recall specificallyExpected: Recall meets project target for partial occlusion.Action: Document missed detectionsExpected: False negatives categorized by occlusion level. | Recall meets project target for partial occlusion scenario. | High | To Do |
