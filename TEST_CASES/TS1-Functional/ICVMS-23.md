# ICVMS-23

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-23 | TC-ZONE-001 \| Create polygon zone on camera | Admin logged in. Camera CAM-001 exists in system. | Action: Send POST /api/v1/zones with polygon coordinates for CAM-001Test Data: {"camera_id":"CAM-001","type":"PRODUCTION","polygon":[[100,100],[400,100],[400,400],[100,400]]}Expected: HTTP 201 Created. zone_id returned.Action: Send GET /api/v1/zones/{zone_id}Expected: Zone returned with correct camera_id and polygon. | Zone created, linked to correct camera, polygon stored correctly. | High | To Do |
