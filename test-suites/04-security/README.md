# TS4 — Security Testing
→ See full test cases in: `../../test-plan/TEST-PLAN-v1.0.md`

**Covers:**
- Authentication & Session (TC-SEC-001 to 006) — hash, JWT, brute force, timing oracle
- Authorization & RBAC (TC-SEC-007 to 011) — IDOR, privilege escalation
- Injection (TC-SEC-012 to 016) — SQLi, XSS, command injection
- Transport & Secrets (TC-SEC-017 to 024) — HTTPS, TLS, no hardcoded secrets, creds not in logs
- Input Validation & CSRF (TC-SEC-025 to 028)
- Audit Logging (TC-SEC-029 to 032)

**Tools:** Manual review + OWASP checklist + Burp Suite

**Critical checks:**
- No credentials in source code (grep)
- No credentials in logs (grep)
- RTSP credentials absent from API responses
- HTTPS enforced, TLS 1.2+ only

**Total:** ~35 Test Cases
