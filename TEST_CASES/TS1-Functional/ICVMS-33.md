# ICVMS-33

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-33 | TC-DWL-002 \| Dwell time calculated correctly per track | Zone ZONE-01 active. Track ID 1001 enters zone. | Action: Person with Track ID 1001 enters zone at 10:00:00Expected: Enter timestamp recorded for Track 1001.Action: Person exits zone at 10:05:30Expected: Exit timestamp recorded.Action: Check dwell time calculationTest Data: GET /api/v1/events?track_id=1001&type=ZONE_EXITExpected: dwell_time = 5m 30s (330 seconds). | Dwell time = exit_time - enter_time. Calculated correctly per track_id. | High | To Do |
