# Reporting a security issue

Use [private vulnerability reporting](https://github.com/wiredbydesign/stackyard/security/advisories/new).
Do not put credentials, customer data, or exploit details in public issues, pull
requests, or CI logs. Include the affected revision, impact, and a safe
reproduction with sensitive values removed.

Keep real credentials in the deployment secret store or local ignored files.
If a credential was committed, revoke or rotate it first; deleting a file does
not remove the credential from Git history.

Dependency updates require the same checks as other changes. A passing scan is
not a guarantee that code or dependencies are secure.
