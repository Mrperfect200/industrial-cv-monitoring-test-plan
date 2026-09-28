# ICVMS-22

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-22 | TC-VID-005 \| Frame skipping reduces GPU load | Camera streaming. System running at 5 FPS. | Action: Update processing_fps = 25 via APITest Data: PUT /api/v1/cameras/{id}/configExpected: Configuration accepted. HTTP 200.Action: Monitor FPS within 5 secondsExpected: New FPS applied without service restart. | FPS change applies within 5 seconds. No restart required. | High | To Do |
