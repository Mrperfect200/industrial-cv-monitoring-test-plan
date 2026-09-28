# ICVMS-89

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-89 | TC-API-041 \| Rate limiting returns 429 on exceed | Rate limiting configured (e.g. 100 requests/minute). System running. | Action: Send 101 requests to GET /api/v1/events in under 60 secondsTest Data: Use loop or k6 scriptExpected: First 100 succeed with HTTP 200.Action: Check 101st requestExpected: HTTP 429 Too Many Requests.Action: Check response headersExpected: X-RateLimit-Limit and X-RateLimit-Remaining present. | HTTP 429 after rate limit exceeded. Rate limit headers present on responses. | High | To Do |
