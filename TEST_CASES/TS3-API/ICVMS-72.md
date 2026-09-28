# ICVMS-72

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-72 | TC-API-002 \| POST /auth/login — wrong password returns 401 | System running. User account exists. | Action: POST /api/v1/auth/login with correct email but wrong passwordTest Data: {"email":"admin@factory.com","password":"WrongPass"}Expected: HTTP 401 Unauthorized.Action: Check response bodyExpected: Error message does not reveal whether email exists.Action: Attempt 5 more times with wrong passwordExpected: Rate limiting or lockout applied after threshold. | HTTP 401 on wrong password. No user enumeration. Rate limiting active. | Highest | To Do |
