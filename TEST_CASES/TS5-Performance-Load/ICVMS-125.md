# ICVMS-125

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-125 | TC-STR-003 \| Stress test — 120 cameras confirm graceful behavior | System running. Scaling test environment available. | Action: Ramp to 120 cameras (50% above max)Expected: System heavily stressed.Action: Observe failure behaviorExpected: System fails or severely degrades.Action: Verify failure is graceful: logs error, does not corrupt data, does not take down infrastructureExpected: Graceful failure confirmed.Action: Remove excess load (back to 80)Expected: System recovers within defined RTO.Action: Verify all 80 cameras resume normallyExpected: All 80 cameras back to normal operation. | Graceful failure at 120 cameras. No data corruption. Full recovery confirmed on return to normal load. | High | To Do |
