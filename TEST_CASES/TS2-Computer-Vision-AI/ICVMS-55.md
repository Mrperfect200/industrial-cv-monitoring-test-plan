# ICVMS-55

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-55 | TC-DET-009 \| False positive rate — empty scene | Test dataset of empty scenes (no people present) available. | Action: Run inference on 200 empty scene framesTest Data: No people in any frameExpected: Ideally zero detections.Action: Count false positivesExpected: FP count / total frames = FP rate.Action: Verify FP rate meets project thresholdExpected: FP rate <= project-defined threshold. | False positive rate on empty scenes meets project-defined threshold. | High | To Do |
