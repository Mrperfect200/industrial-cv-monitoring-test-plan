# ICVMS-95

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-95 | TC-SEC-005 \| Brute force protection — lockout after failed attempts | System running. Login endpoint available. | Action: Send 10 failed login attempts with wrong passwordTest Data: {"email":"admin@factory.com","password":"wrong"}Expected: First attempts return 401.Action: Send 20th failed attemptExpected: HTTP 429 or HTTP 401 with lockout message.Action: Wait for lockout period / unlock accountExpected: After lockout period, login succeeds with correct credentials. | Brute force protection active. Account locked or rate limited after repeated failures. | High | To Do |
