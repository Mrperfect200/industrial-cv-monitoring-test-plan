# ICVMS-103

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-103 | TC-SEC-018 \| TLS 1.2+ enforced — TLS 1.0/1.1 disabled | TLS scanner available (nmap, testssl.sh, or similar). | Action: Run TLS scan against API serverTest Data: testssl.sh https://your-api/Expected: Scan results available.Action: Check TLS 1.0 and 1.1 statusExpected: TLS 1.0 and 1.1 disabled.Action: Check TLS 1.2 and 1.3 statusExpected: TLS 1.2 and/or 1.3 enabled.Action: Check for weak cipher suitesExpected: No RC4, DES, or NULL ciphers present. | TLS 1.0 and 1.1 disabled. TLS 1.2+ enforced. No weak ciphers. | High | To Do |
