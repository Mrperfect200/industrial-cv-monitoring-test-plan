# ICVMS-99

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-99 | TC-SEC-012 \| SQL injection in login username field blocked | Login endpoint available. Burp Suite or manual test ready. | Action: Send POST /api/v1/auth/login with SQL injection in usernameTest Data: {"email":"admin@x.com' OR 1=1 --","password":"x"}Expected: HTTP 401 Unauthorized. No SQL error in response.Action: Check server logs for SQL errorExpected: No database error logged.Action: Verify no data returned from DB bypassExpected: Response identical to normal failed login. | SQL injection in login field blocked. No DB error. No bypass possible. | Highest | To Do |
