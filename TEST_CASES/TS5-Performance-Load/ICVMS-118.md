# ICVMS-118

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-118 | TC-SCL-004 \| Scale test — 20 cameras: all metrics measured | 20 cameras connected. Model deployed. Monitoring active. | Action: Run system with 20 cameras for 15 minutesExpected: All 20 processing.Action: Record all metrics every 3 minutesExpected: All values documented.Action: Check for first signs of resource pressureExpected: Note if GPU% > 70% or VRAM > 80%.Action: Verify pass criteriaExpected: FPS >= target, Event loss = 0, No crashes. | 20-camera test passed. Resource pressure points identified and documented. | High | To Do |
