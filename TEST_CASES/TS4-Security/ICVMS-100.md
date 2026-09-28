# ICVMS-100

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-100 | TC-SEC-013 \| SQL injection in event query filter blocked | Events endpoint available. Database connected. | Action: GET /api/v1/events?camera_id=1'; DROP TABLE events;--Expected: HTTP 400 or 200 with empty/normal results.Action: Verify events table still existsTest Data: SELECT COUNT(*) FROM events;Expected: Table intact. No data lost.Action: Try UNION-based injectionTest Data: ?camera_id=1 UNION SELECT username,password FROM users--Expected: HTTP 400 or no sensitive data returned. | SQL injection in query parameters blocked. Database unaffected. | Highest | To Do |
