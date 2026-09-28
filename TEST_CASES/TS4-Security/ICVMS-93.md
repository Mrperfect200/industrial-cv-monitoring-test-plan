# ICVMS-93

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-93 | TC-SEC-003 \| JWT expiry enforced — expired token rejected | System running. JWT token with past expiry available (or wait for token to expire). | Action: Obtain valid JWT tokenExpected: Token received with exp timestamp.Action: Wait for token to expire (or craft expired token)Expected: Token past exp time.Action: Send GET /api/v1/cameras with expired tokenExpected: HTTP 401 Unauthorized.Action: Check error messageExpected: Response indicates token expired. | Expired JWT returns 401. System does not accept tokens past expiry. | Highest | To Do |
