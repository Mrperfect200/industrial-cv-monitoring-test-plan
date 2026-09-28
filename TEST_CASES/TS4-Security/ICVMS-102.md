# ICVMS-102

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-102 | TC-SEC-017 \| API only accessible over HTTPS — HTTP rejected | API deployed with TLS certificate. HTTP port may be open. | Action: Send HTTP request to APITest Data: curl http://your-api/api/v1/camerasExpected: HTTP 301 redirect to HTTPS or connection refused.Action: Send HTTPS requestTest Data: curl https://your-api/api/v1/camerasExpected: HTTP 200 or 401. Responds correctly over HTTPS.Action: Verify no sensitive data over HTTPExpected: No API responses served over plain HTTP. | API accessible only over HTTPS. HTTP requests redirected or rejected. | Highest | To Do |
