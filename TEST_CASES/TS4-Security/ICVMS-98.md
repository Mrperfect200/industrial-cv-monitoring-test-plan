# ICVMS-98

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-98 | TC-SEC-010 \| Privilege escalation via PUT /users blocked → 403 | Operator account available. System running. | Action: Login as OperatorExpected: Token received.Action: PUT /api/v1/users/{own_id} with role=AdminTest Data: {"role":"Admin"}Expected: HTTP 403 Forbidden.Action: Verify Operator role unchangedTest Data: GET /api/v1/users/{own_id} as AdminExpected: Role still = Operator.Action: Try setting role=SupervisorExpected: HTTP 403 Forbidden. | Operators cannot escalate their own privileges. Role change blocked. | Highest | To Do |
