---
title: Requirements
description: System requirements for {{ app.name }}
weight: 100
---

# System Requirements

## Hardware Requirements

**Updated for v2.4.0** - Requirements have been reduced thanks to performance optimizations.

| Component | Minimum | Recommended |
|-----------|---------|-------------|
| CPU | 2 cores | 4 cores |
| Memory | 4 GB | 8 GB |
| Disk | 20 GB SSD | 50 GB SSD |

{{#if entitlements.isHAEnabled}}
### High Availability Requirements

For HA deployments, multiply the above requirements by the number of nodes (minimum 3).

| Component | Per Node | 3-Node Cluster |
|-----------|----------|-----------------|
| CPU | 4 cores | 12 cores |
| Memory | 8 GB | 24 GB |
| Disk | 40 GB SSD | 120 GB SSD |
{{/if}}

## Software Requirements

{{#if entitlements.isHelmInstallEnabled}}
### Helm Deployments

- Kubernetes 1.27+
- Helm 3.12+
- `kubectl` configured with cluster access
- Container runtime: containerd 1.6+ or CRI-O 1.25+
{{/if}}

{{#if entitlements.isEmbeddedClusterDownloadEnabled}}
### Linux Deployments

- Ubuntu 22.04+ / RHEL 8+ / Rocky Linux 8+ / Amazon Linux 2023
- Systemd-based init system
- Root access or sudo privileges
- Internet access (or [air gap bundle](/installation/airgap) for disconnected environments)
{{/if}}

## Network Requirements

| Port | Protocol | Direction | Purpose |
|------|----------|-----------|---------|
| 443 | TCP | Outbound | Registry access, license validation |
| 6443 | TCP | Inbound | Kubernetes API (Helm only) |
| 30000-30100 | TCP | Inbound | NodePort services (Linux only) |

{{#if entitlements.isHAEnabled}}
### HA Network Requirements

| Port | Protocol | Direction | Purpose |
|------|----------|-----------|---------|
| 2379-2380 | TCP | Internal | etcd peer communication |
| 9443 | TCP | Internal | Join server |
| 10250 | TCP | Internal | Kubelet API |
{{/if}}

## Registry Access

{{ app.name }} images are distributed through the Replicated registry. Authenticate with your service account token:

```bash
helm registry login registry.replicated.com \
  --username {{ customer.email }} \
  --password {{ license.id }}
```
