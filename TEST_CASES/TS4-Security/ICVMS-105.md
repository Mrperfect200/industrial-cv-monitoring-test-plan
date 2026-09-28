# ICVMS-105

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-105 | TC-SEC-020 \| DB credentials not hardcoded in source code | Source code repository accessible. | Action: Search codebase for database password patternsTest Data: grep -riE 'DB_PASS\|db_password\|postgres.*password' src/Expected: Zero hardcoded values found.Action: Search for connection string with passwordTest Data: grep -rE 'postgresql://[^:]+:[^@]+@' src/Expected: Zero matches.Action: Verify DB credentials from environmentExpected: DB connection uses os.environ or config file outside repo. | No DB credentials hardcoded in source. All loaded from environment variables. | Highest | To Do |
