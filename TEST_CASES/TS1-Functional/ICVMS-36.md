# ICVMS-36

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-36 | TC-EVT-002 \| Event ID is unique across all events | System running under normal load. | Action: Generate 100 events of any typeTest Data: Trigger various business conditionsExpected: All 100 events created.Action: Query all events and check event_id uniquenessTest Data: GET /api/v1/events?limit=100Expected: All 100 event_ids are unique. No duplicates. | All event_ids unique across 100 generated events. | Highest | To Do |
