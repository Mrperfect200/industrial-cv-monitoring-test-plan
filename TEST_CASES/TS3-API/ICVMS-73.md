# ICVMS-73

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-73 | TC-API-003 \| POST /auth/login — no user enumeration on invalid user | System running. | Action: POST /api/v1/auth/login with non-existent emailTest Data: {"email":"nobody@fake.com","password":"anything"}Expected: HTTP 401 Unauthorized.Action: Compare response body with wrong-password responseExpected: Identical response. No hint that email doesn't exist.Action: Compare response time with valid-user wrong-passwordExpected: Response times similar. No timing oracle. | Non-existent user returns same 401 as wrong password. No user enumeration possible. | Highest | To Do |
