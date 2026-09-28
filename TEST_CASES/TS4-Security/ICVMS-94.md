# ICVMS-94

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-94 | TC-SEC-004 \| JWT not accepted after logout | System running. Valid session available. | Action: Login and get JWT tokenExpected: Token received.Action: Use token on GET /api/v1/camerasExpected: HTTP 200. Works correctly.Action: POST /api/v1/auth/logoutTest Data: Authorization: Bearer <token>Expected: HTTP 200. Logout successful.Action: Use same token again on GET /api/v1/camerasExpected: HTTP 401. Token rejected after logout. | Token invalidated after logout. Reuse of logged-out token returns 401. | Highest | To Do |
