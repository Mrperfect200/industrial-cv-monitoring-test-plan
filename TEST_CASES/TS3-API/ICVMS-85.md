# ICVMS-85

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-85 | TC-API-024 \| GET /events?from&to — filters by time range correctly | Events exist across multiple dates. Admin logged in. | Action: GET /api/v1/events?from=2026-09-01T00:00:00Z&to=2026-09-01T23:59:59ZExpected: HTTP 200.Action: Verify all returned events are within date rangeExpected: No events outside range.Action: GET /api/v1/events?from=T2&to=T1 (invalid range)Expected: HTTP 400 Bad Request. | Time range filter returns only events in range. Invalid range returns 400. | High | To Do |
