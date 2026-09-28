# ICVMS-87

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-87 | TC-API-033 \| DELETE /zones/{id} — Viewer gets 403 | Viewer account available. Zone ZONE-01 exists. | Action: Login as ViewerExpected: Token received.Action: DELETE /api/v1/zones/ZONE-01 using Viewer tokenExpected: HTTP 403 Forbidden.Action: Verify ZONE-01 still existsTest Data: GET /api/v1/zones/ZONE-01Expected: HTTP 200. Zone intact. | Viewer cannot delete zones. HTTP 403. Zone unaffected. | Highest | To Do |
