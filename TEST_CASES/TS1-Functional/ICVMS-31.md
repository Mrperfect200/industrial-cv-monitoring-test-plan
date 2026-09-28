# ICVMS-31

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-31 | TC-QUE-001 \| Queue count correct | Queue zone configured on CAM-001. System running. | Action: 8 people standing in queue zoneTest Data: Use test videoExpected: System counts objects in queue zone.Action: Check queue count metricTest Data: GET /api/v1/zones/{id}/queueExpected: count = 8. | Queue count = actual number of people in queue zone. | High | To Do |
