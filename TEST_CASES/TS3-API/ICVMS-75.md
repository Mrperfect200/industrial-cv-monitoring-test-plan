# ICVMS-75

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-75 | TC-API-009 \| Any endpoint — invalid token returns 401 | System running. | Action: Craft a malformed JWT token (modify payload bytes)Test Data: eyJhbGciOiJIUzI1NiJ9.INVALID.signatureExpected: Send as Bearer token.Action: Send GET /api/v1/cameras with malformed tokenExpected: HTTP 401 Unauthorized.Action: Try with a token signed by a different secretExpected: HTTP 401. Signature verification fails. | Malformed or mis-signed JWT always returns 401. | Highest | To Do |
