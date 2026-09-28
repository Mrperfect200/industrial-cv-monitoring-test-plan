# ICVMS-42

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-42 | TC-USR-007 \| Non-admin cannot create users → 403 | Operator account credentials available. | Action: Login as OperatorExpected: Login successful.Action: Send POST /api/v1/users with new user payloadTest Data: {"email":"new@test.com","role":"Viewer"}Expected: HTTP 403 Forbidden.Action: Verify no user was createdTest Data: GET /api/v1/users (as Admin)Expected: New user not in list. | Operator cannot create users. HTTP 403. No user created. | Highest | To Do |
