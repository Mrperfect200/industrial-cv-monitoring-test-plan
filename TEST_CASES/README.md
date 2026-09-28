# Test Cases Directory

This directory contains professional-format test cases for the Industrial Computer Vision Monitoring System.

## Structure
```
TEST_CASES/
├── TEMPLATE.md                  # Standard test case template
├── TS1-Functional/              # Functional testing test cases
│   ├── TC-CAM-001.md            # Add new camera
│   ├── TC-CAM-002.md            # Duplicate camera ID
│   └── ...
├── TS2-Computer-Vision-AI/      # Computer Vision & AI test cases
├── TS3-API/                     # API testing test cases
├── TS4-Security/                # Security testing test cases
├── TS5-Performance-Load/        # Performance & load testing test cases
├── TS6-Reliability-Failover/    # Reliability & failover test cases
└── TS7-Soak/                    # Soak testing test cases
```

## Test Case Format
Each test case follows this professional format:
1. **Test Information** - Metadata about the test case
2. **Preconditions** - Required system state before execution
3. **Test Steps** - Numbered steps with actions, data, and expected outcomes
4. **Expected Result** - Clear, measurable outcome
5. **Post Conditions** - System state after test execution
6. **Attachments** - Related test materials
7. **Execution History** - Log of test executions

## Usage
- QA engineers should execute test cases and update the Execution History table
- Failed tests should have a Defect ID linked to the issue tracker
- Automated test cases should reference their automation scripts in Attachments
- All test cases must be reviewed and signed off before promotion to next test phase
