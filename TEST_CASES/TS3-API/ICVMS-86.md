# ICVMS-86

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-86 | TC-API-025 \| GET /events — pagination returns correct page | 50+ events exist in database. Admin logged in. | Action: GET /api/v1/events?page=1&limit=10Expected: HTTP 200. Returns 10 events. page=1.Action: GET /api/v1/events?page=2&limit=10Expected: Returns next 10 events. No duplicates from page 1.Action: GET /api/v1/events?page=999&limit=10 (beyond last page)Expected: HTTP 200. Empty array or last page. | Pagination returns correct pages. No duplicates across pages. | High | To Do |
