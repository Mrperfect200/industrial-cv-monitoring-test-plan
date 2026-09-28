# ICVMS-92

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-92 | TC-SEC-002 \| JWT signed with strong algorithm RS256/HS256 | System running. Valid credentials available. | Action: Login and receive JWT tokenExpected: Token received.Action: Decode JWT header using base64Test Data: echo '<header>' \| base64 -dExpected: alg = RS256 or HS256.Action: Verify token contains exp claimExpected: exp claim present with future timestamp.Action: Verify token contains iat and sub claimsExpected: Both present. | JWT uses strong algorithm. Contains required claims (exp, iat, sub). | Highest | To Do |
