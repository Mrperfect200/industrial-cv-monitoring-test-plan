# ICVMS-88

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-88 | TC-API-040 \| API versioning /api/v1 prefix active on all endpoints | System running. API deployed. | Action: GET /api/v1/camerasExpected: HTTP 200. URL prefix is /api/v1/.Action: GET /api/cameras (without version)Expected: HTTP 404 or redirect to versioned URL.Action: Check all endpoints use /api/v1/ prefixTest Data: Inspect API documentationExpected: All endpoints versioned correctly. | All endpoints accessible only under /api/v1/. Unversioned paths return 404. | High | To Do |
