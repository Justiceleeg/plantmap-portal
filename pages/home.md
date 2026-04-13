---
title: PlantMap Documentation
---

# PlantMap Documentation

Welcome, {{ customer.name }}. This portal contains installation guides, upgrade instructions, and troubleshooting resources for PlantMap — a plant tracking and care logging application.

## Available Features

Your license includes access to:

{{#if entitlements.isEmbeddedClusterDownloadEnabled}}
- **Linux (Embedded Cluster):** Install PlantMap on a bare Linux server
{{/if}}
{{#if entitlements.isHelmInstallEnabled}}
- **Helm Installation:** Deploy PlantMap to an existing Kubernetes cluster
{{/if}}
{{#if entitlements.isAirgapSupported}}
- **Air Gap Support:** Install in disconnected environments with no internet access
{{/if}}
{{#if entitlements.isTerraformEnabled}}
- **Terraform Modules:** Provision AWS infrastructure for PlantMap
{{/if}}

## Getting Started

{{#if entitlements.isEmbeddedClusterDownloadEnabled}}
1. **[Requirements](installation/requirements)** — Review system requirements
{{/if}}
2. **Installation** — Follow the guide for your deployment method:
{{#if entitlements.isEmbeddedClusterDownloadEnabled}}
   - [Linux Installation](installation/linux)
{{/if}}
{{#if entitlements.isHelmInstallEnabled}}
   - [Helm Installation](installation/helm)
{{/if}}
3. **[Release History](installation/release-history)** — View all available versions
4. **[Check for Updates](updates/checking)** — Keep your instance current

## Support

If you run into issues:
1. Generate a support bundle from the PlantMap UI (**Settings > Support Bundle**)
2. [Upload the bundle](operations/bundles/uploaded) for analysis
3. [Contact support](support/contact) if you need further help
