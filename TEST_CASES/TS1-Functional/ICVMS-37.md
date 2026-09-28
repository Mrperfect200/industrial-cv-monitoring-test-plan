# ICVMS-37

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-37 | TC-EVT-003 \| Event persisted to database | System running. Database connected. | Action: Trigger a ZONE_ENTER eventExpected: Event generated.Action: Query database directly for the eventTest Data: SELECT * FROM events WHERE event_id = '...'Expected: Record exists in DB with correct fields. | Every generated event is persisted to the database. | High | To Do |
