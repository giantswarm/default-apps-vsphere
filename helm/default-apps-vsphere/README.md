# Values schema documentation

This page lists all available configuration options, based on the [configuration values schema](values.schema.json).

<!-- DOCS_START -->

### Apps

Properties within the `.apps` top-level object

| **Property** | **Description** | **More Details** |
| :----------- | :-------------- | :--------------- |
| `apps.capi-node-labeler` |**None**|**Type:** `object`<br/>|
| `apps.capi-node-labeler.appName` |**None**|**Type:** `string`<br/>|
| `apps.capi-node-labeler.catalog` |**None**|**Type:** `string`<br/>|
| `apps.capi-node-labeler.chartName` |**None**|**Type:** `string`<br/>|
| `apps.capi-node-labeler.clusterValues` |**None**|**Type:** `object`<br/>|
| `apps.capi-node-labeler.clusterValues.configMap` |**None**|**Type:** `boolean`<br/>|
| `apps.capi-node-labeler.clusterValues.secret` |**None**|**Type:** `boolean`<br/>|
| `apps.capi-node-labeler.dependsOn` |**None**|**Type:** `string`<br/>|
| `apps.capi-node-labeler.extraConfigs` |**None**|**Type:** `array`<br/>|
| `apps.capi-node-labeler.extraConfigs[*]` |**None**||
| `apps.capi-node-labeler.extraConfigs[*].kind` |**None**|**Type:** `string`<br/>|
| `apps.capi-node-labeler.extraConfigs[*].name` |**None**|**Type:** `string`<br/>|
| `apps.capi-node-labeler.forceUpgrade` |**None**|**Type:** `boolean`<br/>|
| `apps.capi-node-labeler.inCluster` |**None**|**Type:** `boolean`<br/>|
| `apps.capi-node-labeler.namespace` |**None**|**Type:** `string`<br/>|
| `apps.capi-node-labeler.version` |**None**|**Type:** `string`<br/>|
| `apps.certExporter` |**None**|**Type:** `object`<br/>|
| `apps.certExporter.appName` |**None**|**Type:** `string`<br/>|
| `apps.certExporter.catalog` |**None**|**Type:** `string`<br/>|
| `apps.certExporter.chartName` |**None**|**Type:** `string`<br/>|
| `apps.certExporter.clusterValues` |**None**|**Type:** `object`<br/>|
| `apps.certExporter.clusterValues.configMap` |**None**|**Type:** `boolean`<br/>|
| `apps.certExporter.clusterValues.secret` |**None**|**Type:** `boolean`<br/>|
| `apps.certExporter.dependsOn` |**None**|**Type:** `string`<br/>|
| `apps.certExporter.extraConfigs` |**None**|**Type:** `array`<br/>|
| `apps.certExporter.extraConfigs[*]` |**None**||
| `apps.certExporter.extraConfigs[*].kind` |**None**|**Type:** `string`<br/>|
| `apps.certExporter.extraConfigs[*].name` |**None**|**Type:** `string`<br/>|
| `apps.certExporter.forceUpgrade` |**None**|**Type:** `boolean`<br/>|
| `apps.certExporter.inCluster` |**None**|**Type:** `boolean`<br/>|
| `apps.certExporter.namespace` |**None**|**Type:** `string`<br/>|
| `apps.certExporter.version` |**None**|**Type:** `string`<br/>|
| `apps.chartOperatorExtensions` |**None**|**Type:** `object`<br/>|
| `apps.chartOperatorExtensions.appName` |**None**|**Type:** `string`<br/>|
| `apps.chartOperatorExtensions.catalog` |**None**|**Type:** `string`<br/>|
| `apps.chartOperatorExtensions.chartName` |**None**|**Type:** `string`<br/>|
| `apps.chartOperatorExtensions.clusterValues` |**None**|**Type:** `object`<br/>|
| `apps.chartOperatorExtensions.clusterValues.configMap` |**None**|**Type:** `boolean`<br/>|
| `apps.chartOperatorExtensions.clusterValues.secret` |**None**|**Type:** `boolean`<br/>|
| `apps.chartOperatorExtensions.dependsOn` |**None**|**Type:** `string`<br/>|
| `apps.chartOperatorExtensions.extraConfigs` |**None**|**Type:** `array`<br/>|
| `apps.chartOperatorExtensions.extraConfigs[*]` |**None**||
| `apps.chartOperatorExtensions.extraConfigs[*].kind` |**None**|**Type:** `string`<br/>|
| `apps.chartOperatorExtensions.extraConfigs[*].name` |**None**|**Type:** `string`<br/>|
| `apps.chartOperatorExtensions.forceUpgrade` |**None**|**Type:** `boolean`<br/>|
| `apps.chartOperatorExtensions.inCluster` |**None**|**Type:** `boolean`<br/>|
| `apps.chartOperatorExtensions.namespace` |**None**|**Type:** `string`<br/>|
| `apps.chartOperatorExtensions.version` |**None**|**Type:** `string`<br/>|
| `apps.ciliumServiceMonitors` |**None**|**Type:** `object`<br/>|
| `apps.ciliumServiceMonitors.appName` |**None**|**Type:** `string`<br/>|
| `apps.ciliumServiceMonitors.catalog` |**None**|**Type:** `string`<br/>|
| `apps.ciliumServiceMonitors.chartName` |**None**|**Type:** `string`<br/>|
| `apps.ciliumServiceMonitors.clusterValues` |**None**|**Type:** `object`<br/>|
| `apps.ciliumServiceMonitors.clusterValues.configMap` |**None**|**Type:** `boolean`<br/>|
| `apps.ciliumServiceMonitors.clusterValues.secret` |**None**|**Type:** `boolean`<br/>|
| `apps.ciliumServiceMonitors.dependsOn` |**None**|**Type:** `string`<br/>|
| `apps.ciliumServiceMonitors.extraConfigs` |**None**|**Type:** `array`<br/>|
| `apps.ciliumServiceMonitors.extraConfigs[*]` |**None**||
| `apps.ciliumServiceMonitors.extraConfigs[*].kind` |**None**|**Type:** `string`<br/>|
| `apps.ciliumServiceMonitors.extraConfigs[*].name` |**None**|**Type:** `string`<br/>|
| `apps.ciliumServiceMonitors.forceUpgrade` |**None**|**Type:** `boolean`<br/>|
| `apps.ciliumServiceMonitors.inCluster` |**None**|**Type:** `boolean`<br/>|
| `apps.ciliumServiceMonitors.namespace` |**None**|**Type:** `string`<br/>|
| `apps.ciliumServiceMonitors.version` |**None**|**Type:** `string`<br/>|
| `apps.clusterResources` |**None**|**Type:** `object`<br/>|
| `apps.clusterResources.appName` |**None**|**Type:** `string`<br/>|
| `apps.clusterResources.catalog` |**None**|**Type:** `string`<br/>|
| `apps.clusterResources.chartName` |**None**|**Type:** `string`<br/>|
| `apps.clusterResources.clusterValues` |**None**|**Type:** `object`<br/>|
| `apps.clusterResources.clusterValues.configMap` |**None**|**Type:** `boolean`<br/>|
| `apps.clusterResources.clusterValues.secret` |**None**|**Type:** `boolean`<br/>|
| `apps.clusterResources.dependsOn` |**None**|**Type:** `string`<br/>|
| `apps.clusterResources.extraConfigs` |**None**|**Type:** `array`<br/>|
| `apps.clusterResources.extraConfigs[*]` |**None**||
| `apps.clusterResources.extraConfigs[*].kind` |**None**|**Type:** `string`<br/>|
| `apps.clusterResources.extraConfigs[*].name` |**None**|**Type:** `string`<br/>|
| `apps.clusterResources.forceUpgrade` |**None**|**Type:** `boolean`<br/>|
| `apps.clusterResources.inCluster` |**None**|**Type:** `boolean`<br/>|
| `apps.clusterResources.namespace` |**None**|**Type:** `string`<br/>|
| `apps.clusterResources.version` |**None**|**Type:** `string`<br/>|
| `apps.metricsServer` |**None**|**Type:** `object`<br/>|
| `apps.metricsServer.appName` |**None**|**Type:** `string`<br/>|
| `apps.metricsServer.catalog` |**None**|**Type:** `string`<br/>|
| `apps.metricsServer.chartName` |**None**|**Type:** `string`<br/>|
| `apps.metricsServer.clusterValues` |**None**|**Type:** `object`<br/>|
| `apps.metricsServer.clusterValues.configMap` |**None**|**Type:** `boolean`<br/>|
| `apps.metricsServer.clusterValues.secret` |**None**|**Type:** `boolean`<br/>|
| `apps.metricsServer.dependsOn` |**None**|**Type:** `string`<br/>|
| `apps.metricsServer.extraConfigs` |**None**|**Type:** `array`<br/>|
| `apps.metricsServer.extraConfigs[*]` |**None**||
| `apps.metricsServer.extraConfigs[*].kind` |**None**|**Type:** `string`<br/>|
| `apps.metricsServer.extraConfigs[*].name` |**None**|**Type:** `string`<br/>|
| `apps.metricsServer.forceUpgrade` |**None**|**Type:** `boolean`<br/>|
| `apps.metricsServer.inCluster` |**None**|**Type:** `boolean`<br/>|
| `apps.metricsServer.namespace` |**None**|**Type:** `string`<br/>|
| `apps.metricsServer.version` |**None**|**Type:** `string`<br/>|
| `apps.nodeExporter` |**None**|**Type:** `object`<br/>|
| `apps.nodeExporter.appName` |**None**|**Type:** `string`<br/>|
| `apps.nodeExporter.catalog` |**None**|**Type:** `string`<br/>|
| `apps.nodeExporter.chartName` |**None**|**Type:** `string`<br/>|
| `apps.nodeExporter.clusterValues` |**None**|**Type:** `object`<br/>|
| `apps.nodeExporter.clusterValues.configMap` |**None**|**Type:** `boolean`<br/>|
| `apps.nodeExporter.clusterValues.secret` |**None**|**Type:** `boolean`<br/>|
| `apps.nodeExporter.dependsOn` |**None**|**Type:** `string`<br/>|
| `apps.nodeExporter.extraConfigs` |**None**|**Type:** `array`<br/>|
| `apps.nodeExporter.extraConfigs[*]` |**None**||
| `apps.nodeExporter.extraConfigs[*].kind` |**None**|**Type:** `string`<br/>|
| `apps.nodeExporter.extraConfigs[*].name` |**None**|**Type:** `string`<br/>|
| `apps.nodeExporter.forceUpgrade` |**None**|**Type:** `boolean`<br/>|
| `apps.nodeExporter.inCluster` |**None**|**Type:** `boolean`<br/>|
| `apps.nodeExporter.namespace` |**None**|**Type:** `string`<br/>|
| `apps.nodeExporter.version` |**None**|**Type:** `string`<br/>|
| `apps.observabilityBundle` |**None**|**Type:** `object`<br/>|
| `apps.observabilityBundle.appName` |**None**|**Type:** `string`<br/>|
| `apps.observabilityBundle.catalog` |**None**|**Type:** `string`<br/>|
| `apps.observabilityBundle.chartName` |**None**|**Type:** `string`<br/>|
| `apps.observabilityBundle.clusterValues` |**None**|**Type:** `object`<br/>|
| `apps.observabilityBundle.clusterValues.configMap` |**None**|**Type:** `boolean`<br/>|
| `apps.observabilityBundle.clusterValues.secret` |**None**|**Type:** `boolean`<br/>|
| `apps.observabilityBundle.dependsOn` |**None**|**Type:** `string`<br/>|
| `apps.observabilityBundle.extraConfigs` |**None**|**Type:** `array`<br/>|
| `apps.observabilityBundle.extraConfigs[*]` |**None**||
| `apps.observabilityBundle.extraConfigs[*].kind` |**None**|**Type:** `string`<br/>|
| `apps.observabilityBundle.extraConfigs[*].name` |**None**|**Type:** `string`<br/>|
| `apps.observabilityBundle.forceUpgrade` |**None**|**Type:** `boolean`<br/>|
| `apps.observabilityBundle.inCluster` |**None**|**Type:** `boolean`<br/>|
| `apps.observabilityBundle.namespace` |**None**|**Type:** `string`<br/>|
| `apps.observabilityBundle.version` |**None**|**Type:** `string`<br/>|
| `apps.teleport-kube-agent` |**None**|**Type:** `object`<br/>|
| `apps.teleport-kube-agent.appName` |**None**|**Type:** `string`<br/>|
| `apps.teleport-kube-agent.catalog` |**None**|**Type:** `string`<br/>|
| `apps.teleport-kube-agent.chartName` |**None**|**Type:** `string`<br/>|
| `apps.teleport-kube-agent.clusterValues` |**None**|**Type:** `object`<br/>|
| `apps.teleport-kube-agent.clusterValues.configMap` |**None**|**Type:** `boolean`<br/>|
| `apps.teleport-kube-agent.clusterValues.secret` |**None**|**Type:** `boolean`<br/>|
| `apps.teleport-kube-agent.dependsOn` |**None**|**Type:** `string`<br/>|
| `apps.teleport-kube-agent.extraConfigs` |**None**|**Type:** `array`<br/>|
| `apps.teleport-kube-agent.extraConfigs[*]` |**None**||
| `apps.teleport-kube-agent.extraConfigs[*].kind` |**None**|**Type:** `string`<br/>|
| `apps.teleport-kube-agent.extraConfigs[*].name` |**None**|**Type:** `string`<br/>|
| `apps.teleport-kube-agent.forceUpgrade` |**None**|**Type:** `boolean`<br/>|
| `apps.teleport-kube-agent.inCluster` |**None**|**Type:** `boolean`<br/>|
| `apps.teleport-kube-agent.namespace` |**None**|**Type:** `string`<br/>|
| `apps.teleport-kube-agent.version` |**None**|**Type:** `string`<br/>|

### User Config

Properties within the `.userConfig` top-level object

| **Property** | **Description** | **More Details** |
| :----------- | :-------------- | :--------------- |
| `userConfig.certExporter` |**None**|**Type:** `object`<br/>|
| `userConfig.certExporter.configMap` |**None**|**Type:** `object`<br/>|
| `userConfig.certExporter.configMap.values` |**None**|**Types:** `object, string`<br/>|
| `userConfig.certManager` |**None**|**Type:** `object`<br/>|
| `userConfig.certManager.configMap` |**None**|**Type:** `object`<br/>|
| `userConfig.certManager.configMap.values` |**None**|**Types:** `object, string`<br/>|
| `userConfig.metricsServer` |**None**|**Type:** `object`<br/>|
| `userConfig.metricsServer.configMap` |**None**|**Type:** `object`<br/>|
| `userConfig.metricsServer.configMap.values` |**None**|**Types:** `object, string`<br/>|
| `userConfig.netExporter` |**None**|**Type:** `object`<br/>|
| `userConfig.netExporter.configMap` |**None**|**Type:** `object`<br/>|
| `userConfig.netExporter.configMap.values` |**None**|**Types:** `object, string`<br/>|
| `userConfig.nodeExporter` |**None**|**Type:** `object`<br/>|
| `userConfig.nodeExporter.configMap` |**None**|**Type:** `object`<br/>|
| `userConfig.nodeExporter.configMap.values` |**None**|**Types:** `object, string`<br/>|
| `userConfig.vpa` |**None**|**Type:** `object`<br/>|
| `userConfig.vpa.configMap` |**None**|**Type:** `object`<br/>|
| `userConfig.vpa.configMap.values` |**None**|**Types:** `object, string`<br/>|

### Other

| **Property** | **Description** | **More Details** |
| :----------- | :-------------- | :--------------- |
| `clusterName` |**None**|**Type:** `string`<br/>|
| `managementCluster` |**None**|**Type:** `string`<br/>|
| `organization` |**None**|**Type:** `string`<br/>|

<!-- DOCS_END -->
