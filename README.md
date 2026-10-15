# Stackyard

[![Repository checks](https://github.com/wiredbydesign/stackyard/actions/workflows/repository-checks.yml/badge.svg?branch=main&event=push)](https://github.com/wiredbydesign/stackyard/actions/workflows/repository-checks.yml)

Docker Compose configurations for Caddy, Komodo, and NetBird. Review the upstream
service documentation and the files for the stack you intend to run before
using them; these examples are not a complete production deployment procedure.

## Project workflow

Use a branch and pull request for changes to `main`. Badges link to workflow runs on `main`.

| Area | Current process |
| --- | --- |
| Checks | Repository checks validate workflows and scan commit history for secrets. Validate affected Compose files locally with `docker compose ... config --quiet`. |
| Environments | Host-specific configuration stays in ignored local environment files. |
| Delivery | Stacks are configured and started manually by their operator; this repository has no automated service deployment. |
| Releases and recovery | Review configuration changes and upstream image versions before using them. CI does not certify running services. |
| Guides | [Local configuration](#local-configuration) and the relevant service documentation. |

See [CONTRIBUTING.md](CONTRIBUTING.md) for local verification and [SECURITY.md](SECURITY.md) for private vulnerability reporting.

## Local configuration

Copy the relevant `compose.env.example` to an ignored `compose.env` file. Set
hostnames, authentication settings, and unique credentials locally. Example
values are placeholders and must not be used as production credentials. For
Komodo, keep the core and periphery passkeys consistent. NetBird also requires
its external identity provider and management configuration.

Use `docker compose --env-file <local-env-file> -f <compose-file> config --quiet`
to validate a stack before starting it. This checks configuration without
starting containers. Keep generated state, keys, and local environment files
out of Git.

The Repository checks workflow validates GitHub Actions and scans commit
history for secrets. It does not deploy containers or verify the configuration
of running services. See [CONTRIBUTING.md](CONTRIBUTING.md) and
[SECURITY.md](SECURITY.md).
