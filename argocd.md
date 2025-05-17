import Tabs from "@theme/Tabs"
import TabItem from "@theme/TabItem"
import Prerequisites from "/docs/build-your-software-catalog/sync-data-to-catalog/templates/\_ocean_helm_prerequisites_block.mdx"
import ProjecttBlueprint from '/docs/build-your-software-catalog/custom-integration/webhook/examples/resources/argocd/\_example_project_blueprint.mdx'
import ApplicationBlueprint from '/docs/build-your-software-catalog/custom-integration/webhook/examples/resources/argocd/\_example_application_blueprint.mdx'
import EventBlueprint from '/docs/build-your-software-catalog/custom-integration/webhook/examples/resources/argocd/\_example_event_blueprint.mdx'

import ArgoCDWebhookConfig from '/docs/build-your-software-catalog/custom-integration/webhook/examples/resources/argocd/\_example_webhook_configuration.mdx'
import ArgoCDEventWebhookConfig from '/docs/build-your-software-catalog/custom-integration/webhook/examples/resources/argocd/\_example_events_webhook_config.mdx'
import ArgoCDEventManifest from '/docs/build-your-software-catalog/custom-integration/webhook/examples/resources/argocd/\_example_events_manifest.mdx'
import PortApiRegionTip from "/docs/generalTemplates/_port_region_parameter_explanation_template.md"
import OceanRealtimeInstallation from "/docs/build-your-software-catalog/sync-data-to-catalog/templates/_ocean_realtime_installation.mdx"


# ArgoCD

Port's ArgoCD integration allows you to model ArgoCD resources in your software catalog and ingest data into them.


## Overview

This integration allows you to:

- Map and organize your desired ArgoCD resources and their metadata in Port (see supported resources below).
- Watch for ArgoCD object changes (create/update/delete) in real-time, and automatically apply the changes to your software catalog.

### Supported Resources

The resources that can be ingested from ArgoCD into Port are listed below.
It is possible to reference any field that appears in the API responses linked below in the mapping configuration.

- [`cluster`](https://cd.apps.argoproj.io/swagger-ui#operation/ClusterService_List)
- [`project`](https://cd.apps.argoproj.io/swagger-ui#operation/ProjectService_List)
- [`application`](https://cd.apps.argoproj.io/swagger-ui#operation/ApplicationService_List)
- [`deployment-history`](https://cd.apps.argoproj.io/swagger-ui#operation/ApplicationService_List) 
- [`kubernetes-resource`](https://cd.apps.argoproj.io/swagger-ui#operation/ApplicationService_List)
- [`managed-resource`](https://cd.apps.argoproj.io/swagger-ui#operation/ApplicationService_ManagedResources)

## Prerequisites

- ArgoCD installed and configured
- Access to Port API
- Environment variables set for authentication

## Configuration Mapping

// Configuration Mapping
// The following maps ArgoCD application fields to Port properties:
// 
// | ArgoCD Field | Port Property |
// |-------------|--------------|
// | metadata.name | identifier |
// | spec.project | project |
// | spec.source.repoURL | gitRepository |
// | spec.source.path | gitPath |
// | spec.destination.namespace | namespace |
// | status.health.status | healthStatus |
// | status.sync.status | syncStatus |
//
// Additional configuration can be added as needed.


## Setup Instructions

1. Install the Port CLI
2. Configure your environment variables
3. Run the initial sync
4. Verify the connection

## Troubleshooting

Common issues and their solutions:

- Connection errors: Check your network settings
- Authentication failures: Verify your tokens
- Sync issues: Check the logs for more details