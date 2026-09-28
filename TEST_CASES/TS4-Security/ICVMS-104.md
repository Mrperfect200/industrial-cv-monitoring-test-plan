# ICVMS-104

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-104 | TC-SEC-019 \| RTSP credentials not hardcoded in source code | Source code repository accessible. | Action: Search entire codebase for RTSP password patternsTest Data: grep -riE 'rtsp.*password\|password.*rtsp' src/Expected: Zero matches with actual credential values.Action: Search for hardcoded IP with credentials patternTest Data: grep -rE 'rtsp://[a-z]+:[a-z]+@' src/Expected: Zero matches.Action: Verify RTSP credentials come from environment or configTest Data: grep -r 'os.environ\\|os.getenv\\|config\[' src/Expected: Credentials loaded from env/config. | No RTSP credentials hardcoded in source code. Loaded from environment only. | Highest | To Do |
