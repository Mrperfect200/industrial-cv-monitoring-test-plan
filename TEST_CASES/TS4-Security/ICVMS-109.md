# ICVMS-109

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-109 | TC-SEC-029 \| Login attempts (success+fail) in audit log | Audit logging enabled. Admin account available. | Action: Perform successful login as AdminExpected: Login succeeds.Action: Check audit log for login entryTest Data: SELECT * FROM audit_logs WHERE action='LOGIN' ORDER BY timestamp DESC LIMIT 1;Expected: Entry exists: user_id, action=LOGIN, timestamp, ip_address.Action: Perform failed login attemptExpected: Login fails.Action: Check audit log for failed loginExpected: Entry exists: action=LOGIN_FAILED, timestamp, ip_address. | Both successful and failed logins recorded in audit log with timestamp and IP. | High | To Do |
