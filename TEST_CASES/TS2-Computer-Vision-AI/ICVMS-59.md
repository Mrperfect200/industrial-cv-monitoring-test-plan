# ICVMS-59

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-59 | TC-DET-017 \| Per-class threshold configurable without code change | Model deployed. Config file accessible. | Action: Set helmet threshold = 0.65 in config fileExpected: Config updated.Action: Restart inference serviceExpected: Service restarts with new config.Action: Run inference — verify helmet detections below 0.65 absentExpected: Zero helmet detections below 0.65.Action: Change threshold to 0.80 without code changeTest Data: Edit config onlyExpected: New threshold applied on restart. | Per-class threshold fully configurable via config file. No code change required. | High | To Do |
