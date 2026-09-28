# ICVMS-70

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-70 | TC-ZONE-CV-004 \| Multiple zones on same camera work independently | Two zones ZONE-01 and ZONE-02 configured on same camera CAM-001. | Action: Person enters ZONE-01 onlyExpected: ZONE_ENTER for ZONE-01 fires.Action: Check ZONE-02 eventsExpected: No ZONE_ENTER for ZONE-02.Action: Person enters ZONE-02 onlyExpected: ZONE_ENTER for ZONE-02 fires independently.Action: Verify events have correct zone_id each timeExpected: Events correctly differentiated by zone_id. | Each zone generates independent events. zone_id correct in all events. | High | To Do |
