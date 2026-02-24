---
title: What's New in v2.5.0
description: Release notes and new features in {{ app.name }} v2.5.0
weight: 1
---

# What's New in v2.5.0

This release introduces a new plugin system and enhanced monitoring capabilities.

## Highlights

- **Plugin System** - Extend {{ app.name }} with custom plugins for data sources and exporters
- **Enhanced Metrics** - New Prometheus metrics for detailed performance monitoring
- **Webhook Notifications** - Configure webhooks for alerts and lifecycle events
- **ARM64 Support** - Native support for ARM64 architectures (Apple Silicon, AWS Graviton)

## Breaking Changes

None in this release.

## New Features

### Plugin System

Install plugins to extend functionality:

```bash
chartsmith plugin install my-plugin
chartsmith plugin list
```

See the [CLI Reference](/reference/cli) for all plugin commands.

### Webhook Notifications

Configure webhooks in the admin console or via environment variables:

```bash
CHARTSMITH_WEBHOOK_URL=https://example.com/webhook
CHARTSMITH_WEBHOOK_EVENTS=alert,upgrade,backup
```

## Upgrade Notes

No special steps required. See the [Migration Guide](/migration) for details.

## Previous Releases

- [v2.4.0 Release Notes](https://github.com/chartsmith/releases/v2.4.0)
