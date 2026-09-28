# ICVMS-30

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-30 | TC-OCC-008 \| Occupancy threshold configurable via API | Admin logged in. Zone ZONE-01 exists. | Action: Set zone threshold = 20 via APITest Data: PUT /api/v1/zones/ZONE-01 with {threshold: 20}Expected: HTTP 200. Threshold saved.Action: Simulate occupancy reaching 20Expected: No OVER_OCCUPANCY event.Action: Simulate occupancy reaching 21Expected: OVER_OCCUPANCY event fires.Action: Change threshold to 10 via APIExpected: New threshold applied. Event fires at 11 not 21. | Threshold configurable via API. Takes effect without restart. | High | To Do |
