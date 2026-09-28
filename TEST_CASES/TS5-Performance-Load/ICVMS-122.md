# ICVMS-122

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-122 | TC-PERF-010 \| 80 cameras simultaneous events — zero event loss | 80 cameras running. Event generation active. | Action: Trigger simultaneous events on all 80 cameras at the same timeTest Data: Script that causes zone trigger on all cameras simultaneouslyExpected: Events generated from all cameras.Action: Check database for all eventsTest Data: COUNT events generated in last 10 secondsExpected: All 80+ events stored. Zero lost.Action: Check API response time during event burstTest Data: GET /api/v1/events during burstExpected: Response time within acceptable range.Action: Check DB write latency during burstExpected: No DB timeout or error. | Zero event loss during simultaneous 80-camera event burst. API and DB handle load. | Highest | To Do |
