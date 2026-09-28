# ICVMS-83

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-83 | TC-API-021 \| GET /events — returns paginated event list | System running with events in database. Admin logged in. | Action: GET /api/v1/eventsExpected: HTTP 200. Paginated list of events returned.Action: Check response schemaExpected: Array of events. Each has event_id, type, camera_id, timestamp, severity.Action: Check pagination metadataExpected: Response includes total, page, limit fields. | Events list returns paginated results with correct schema. | High | To Do |
