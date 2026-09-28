# ICVMS-124

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-124 | TC-STR-002 \| Stress test — 100 cameras find failure point | System running. Scaling test environment available. | Action: Ramp to 100 camerasExpected: System under stress.Action: Find the point where first failure occursTest Data: Monitor until FPS = 0 or crash or OOMExpected: Failure point identified and documented.Action: Document failure behaviorExpected: Error type, resource state at failure, camera count at failure.Action: Verify no data corruption on failureTest Data: Check DB integrity after failureExpected: Database intact. No corrupted records. | Failure point documented. Failure is graceful (no data corruption). Exact camera count at failure recorded. | High | To Do |
