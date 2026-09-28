# ICVMS-110

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-110 | TC-SEC-030 \| Camera create/delete changes recorded in audit log | Audit logging enabled. Admin account available. | Action: Create a new camera as AdminExpected: Camera created.Action: Check audit logTest Data: SELECT * FROM audit_logs WHERE action='CAMERA_CREATED' ORDER BY timestamp DESC LIMIT 1;Expected: Entry: user_id, action=CAMERA_CREATED, camera_id, timestamp.Action: Delete a camera as AdminExpected: Camera deleted.Action: Check audit logExpected: Entry: action=CAMERA_DELETED, camera_id, user_id, timestamp. | Camera create and delete operations recorded in audit log with full context. | High | To Do |
