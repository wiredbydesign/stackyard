# Contributing

Use a branch and pull request for changes to `main`. Describe the problem,
verification, and any operational impact. Follow applicable `AGENTS.md`
instructions and the repository README and runbooks. Resolve review threads
before merging.

## Verification

Run the checks relevant to the change, including:

Validate the affected Compose configuration locally with a separate, non-production environment file. Do not start services as part of a repository-only check.

The Repository checks workflow validates Actions syntax and scans reachable
commit history for secrets. Keep external actions pinned to full commit SHAs.
Use explicit job permissions, bounded timeouts, and credential-free PR checks.
Investigate scanner findings; only suppress individually verified false positives.

## Dependencies and releases

Commit dependency lockfiles. Review Dependabot changes and their CI results;
version-update configuration does not itself enable GitHub security alerts.
Follow the existing release runbook. A pull request is not authorization to
deploy production or apply infrastructure.

Report vulnerabilities using [SECURITY.md](SECURITY.md). Never commit local
credentials, generated Terraform state, or customer data.
