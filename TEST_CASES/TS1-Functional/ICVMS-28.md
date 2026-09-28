# ICVMS-28

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-28 | TC-OCC-001 \| Occupancy increments on ZONE_ENTER | Zone ZONE-01 active on CAM-001. Current occupancy = 3. | Action: Person enters ZONE-01 (centroid crosses polygon boundary)Test Data: Use test videoExpected: ZONE_ENTER event generated.Action: Check occupancy countTest Data: GET /api/v1/zones/ZONE-01/occupancyExpected: Current occupancy = 4. | Occupancy increments by 1 on each ZONE_ENTER event. | High | To Do |
