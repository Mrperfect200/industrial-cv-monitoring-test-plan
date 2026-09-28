# ICVMS-39

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-39 | TC-ALT-004 \| Webhook alert delivers correct payload | Webhook alert configured with endpoint URL. System running. | Action: Trigger an alertable eventExpected: Event generated.Action: Check webhook endpoint received POST requestTest Data: Check webhook receiver logsExpected: POST received within configured latency.Action: Check webhook payload schemaExpected: Payload matches event JSON schema with all required fields. | Webhook receives correct event payload within configured latency. | High | To Do |
