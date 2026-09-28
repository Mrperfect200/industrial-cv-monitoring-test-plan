# ICVMS-78

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-78 | TC-API-015 \| POST /cameras — Admin creates camera returns 201 | Admin logged in. System running. | Action: POST /api/v1/cameras with all required fieldsTest Data: {"name":"Line-5","area":"AREA-B","rtsp_url":"rtsp://10.0.0.5/stream","fps":25,"codec":"H264","resolution":"1920x1080"}Expected: HTTP 201 Created.Action: Check response bodyExpected: Contains camera_id (auto-generated), all submitted fields.Action: GET /api/v1/cameras/{camera_id}Expected: HTTP 200. Camera exists with correct fields. | Camera created successfully. 201 returned. Camera retrievable by ID. | High | To Do |
