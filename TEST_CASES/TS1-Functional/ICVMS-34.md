# ICVMS-34

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-34 | TC-DWL-003 \| LONG_DWELL alert fires at threshold | Zone ZONE-01 active. Dwell threshold = 300 seconds. | Action: Person enters zone. Dwell threshold = 300s.Expected: Enter timestamp recorded.Action: Wait 301 seconds (person still in zone)Expected: LONG_DWELL event generated.Action: Check event fieldsExpected: event contains track_id, zone_id, dwell_duration=301s, threshold=300s. | LONG_DWELL event fires at 301s. Not before threshold. Contains full schema. | Highest | To Do |
