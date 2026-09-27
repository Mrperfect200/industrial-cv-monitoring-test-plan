# TS7 — Soak Testing
→ See full test cases in: `../../test-plan/TEST-PLAN-v1.0.md`

**Phases:**

| Phase | Duration | When |
|---|---|---|
| Phase 1 | 8 hours | After integration testing passes |
| Phase 2 | 24 hours | Before UAT |
| Phase 3 | 72 hours | Before Production sign-off |

**Monitor every 30 minutes:**
→ See: `../../checklists/SOAK-TEST-MONITORING-CHECKLIST.md`

**Pass criteria:**
- No service crash during full duration
- No OOM
- RAM stable (no unbounded growth)
- VRAM stable
- FPS within ±15% of baseline throughout
- Zero event loss for verifiable events
- All cameras recover from any transient disconnect
- No queue overflow errors in logs
