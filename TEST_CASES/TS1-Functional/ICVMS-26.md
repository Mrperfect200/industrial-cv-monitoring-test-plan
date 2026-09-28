# ICVMS-26

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-26 | TC-LINE-003 \| Entry direction detected correctly | Virtual line configured horizontally. Object approaches from top. | Action: Play video of person moving top-to-bottom crossing lineExpected: Object crosses line.Action: Check LINE_CROSSED event direction fieldExpected: direction = ENTRY. | Direction = ENTRY when object crosses in configured entry direction. | High | To Do |
