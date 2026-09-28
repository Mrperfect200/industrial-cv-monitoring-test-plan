# ICVMS-10

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-10 | TC-CAM-003 \| Add camera with missing required fields → 400 | Admin logged in. System running. | Action: Send POST /api/v1/cameras without rtsp_url fieldTest Data: {"name":"Cam2","area":"AREA-A","fps":25}Expected: HTTP 400 Bad Request.Action: Check error response contains field-level detailExpected: Response body identifies rtsp_url as missing/required.Action: Send POST without name fieldTest Data: {"rtsp_url":"rtsp://x/y","area":"AREA-A"}Expected: HTTP 400. name identified as missing. | HTTP 400 for each missing required field. Field name specified in error response. | High | To Do |
