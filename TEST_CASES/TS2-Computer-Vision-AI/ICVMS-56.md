# ICVMS-56

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-56 | TC-DET-014 \| Bounding box format correct xyxy consistent | Model deployed. Inference running. | Action: Run inference on test imageTest Data: Any image with detectionsExpected: Detections returned.Action: Inspect bounding box format for each detectionExpected: Every bbox = [x1, y1, x2, y2] integers.Action: Verify no detection uses xywh formatExpected: No width/height format mixed in. Format consistent across all cameras. | All bounding boxes use xyxy format consistently. No format mixing. | Highest | To Do |
