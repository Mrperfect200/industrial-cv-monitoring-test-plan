# ICVMS-82

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-82 | TC-API-020 \| DELETE /cameras/{id} — Operator gets 403 | Operator account available. Camera CAM-010 exists. | Action: Login as OperatorExpected: Token received.Action: DELETE /api/v1/cameras/CAM-010 using Operator tokenExpected: HTTP 403 Forbidden.Action: Verify CAM-010 still existsTest Data: GET /api/v1/cameras/CAM-010Expected: HTTP 200. Camera intact. | Operator cannot delete cameras. HTTP 403. Camera unaffected. | Highest | To Do |
