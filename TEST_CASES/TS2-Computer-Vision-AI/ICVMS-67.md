# ICVMS-67

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-67 | TC-ROI-003 \| ROI reduces GPU inference area vs full frame | ROI configured on CAM-001. GPU monitoring active. | Action: Run inference with full-frame processing (no ROI)Expected: Baseline GPU% recorded.Action: Enable ROI (50% of frame area)Expected: ROI active.Action: Run same inference with ROIExpected: GPU% measured.Action: Compare GPU% full-frame vs ROIExpected: GPU% lower with ROI than full-frame. | ROI reduces GPU utilization compared to full-frame inference. | High | To Do |
