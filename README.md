# Stackyard

Docker Compose configurations for Caddy, Komodo, and NetBird. Review the upstream
service documentation and the files for the stack you intend to run before
using them; these examples are not a complete production deployment procedure.

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
