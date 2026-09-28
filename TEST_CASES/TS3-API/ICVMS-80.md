# ICVMS-80

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-80 | TC-API-017 \| POST /cameras — missing required field returns 400 | Admin logged in. System running. | Action: POST /api/v1/cameras without rtsp_url fieldTest Data: {"name":"Cam","area":"AREA-A","fps":25}Expected: HTTP 400 Bad Request.Action: Check error bodyExpected: Field-level error: rtsp_url is required.Action: POST without name fieldExpected: HTTP 400. name is required.Action: POST with fps = 'fast' (wrong type)Expected: HTTP 400. fps must be integer. | HTTP 400 for missing or invalid fields. Field name specified in error. | High | To Do |
