# ICVMS-111

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-111 | TC-PERF-001 \| Baseline: single camera inference latency (ms) | Single camera connected. Model deployed. GPU monitoring active (nvidia-smi). System running. | Action: Start inference on 1 camera at 10 FPSExpected: Inference running.Action: Measure inference latency for 100 consecutive framesTest Data: Log timestamp before and after model.predict()Expected: Latency per frame recorded.Action: Calculate average, min, max, p95 latencyExpected: Baseline latency values documented.Action: Record GPU utilization and VRAMTest Data: nvidia-smi --query-gpu=utilization.gpu,memory.used --format=csvExpected: GPU% and VRAM MB recorded as baseline. | Baseline inference latency and GPU metrics documented for single camera. All values recorded for comparison in scale tests. | High | To Do |
