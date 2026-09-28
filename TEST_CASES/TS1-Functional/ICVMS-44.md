# ICVMS-44

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-44 | TC-DASH-002 \| Online/Offline counts accurate in real time | 80 cameras configured. 4 cameras are offline. | Action: Take 4 cameras offlineTest Data: Stop RTSP source for 4 camerasExpected: Cameras go OFFLINE.Action: Open Dashboard overviewExpected: Online = 76, Offline = 4.Action: Bring 1 camera back onlineExpected: Online = 77, Offline = 3 — updates in real time. | Online/Offline counts accurate and update in real time. | High | To Do |
