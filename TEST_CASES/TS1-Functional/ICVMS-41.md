# ICVMS-41

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-41 | TC-USR-003 \| Viewer cannot delete camera → 403 | Viewer account credentials available. Camera CAM-001 exists. | Action: Login as Viewer userExpected: Login successful.Action: Send DELETE /api/v1/cameras/CAM-001 using Viewer tokenExpected: HTTP 403 Forbidden.Action: Verify CAM-001 still existsTest Data: GET /api/v1/cameras/CAM-001Expected: HTTP 200. Camera intact. | Viewer cannot delete cameras. HTTP 403. Camera unaffected. | Highest | To Do |
