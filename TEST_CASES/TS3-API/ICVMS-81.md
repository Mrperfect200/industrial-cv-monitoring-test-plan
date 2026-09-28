# ICVMS-81

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-81 | TC-API-019 \| DELETE /cameras/{id} — Admin succeeds 204 | Admin logged in. Camera CAM-010 exists. | Action: DELETE /api/v1/cameras/CAM-010Expected: HTTP 200 or 204.Action: GET /api/v1/cameras/CAM-010Expected: HTTP 404 Not Found.Action: Check camera not in listTest Data: GET /api/v1/camerasExpected: CAM-010 absent from list. | Camera deleted. 404 on subsequent fetch. Removed from list. | High | To Do |
