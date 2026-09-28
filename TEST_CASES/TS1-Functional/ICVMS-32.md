# ICVMS-32

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-32 | TC-QUE-002 \| QUEUE_THRESHOLD event fires on exceed | Queue zone configured. threshold = 5. | Action: Simulate 6 people in queue zoneExpected: Count = 6 > threshold = 5.Action: Check event logExpected: QUEUE_THRESHOLD event generated with count=6, threshold=5. | QUEUE_THRESHOLD event fires when queue count exceeds configured threshold. | High | To Do |
