# ICVMS-38

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-38 | TC-ALT-001 \| Dashboard notification on critical event | Alert rule configured: OVER_OCCUPANCY → Dashboard notification. System running. | Action: Trigger OVER_OCCUPANCY eventTest Data: Simulate occupancy > thresholdExpected: Event generated.Action: Check dashboard notifications panelExpected: Notification appears within configured alert latency.Action: Check notification contentExpected: Contains: zone_id, count, threshold, timestamp. | Dashboard notification appears with correct content on OVER_OCCUPANCY. | High | To Do |
