# ICVMS-62

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-62 | TC-TRK-002 \| Track ID unique per individual person | Tracking enabled. Two persons in camera view simultaneously. | Action: Play test video with 2 persons visible simultaneouslyExpected: Both detected.Action: Check Track IDs assignedExpected: Person A = ID 1001, Person B = ID 1002. Different IDs.Action: Verify IDs do not swap during trackingTest Data: Monitor over 30 secondsExpected: Each person retains their own ID. | Unique Track ID per person. IDs do not swap between persons. | Highest | To Do |
