# ICVMS-66

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-66 | TC-ROI-001 \| Detection only within configured ROI | ROI configured on CAM-001. Object detection active. | Action: Place object outside configured ROI boundaryTest Data: Use test video with object outside ROIExpected: Object visible in frame.Action: Check detection outputExpected: Zero detections for object outside ROI.Action: Place object inside ROIExpected: Detection fires correctly. | Objects outside ROI produce zero detections. Objects inside ROI detected correctly. | High | To Do |
