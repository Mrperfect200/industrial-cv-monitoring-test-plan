# ICVMS-117

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-117 | TC-SCL-003 \| Scale test — 10 cameras: all metrics measured | 10 cameras connected. Model deployed. Monitoring active. | Action: Run system with 10 cameras for 10 minutesExpected: All 10 processing.Action: Record all metricsTest Data: FPS, GPU%, VRAM, CPU%, RAM, dropped frames, event lossExpected: All values documented.Action: Compare vs 5-camera resultsExpected: Degradation trend observed.Action: Verify pass criteriaExpected: FPS >= target, Event loss = 0, No OOM, No crashes. | 10-camera test passed. Metrics recorded. Scaling trend documented. | High | To Do |
