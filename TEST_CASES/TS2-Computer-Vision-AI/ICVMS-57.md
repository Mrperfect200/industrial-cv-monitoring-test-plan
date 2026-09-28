# ICVMS-57

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-57 | TC-DET-015 \| Detection includes all required output fields | Model deployed. Inference running. | Action: Run inference on test frameExpected: Detections returned.Action: Inspect each detection object schemaExpected: class, confidence, bbox, camera_id, timestamp all present.Action: Verify no required field is null or missingExpected: All fields populated for every detection. | Every detection contains all required fields. No missing or null values. | Highest | To Do |
