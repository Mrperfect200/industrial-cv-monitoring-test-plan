# ICVMS-46

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-46 | TC-MON-001 \| GPU utilization reported in monitoring | System running. Inference active. | Action: Check monitoring endpoint or dashboardTest Data: GET /api/v1/monitoring/gpuExpected: Response contains gpu_utilization_percent.Action: Run inference on 10 camerasExpected: GPU utilization % increases and is reported. | GPU utilization reported in real time via monitoring endpoint. | High | To Do |
