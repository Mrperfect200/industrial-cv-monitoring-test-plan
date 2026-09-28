# ICVMS-97

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-97 | TC-SEC-008 \| IDOR — access another user data blocked → 403 | Two regular user accounts: User A (ID=101) and User B (ID=102). Both logged in separately. | Action: Login as User B. Get token.Expected: Token for User B received.Action: GET /api/v1/users/101 using User B tokenExpected: HTTP 403 Forbidden or 404.Action: PUT /api/v1/users/101 using User B tokenTest Data: {"role":"Admin"}Expected: HTTP 403 Forbidden.Action: Verify User A data unchangedTest Data: Login as User A and check profileExpected: User A data intact. | User B cannot access or modify User A data. IDOR protection working. | Highest | To Do |
