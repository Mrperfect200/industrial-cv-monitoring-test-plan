# ICVMS-113

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-113 | TC-PERF-003 \| Baseline: single camera GPU utilization % | Single camera running. nvidia-smi available. | Action: Run inference on 1 camera for 5 minutesExpected: Stable operation.Action: Sample GPU utilization every 30 secondsTest Data: nvidia-smi dmon -s u -d 30Expected: 10 samples collected.Action: Calculate average GPU% for single cameraExpected: Baseline GPU% documented.Action: Sample VRAM usageExpected: Baseline VRAM MB documented. | Single-camera GPU% and VRAM baseline documented. Used for headroom calculation at 80 cameras. | High | To Do |
