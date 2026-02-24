---
title: Migration Guide
description: Migrating to {{ app.name }} v2.5.0 from previous versions
weight: 2
---

# Migration Guide

This guide covers migrating to {{ app.name }} v2.5.0 from previous versions.

## Migrating from v2.4.x

v2.5.0 is a drop-in replacement for v2.4.x. No configuration changes are required.

### Recommended Steps

1. Review the [What's New](/whats-new) page for new features
2. Back up your current configuration
3. Follow the standard [upgrade procedure](/operations/upgrading)

## Migrating from v2.3.x or Earlier

If you're upgrading from v2.3.x or earlier, note the following changes:

### Configuration Changes

The following environment variables have been renamed:

| Old Name | New Name |
|----------|----------|
| `APP_CACHE_SIZE` | `CHARTSMITH_CACHE_SIZE_MB` |
| `APP_LOG_LEVEL` | `CHARTSMITH_LOG_LEVEL` |

### Database Migration

A database migration will run automatically on first startup. Ensure you have a backup before upgrading.

{{#if entitlements.isHAEnabled}}
### High Availability Considerations

For HA deployments, perform a rolling upgrade:

1. Upgrade one node at a time
2. Wait for the node to rejoin the cluster before proceeding
3. Verify cluster health between each node upgrade
{{/if}}

## Rollback Procedure

If you need to rollback:

1. Stop the application
2. Restore your configuration backup
3. Restore the database backup (if applicable)
4. Start the previous version

See [Troubleshooting](/operations/troubleshooting) if you encounter issues.
