# ICVMS-35

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-35 | TC-EVT-001 \| Event schema complete — all required fields present | System running. Any event trigger active. | Action: Trigger any business event (e.g. OVER_OCCUPANCY)Expected: Event generated and stored.Action: GET /api/v1/events/{event_id}Expected: Response contains all required fields.Action: Verify schema completenessExpected: event_id, type, camera_id, area_id, zone_id, timestamp, severity, status all present. | Every event contains complete schema. No required field missing. | Highest | To Do |
