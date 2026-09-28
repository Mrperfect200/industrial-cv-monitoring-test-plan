# ICVMS-90

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-90 | TC-API-044 \| Error responses have consistent JSON schema | System running. | Action: Send POST /api/v1/cameras with missing field to trigger 400Expected: HTTP 400.Action: Inspect error response body schemaExpected: Contains: error, message, field (or errors array).Action: Trigger 401 (no token)Expected: Error response same schema.Action: Trigger 403 (wrong role)Expected: Error response same schema.Action: Trigger 404 (not found)Expected: Error response same schema. | All error responses (400/401/403/404/429) use same consistent JSON schema. | High | To Do |
