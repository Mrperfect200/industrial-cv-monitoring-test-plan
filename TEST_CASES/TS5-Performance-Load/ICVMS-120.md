# ICVMS-120

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-120 | TC-SCL-006 \| Scale test — 60 cameras: all metrics measured | 60 cameras connected. Model deployed. Monitoring active. | Action: Run system with 60 cameras for 20 minutesExpected: All 60 processing.Action: Record all metrics every 5 minutesExpected: All values documented.Action: Check GPU and VRAM headroom remainingExpected: Headroom > 20% of capacity.Action: Verify pass criteriaExpected: FPS >= target, Event loss = 0, No crashes. | 60-camera test passed. Sufficient headroom confirmed. Metrics documented. | High | To Do |
