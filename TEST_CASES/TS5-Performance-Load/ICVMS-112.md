# ICVMS-112

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-112 | TC-PERF-002 \| Baseline: single camera end-to-end event latency | Single camera. Model deployed. Timer available. | Action: Trigger a business event (e.g. person enters zone)Expected: Event condition met.Action: Record timestamp at: frame captured, inference complete, event generated, event stored in DB, event visible in APIExpected: All timestamps captured.Action: Calculate end-to-end latency: frame capture → API-visible eventExpected: Total latency = T_api - T_frame_capture.Action: Repeat 20 times and calculate averageExpected: Average end-to-end latency documented as baseline. | End-to-end event latency baseline measured and documented. Used as reference for scale tests. | High | To Do |
