# ICVMS-65

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-65 | TC-TRK-007 \| IDF1 metric meets project-defined target | Tracking evaluation dataset available. IDF1 evaluation script ready. | Action: Run IDF1 evaluation on test tracking sequenceTest Data: python eval_tracking.pyExpected: IDF1 score calculated.Action: Compare IDF1 against project targetExpected: IDF1 >= project-defined target.Action: Log result to evaluation reportExpected: IDF1 score recorded with model version and dataset version. | IDF1 meets project-defined target. Result logged with full traceability. | High | To Do |
