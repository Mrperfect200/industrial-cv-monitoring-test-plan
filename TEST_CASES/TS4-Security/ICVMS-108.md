# ICVMS-108

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-108 | TC-SEC-024 \| No credentials present in any log files | Camera configured with RTSP credentials. System running for 10 minutes. | Action: Search all log files for RTSP password valueTest Data: grep -r 'ACTUAL_PASSWORD' /var/log/Expected: Zero matches.Action: Search for RTSP username in logsExpected: Zero matches.Action: Search for any credential pattern in logsTest Data: grep -riE 'password=\|secret=\|token=' /var/log/ \| grep -v 'hashed'Expected: No plaintext credential values in logs. | Zero credential values in any log file. Credentials never logged. | Highest | To Do |
