# TS2 — Computer Vision & AI Testing
→ See full test cases in: `../../test-plan/TEST-PLAN-v1.0.md`

**Covers:**
- Detection Accuracy (TC-DET-001 to 020) — lighting, occlusion, crowd, motion blur, FP rate, mAP
- Object Tracking (TC-TRK-001 to 010) — ID persistence, re-ID after occlusion, IDF1
- ROI (TC-ROI-001 to 005)
- Zone Logic CV Layer (TC-ZONE-CV-001 to 005)

**Key Requirement:** Test dataset must be labeled, held-out, and cover:
- Day / Night / Low light / Backlight
- Partial and heavy occlusion
- Low / Medium / High crowd density
- Multiple camera angles
- Motion blur

**Acceptance thresholds:** Defined after PoC — never invented upfront.

**Total:** ~45 Test Cases
