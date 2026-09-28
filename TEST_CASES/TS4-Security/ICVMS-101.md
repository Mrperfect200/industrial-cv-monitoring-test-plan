# ICVMS-101

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-101 | TC-SEC-014 \| XSS in camera name stored safely not executed | Admin logged in. Dashboard renders camera names. | Action: POST /api/v1/cameras with XSS payload as nameTest Data: {"name":"<script>alert(document.cookie)</script>","rtsp_url":"rtsp://x/y","area":"A"}Expected: HTTP 201. Camera created.Action: Open dashboard camera list pageExpected: Page loads. No alert dialog appears.Action: Inspect rendered HTMLTest Data: View page sourceExpected: Script tags are HTML-encoded as &lt;script&gt;. | XSS payload stored safely. Not executed in browser. Correctly escaped in dashboard. | Highest | To Do |
