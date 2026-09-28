# ICVMS-116

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-116 | TC-SCL-002 \| Scale test — 5 cameras: all metrics measured | 5 cameras connected. Model deployed. Monitoring active. | Action: Run system with 5 cameras for 10 minutesExpected: All 5 cameras processing.Action: Record: Inference FPS per camera, GPU%, VRAM, CPU%, RAM, Dropped frames, Event lossTest Data: Every 2 minutesExpected: All metrics captured.Action: Compare vs 1-camera baselineExpected: Note degradation percentage.Action: Verify pass criteria: FPS >= target, Event loss = 0, No crashesExpected: All pass criteria met. | 5-camera test passed. Metrics recorded. Degradation vs baseline noted. | High | To Do |
