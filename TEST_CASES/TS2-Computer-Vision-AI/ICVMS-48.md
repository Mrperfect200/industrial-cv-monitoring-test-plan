# ICVMS-48

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-48 | TC-DET-001 \| Person detection — normal indoor lighting | Labeled test dataset available. Model deployed. Camera with normal indoor lighting. | Action: Run inference on 100 test images with normal lightingTest Data: Dataset: indoor, 1080p, clearExpected: Detections generated for each image.Action: Calculate Precision and RecallTest Data: Using held-out labeled datasetExpected: Precision and Recall meet project-defined targets.Action: Calculate mAP@0.5Expected: mAP@0.5 >= project-defined threshold. | Person detection meets accuracy targets under normal indoor lighting. | High | To Do |
