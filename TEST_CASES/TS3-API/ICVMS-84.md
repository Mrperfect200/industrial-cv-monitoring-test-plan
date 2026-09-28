# ICVMS-84

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-84 | TC-API-022 \| GET /events?camera_id — filters by camera correctly | Events exist for CAM-001 and CAM-002. Admin logged in. | Action: GET /api/v1/events?camera_id=CAM-001Expected: HTTP 200.Action: Verify all events in response have camera_id = CAM-001Expected: No CAM-002 events in response.Action: GET /api/v1/events?camera_id=CAM-999 (non-existent)Expected: HTTP 200. Empty array. | Filter by camera_id returns only matching events. Empty array for no matches. | High | To Do |
