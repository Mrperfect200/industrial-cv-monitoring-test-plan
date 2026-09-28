# ICVMS-60

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-60 | TC-DET-018 \| mAP@0.5 on held-out test set meets target | mAP evaluation script available. Held-out test dataset labeled and ready. | Action: Run evaluation script on held-out test setTest Data: python eval.py --dataset test/Expected: Evaluation runs to completion.Action: Check mAP@0.5 resultExpected: mAP@0.5 >= project-defined target.Action: Verify test set was not used in trainingTest Data: Check dataset split logsExpected: Test set is independent of train/val sets. | mAP@0.5 meets project target. Test set confirmed independent. | Highest | To Do |
