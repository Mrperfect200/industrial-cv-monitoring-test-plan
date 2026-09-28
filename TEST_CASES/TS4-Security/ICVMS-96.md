# ICVMS-96

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-96 | TC-SEC-007 \| Viewer cannot access admin-only endpoints → 403 | Viewer account available. Admin-only endpoint identified. | Action: Login as ViewerExpected: Token received.Action: GET /api/v1/users (admin-only)Test Data: Authorization: Bearer <viewer_token>Expected: HTTP 403 Forbidden.Action: POST /api/v1/camerasExpected: HTTP 403 Forbidden.Action: DELETE /api/v1/cameras/{id}Expected: HTTP 403 Forbidden.Action: GET /api/v1/cameras (read-only allowed)Expected: HTTP 200. Read access permitted. | Viewer blocked from all write/admin operations. Read-only access permitted. | Highest | To Do |
