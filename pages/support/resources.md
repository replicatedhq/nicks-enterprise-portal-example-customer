---
title: Downloadable Resources
description: Scripts, checklists, and other downloadable files for {{ app.name }}
---

# Downloadable Resources

## Shared Resources

These resources are available to all {{ app.name }} customers.

- [Deployment Script]({{asset "assets/deploy.sh"}}) — Automated deployment helper script
- [Onboarding Checklist]({{asset "assets/onboarding-checklist.txt"}}) — Step-by-step onboarding guide

{{#ifEquals customer.name "Opal Laboratories"}}
## Opal Laboratories Resources

These resources are specific to your organization.

- [Deployment Script]({{asset "assets/deploy.sh"}}) — Your customized deployment script
{{/ifEquals}}
