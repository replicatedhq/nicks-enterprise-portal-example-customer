---
title: What's New in v2.6.0
description: Release notes and new features in {{ app.name }} v2.6.0
weight: 1
---

# What's New in v2.6.0

This release brings SSO authentication, improved backup reliability, and a new dashboard UI.

## Highlights

- **SSO Authentication** - Single sign-on support via SAML 2.0 and OIDC providers
- **Dashboard Redesign** - New real-time dashboard with customizable widgets
- **Incremental Backups** - Faster, more efficient backup strategy with point-in-time recovery
- **Multi-cluster Support** - Manage multiple {{ app.name }} instances from a single pane

## Breaking Changes

- The `CHARTSMITH_AUTH_MODE` environment variable now defaults to `sso` instead of `local`
- Deprecated `chartsmith backup --full` flag (use `chartsmith backup --type=full` instead)

## New Features

### SSO Authentication

Configure your identity provider in the admin console:

```yaml
auth:
  mode: sso
  provider: okta  # or azure-ad, google, custom-oidc
  issuer: https://your-org.okta.com
  clientId: ${OIDC_CLIENT_ID}
  clientSecret: ${OIDC_CLIENT_SECRET}
```

See the [Configuration Guide](/configuration/guide) for detailed setup instructions.

### Dashboard Redesign

The new dashboard includes:

- Real-time metrics and alerts
- Customizable widget layout
- Dark mode support
- Mobile-responsive design

### Incremental Backups

Enable incremental backups for faster operations:

```bash
chartsmith backup --type=incremental
chartsmith restore --point-in-time="2024-01-15T10:30:00Z"
```

## Upgrade Notes

1. Review SSO configuration if using local authentication
2. Update any scripts using the deprecated `--full` flag
3. Run `chartsmith migrate` after upgrading

See the [Migration Guide](/migration) for detailed upgrade instructions.

## Previous Releases

- [v2.5.0 Release Notes](https://github.com/chartsmith/releases/v2.5.0)
- [v2.4.0 Release Notes](https://github.com/chartsmith/releases/v2.4.0)
