# ICVMS-61

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-61 | TC-TRK-001 \| Track ID persists across frames for same object | Tracking enabled. Single person walking through camera view. | Action: Play test video of single person walkingExpected: Person detected each frame.Action: Record Track ID assigned on first detectionExpected: Track ID = e.g. 1001.Action: Verify Track ID remains 1001 for all subsequent framesExpected: Same ID maintained throughout full track duration.Action: Verify Track ID removed when person exits frameExpected: No stale track after exit. | Single Track ID maintained for same person throughout entire track duration. | Highest | To Do |
