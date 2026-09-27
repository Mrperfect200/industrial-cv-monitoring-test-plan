# Soak Test Monitoring Checklist

**Project:** Industrial Computer Vision Monitoring System  
**Use:** Fill every 30 minutes during soak test runs

---

## Soak Phases

| Phase | Duration | Trigger |
|---|---|---|
| Phase 1 | 8 hours | After integration testing passes |
| Phase 2 | 24 hours | Before UAT |
| Phase 3 | 72 hours | Before Production sign-off |

---

## Per-Check Row (copy for each 30-min interval)

```
Time:          HH:MM
Camera Count:  ____ online / ____ offline
RAM:           ____ MB  (trending: stable / ↑ growing)
VRAM:          ____ MB  (trending: stable / ↑ growing)
GPU %:         ____
CPU %:         ____
Disk %:        ____
Inference FPS: ____  (baseline was: ____)
Queue Depth:   ____  (max configured: ____)
Dropped Frames: ____ total
Event Latency: ____ ms
Reconnects:    ____ (last 30 min)
GPU Temp:      ____ °C
Errors in Log: Y / N  → [paste excerpt if Y]
Notes:         ____
```

---

## Pass Criteria

| Metric | Threshold |
|---|---|
| RAM growth | < 10% per hour |
| VRAM growth | < 5% per hour |
| FPS degradation | < 15% from baseline |
| Queue depth | Never exceeds configured max |
| Service crashes | 0 |
| OOM events | 0 |
| Event loss | 0 (for verifiable events) |
| GPU temperature | < 85°C sustained |

---

## Sign-off

| Phase | Start Time | End Time | Result | Signed By |
|---|---|---|---|---|
| Phase 1 (8h) | | | Pass / Fail | |
| Phase 2 (24h) | | | Pass / Fail | |
| Phase 3 (72h) | | | Pass / Fail | |
