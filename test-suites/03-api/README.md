# TS3 — API Testing
→ See full test cases in: `../../test-plan/TEST-PLAN-v1.0.md`

**Covers:**
- Authentication (TC-API-001 to 010) — valid login, wrong password, expired token, no token
- Camera Endpoints (TC-API-011 to 020)
- Events Endpoints (TC-API-021 to 027)
- Areas & Zones Endpoints (TC-API-028 to 033)
- API Non-Functional (TC-API-040 to 045) — versioning, rate limiting, sorting, error schema

**Tools:** Postman / pytest + requests

**Test Categories per endpoint:**
- Positive (valid input, correct auth)
- Negative (invalid input, missing fields)
- Auth (no token, invalid token, expired token)
- Authorization (wrong role → 403)
- Boundary (max page size, empty list)

**Total:** ~50 Test Cases
