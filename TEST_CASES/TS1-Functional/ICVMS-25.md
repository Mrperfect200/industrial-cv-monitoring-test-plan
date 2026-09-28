# ICVMS-25

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-25 | TC-LINE-002 \| Line crossing generates LINE_CROSSED event | Virtual line LINE-01 configured on CAM-001. Object tracking active. | Action: Object (person) moves toward the line in the videoTest Data: Use test video with person crossing lineExpected: Object tracked with Track ID.Action: Object centroid crosses LINE-01Expected: LINE_CROSSED event generated immediately.Action: Check event schemaExpected: event contains: camera_id, line_id, track_id, direction, timestamp. | LINE_CROSSED event generated with complete schema on crossing. | Highest | To Do |
