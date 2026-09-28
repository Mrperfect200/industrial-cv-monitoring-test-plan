# ICVMS-45

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-45 | TC-DASH-009 \| Dashboard inaccessible without login | Dashboard URL known. No active session. | Action: Open dashboard URL in browser without logging inExpected: Redirected to login page. Dashboard content not visible.Action: Attempt to access /dashboard directly with no cookie/tokenExpected: HTTP 401 or redirect to login. | Dashboard completely inaccessible without authentication. | Highest | To Do |
