# ICVMS-47

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-47 | TC-LOG-003 \| No credentials present in log files | Camera configured with RTSP credentials. System running. | Action: Connect camera and run system for 5 minutesExpected: Normal operation.Action: Search all log files for RTSP password valueTest Data: grep -r "PASSWORD_VALUE" /logs/Expected: Zero matches.Action: Search for RTSP username in logsExpected: Zero matches.Action: Search for any credential patternTest Data: grep -riE "password\|secret\|token" /logs/ \| grep -v "INFO\\|ERROR\\|WARN"Expected: No credential values in log content. | Zero credential values found in any log file. | Highest | To Do |
