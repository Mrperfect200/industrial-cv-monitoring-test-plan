# ICVMS-79

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-79 | TC-API-016 \| POST /cameras — Viewer gets 403 Forbidden | Viewer account available. System running. | Action: Login as Viewer. Get JWT token.Expected: Token received.Action: POST /api/v1/cameras with valid payload using Viewer tokenExpected: HTTP 403 Forbidden.Action: Check response bodyExpected: Error indicates insufficient permissions.Action: Verify no camera was createdTest Data: GET /api/v1/camerasExpected: New camera not in list. | Viewer cannot create cameras. HTTP 403. No side effects. | Highest | To Do |
