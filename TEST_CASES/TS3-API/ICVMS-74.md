# ICVMS-74

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-74 | TC-API-008 \| Any endpoint — no token returns 401 | System running. | Action: Send request to GET /api/v1/cameras with no Authorization headerExpected: HTTP 401 Unauthorized.Action: Send request with Authorization header emptyTest Data: Authorization: Bearer Expected: HTTP 401.Action: Verify response bodyExpected: Error: missing or invalid token. | HTTP 401 on all requests without valid token. | Highest | To Do |
