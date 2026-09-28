# ICVMS-29

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-29 | TC-OCC-004 \| OVER_OCCUPANCY event fires at threshold | Zone ZONE-01 active. threshold = 20. Current occupancy = 19. | Action: One more person enters the zone (occupancy becomes 20)Expected: No alert yet — at threshold not over.Action: Another person enters (occupancy = 21)Expected: OVER_OCCUPANCY event generated.Action: Check event fieldsExpected: event contains zone_id, count=21, threshold=20, timestamp. | OVER_OCCUPANCY event fires only when count exceeds threshold. Not at threshold. | Highest | To Do |
