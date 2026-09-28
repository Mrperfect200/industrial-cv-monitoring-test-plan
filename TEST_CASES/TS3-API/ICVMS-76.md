# ICVMS-76

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-76 | TC-API-010 \| Any endpoint — expired token returns 401 | System running. A JWT token with past exp timestamp available. | Action: Send GET /api/v1/cameras with expired tokenTest Data: exp = past timestampExpected: HTTP 401 Unauthorized.Action: Check error messageExpected: Indicates token expired (not just invalid).Action: Attempt token refresh with valid refresh_tokenTest Data: POST /api/v1/auth/refreshExpected: HTTP 200. New access_token returned. | Expired token returns 401. Refresh endpoint issues new token correctly. | Highest | To Do |
