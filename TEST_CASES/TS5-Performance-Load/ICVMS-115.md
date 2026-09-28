# ICVMS-115

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-115 | TC-SCL-001 \| Scale test — 1 camera: FPS/latency/GPU/CPU/RAM | 1 camera connected. Model deployed. All monitoring tools active. | Action: Run system with 1 camera for 10 minutesExpected: Stable operation.Action: Record: Inference FPS, End-to-end latency, GPU%, VRAM, CPU%, RAM, Dropped frames, Event lossTest Data: Record every 2 minutesExpected: All metrics captured.Action: Verify: FPS >= configured target, Event loss = 0, No OOM, No crashesExpected: All pass criteria met.Action: Document all values as 1-camera baselineExpected: Baseline table completed. | 1-camera baseline: all metrics within acceptable range. Zero event loss. Zero crashes. | High | To Do |
