# ICVMS-19

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-19 | TC-RTSP-010 \| RTSP credentials not logged | Camera configured with RTSP credentials. System running. | Action: Connect camera with RTSP username and passwordExpected: Stream connects successfully.Action: Search all log files for the RTSP password stringTest Data: grep -r "rtsp_password_value" /var/log/Expected: Zero matches found.Action: Search logs for username stringExpected: Zero matches found. | RTSP credentials (username and password) absent from all log files. | Highest | To Do |
