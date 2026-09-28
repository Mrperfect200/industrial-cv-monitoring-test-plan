# ICVMS-68

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-68 | TC-ZONE-CV-001 \| ZONE_ENTER fires when centroid enters polygon | Polygon zone ZONE-01 active on CAM-001. Tracking active. | Action: Play test video: person's centroid crosses into ZONE-01 polygonExpected: Person tracked.Action: Check event log immediately after crossingExpected: ZONE_ENTER event generated.Action: Verify event fieldsExpected: zone_id=ZONE-01, track_id correct, timestamp present, camera_id=CAM-001. | ZONE_ENTER event fires when centroid enters polygon. Schema complete. | Highest | To Do |
