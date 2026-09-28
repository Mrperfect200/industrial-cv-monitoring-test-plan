# ICVMS-106

| TC ID | Description | Preconditions | Test Steps | Expected Result | Priority | Status |
|-------|-------------|----------------|------------|-----------------|----------|--------|
| ICVMS-106 | TC-SEC-022 \| All secrets loaded from environment variables only | System running. Environment configuration in place. | Action: Check application startup for secret loading methodTest Data: Review startup logs or config loader codeExpected: Secrets loaded via os.environ, dotenv, or secret manager.Action: Verify .env file is in .gitignoreTest Data: cat .gitignore \| grep .envExpected: .env present in .gitignore.Action: Check no secrets in docker-compose.yml as plaintextTest Data: grep -i password docker-compose.ymlExpected: No plaintext passwords. Uses ${ENV_VAR} syntax. | All secrets loaded from environment. .env excluded from version control. | Highest | To Do |
