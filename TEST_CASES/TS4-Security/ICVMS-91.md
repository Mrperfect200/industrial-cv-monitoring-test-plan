# ICVMS-91

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-91 | TC-SEC-001 \| Passwords stored as hash — no plaintext in DB | Database access available. Admin user exists. | Action: Query users table in database directlyTest Data: SELECT password FROM users LIMIT 5;Expected: Password column contains hashed values only.Action: Verify hash formatExpected: Values start with bcrypt/argon2/scrypt prefix. Not plaintext.Action: Attempt to find any plaintext password in DBTest Data: SELECT * FROM users WHERE LENGTH(password) < 20;Expected: Zero results. | All passwords stored as hashes. No plaintext passwords in database. | Highest | To Do |
