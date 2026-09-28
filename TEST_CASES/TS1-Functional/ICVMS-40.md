# ICVMS-40

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-40 | TC-USR-002 \| Viewer cannot add camera → 403 | Viewer account credentials available. System running. | Action: Login as Viewer userExpected: Login successful. JWT token received.Action: Send POST /api/v1/cameras with valid payload using Viewer tokenExpected: HTTP 403 Forbidden.Action: Verify no camera was createdTest Data: GET /api/v1/camerasExpected: No new camera in list. | Viewer cannot create cameras. HTTP 403 returned. No side effects. | Highest | To Do |
