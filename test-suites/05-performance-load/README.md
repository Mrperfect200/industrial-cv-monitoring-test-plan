# TS5 — Performance & Load Testing
→ See full test cases in: `../../test-plan/TEST-PLAN-v1.0.md`

**Covers:**
- Baseline Single Camera (TC-PERF-001 to 005) — latency, GPU%, VRAM, API response
- Scale Testing (TC-SCL-001 to 007) — 1 → 5 → 10 → 20 → 40 → 60 → 80 cameras
- Concurrent Events Load (TC-PERF-010 to 012)
- Stress Testing (TC-STR-001 to 003) — 90 / 100 / 120 cameras

**Tools:** k6 / Locust + GPU/CPU monitoring (nvidia-smi, htop)

**Important:** All latency/FPS targets are TBD after PoC benchmark.  
Never test against invented numbers.

**Scale test pass criteria per stage:**
- FPS ≥ configured target
- Event loss = 0
- No OOM
- No service crashes

**Total:** ~25 Test Cases
