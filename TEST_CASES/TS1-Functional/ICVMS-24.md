# ICVMS-24

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-24 | TC-ZONE-003 \| Zone persists after system restart | Zone ZONE-01 exists on CAM-001. System running. | Action: Restart the vision serviceExpected: Service restarts successfully.Action: Send GET /api/v1/zones/ZONE-01Expected: HTTP 200. Zone still exists with same polygon.Action: Verify zone is active in inference engineTest Data: Check processing logsExpected: Zone events still being generated post-restart. | Zone persists after service restart. Configuration not lost. | High | To Do |
