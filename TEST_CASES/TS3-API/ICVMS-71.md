# ICVMS-71

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-71 | TC-API-001 \| POST /auth/login — valid credentials returns 200 + JWT | System running. Valid admin credentials available. | Action: POST /api/v1/auth/login with valid email and passwordTest Data: {"email":"admin@factory.com","password":"ValidPass123"}Expected: HTTP 200. Response contains access_token and refresh_token.Action: Decode JWT token headerTest Data: Use jwt.ioExpected: Algorithm is RS256 or HS256. Token has exp claim.Action: Use access_token on GET /api/v1/camerasTest Data: Authorization: Bearer <token>Expected: HTTP 200. Cameras returned. | Login returns valid JWT. Token accepted on protected endpoints. | Highest | To Do |
