# ICVMS-63

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-63 | TC-TRK-003 \| Track resumes same ID after brief occlusion | Tracking enabled. Person walks behind obstacle (pillar) briefly. | Action: Play test video: person visible → goes behind pillar for 2s → reappearsExpected: Track lost during occlusion.Action: Check Track ID after reappearanceExpected: Same Track ID re-assigned (not a new ID).Action: Document max occlusion duration before new ID assignedExpected: Threshold for re-ID documented. | Same Track ID re-assigned after brief occlusion. Re-ID threshold documented. | High | To Do |
