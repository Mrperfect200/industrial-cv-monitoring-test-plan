# ICVMS-18

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-18 | TC-RTSP-009 \| RTSP failure generates STREAM_ERROR event | Camera actively streaming and processing. | Action: Kill the RTSP source abruptlyExpected: Stream fails.Action: Check event logExpected: STREAM_ERROR event created with camera_id, timestamp, error detail.Action: Check event schemaExpected: event_id, type=STREAM_ERROR, camera_id, timestamp, severity all present. | STREAM_ERROR event generated with complete schema on RTSP failure. | High | To Do |
