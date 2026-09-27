# TS6 — Reliability & Failover Testing
→ See full test cases in: `../../test-plan/TEST-PLAN-v1.0.md`

**Covers:**
- Camera & Network Failures (TC-REL-001 to 007)
  - Single camera RTSP disconnect → auto-reconnect
  - All cameras disconnect simultaneously
  - Frozen stream detection
  - Camera/NVR reboot
  - One failure must NOT affect other cameras
- Service Failures (TC-REL-008 to 014)
  - AI inference crash → auto-restart
  - Backend crash → auto-restart
  - Database unavailable (5 min / 30 min)
  - Full machine restart
  - GPU OOM
  - Disk full

**After every fault injection, verify:**
- Correct events generated for the failure
- No events lost from cameras that stayed online
- No duplicate events post-recovery
- Logs contain root cause
- Monitoring alerts fired

**Total:** ~25 Test Cases
