# ICVMS-27

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-27 | TC-LINE-004 \| Exit direction detected correctly | Virtual line configured. Object approaches from bottom. | Action: Play video of person moving bottom-to-top crossing lineExpected: Object crosses line.Action: Check LINE_CROSSED event direction fieldExpected: direction = EXIT. | Direction = EXIT when object crosses in configured exit direction. | High | To Do |
