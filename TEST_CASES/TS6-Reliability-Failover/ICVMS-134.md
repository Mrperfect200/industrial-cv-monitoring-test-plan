# ICVMS-134

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-134 | TC-REL-011 \| Database unavailable 30 min → no data corruption | System running with 80 cameras. DB unavailable for 30 minutes. | Action: Stop database for 30 minutesTest Data: systemctl stop postgresqlExpected: DB unavailable.Action: Monitor system behavior during 30-minute outageTest Data: Check logs every 5 minutesExpected: System stays running. Errors logged. No crash.Action: Restart database after 30 minutesExpected: DB available.Action: Verify no data corruption in databaseTest Data: Run DB integrity checkExpected: No corrupted tables or records.Action: Verify system resumes normal operationExpected: Events storing correctly. API responding. | 30-minute DB outage causes no data corruption. System recovers fully on DB restart. | High | To Do |
