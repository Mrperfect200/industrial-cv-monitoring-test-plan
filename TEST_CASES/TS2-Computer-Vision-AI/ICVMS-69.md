# ICVMS-69

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-69 | TC-ZONE-CV-002 \| ZONE_EXIT fires when centroid leaves polygon | Polygon zone ZONE-01 active. Person already inside zone. | Action: Play test video: person's centroid crosses out of ZONE-01 polygonExpected: Person tracked.Action: Check event log immediately after exitExpected: ZONE_EXIT event generated.Action: Verify event fieldsExpected: zone_id, track_id, timestamp, camera_id all present. | ZONE_EXIT event fires when centroid leaves polygon. Schema complete. | Highest | To Do |
