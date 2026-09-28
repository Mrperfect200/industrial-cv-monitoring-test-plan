# ICVMS-114

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-114 | TC-PERF-005 \| Baseline: API response time GET /events | System running. API deployed. Admin token available. | Action: Send 50 GET /api/v1/events requests sequentiallyTest Data: Use curl or Postman runnerExpected: All return HTTP 200.Action: Record response time for each requestExpected: Times recorded.Action: Calculate average, min, max, p95 response timeExpected: API response baseline documented.Action: Send 50 GET /api/v1/cameras requestsExpected: Baseline for cameras endpoint documented. | API response time baseline documented for key endpoints before load testing. | High | To Do |
