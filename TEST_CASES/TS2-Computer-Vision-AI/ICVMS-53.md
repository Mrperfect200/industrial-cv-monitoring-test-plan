# ICVMS-53

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-53 | TC-DET-007 \| Person detection — small object far distance | Test dataset with persons at far distance (>10m from camera) available. | Action: Run inference on far-distance imagesTest Data: Small person bounding boxes (<50px height)Expected: System attempts detection.Action: Calculate Recall for small objectsExpected: Recall meets project target for far objects.Action: Check minimum detectable object sizeExpected: Document minimum pixel height for reliable detection. | Small object detection meets project target. Minimum detectable size documented. | High | To Do |
