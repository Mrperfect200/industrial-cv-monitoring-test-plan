# ICVMS-119

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-119 | TC-SCL-005 \| Scale test — 40 cameras: all metrics measured | 40 cameras connected. Model deployed. Monitoring active. | Action: Run system with 40 cameras for 20 minutesExpected: All 40 processing.Action: Record all metrics every 5 minutesExpected: All values documented.Action: Monitor for queue depth growthExpected: Queue depth stable, not growing.Action: Verify pass criteriaExpected: FPS >= target, Event loss = 0, No OOM, No crashes. | 40-camera test passed. Queue depth stable. Metrics documented. | High | To Do |
