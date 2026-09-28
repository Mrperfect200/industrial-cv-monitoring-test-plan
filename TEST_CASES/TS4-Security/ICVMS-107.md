# ICVMS-107

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-107 | TC-SEC-023 \| RTSP credentials absent from all API responses | Camera configured with RTSP credentials. Admin logged in. | Action: GET /api/v1/cameras/{id}Expected: HTTP 200.Action: Search response body for password/credential fieldsTest Data: Check JSON responseExpected: No rtsp_password, password, secret, credentials fields.Action: GET /api/v1/cameras (list)Expected: RTSP credentials absent from all camera objects in list.Action: Check camera creation response (POST)Expected: 201 response does not echo back RTSP password. | RTSP credentials never present in any API response body. | Highest | To Do |
