# default-apps-vsphere

![Version: 0.15.0](https://img.shields.io/badge/Version-0.15.0-informational?style=flat-square)

A Helm chart which defines the pre-installed apps in all Giant Swarm vSphere clusters

**Homepage:** <https://github.com/giantswarm/default-apps-vsphere>

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| apps.capi-node-labeler.appName | string | `"capi-node-labeler"` |  |
| apps.capi-node-labeler.catalog | string | `"default"` |  |
| apps.capi-node-labeler.chartName | string | `"capi-node-labeler"` |  |
| apps.capi-node-labeler.clusterValues.configMap | bool | `true` |  |
| apps.capi-node-labeler.clusterValues.secret | bool | `false` |  |
| apps.capi-node-labeler.forceUpgrade | bool | `false` |  |
| apps.capi-node-labeler.namespace | string | `"kube-system"` |  |
| apps.capi-node-labeler.version | string | `"0.5.0"` |  |
| apps.certExporter.appName | string | `"cert-exporter"` |  |
| apps.certExporter.catalog | string | `"default"` |  |
| apps.certExporter.chartName | string | `"cert-exporter"` |  |
| apps.certExporter.clusterValues.configMap | bool | `true` |  |
| apps.certExporter.clusterValues.secret | bool | `false` |  |
| apps.certExporter.forceUpgrade | bool | `true` |  |
| apps.certExporter.namespace | string | `"kube-system"` |  |
| apps.certExporter.version | string | `"2.9.1"` |  |
| apps.certManager.appName | string | `"cert-manager"` |  |
| apps.certManager.catalog | string | `"default"` |  |
| apps.certManager.chartName | string | `"cert-manager-app"` |  |
| apps.certManager.clusterValues.configMap | bool | `true` |  |
| apps.certManager.clusterValues.secret | bool | `true` |  |
| apps.certManager.dependsOn | string | `"prometheus-operator-crd"` |  |
| apps.certManager.forceUpgrade | bool | `true` |  |
| apps.certManager.namespace | string | `"kube-system"` |  |
| apps.certManager.version | string | `"3.8.1"` |  |
| apps.chartOperatorExtensions.appName | string | `"chart-operator-extensions"` |  |
| apps.chartOperatorExtensions.catalog | string | `"default"` |  |
| apps.chartOperatorExtensions.chartName | string | `"chart-operator-extensions"` |  |
| apps.chartOperatorExtensions.clusterValues.configMap | bool | `false` |  |
| apps.chartOperatorExtensions.clusterValues.secret | bool | `false` |  |
| apps.chartOperatorExtensions.dependsOn | string | `"prometheus-operator-crd"` |  |
| apps.chartOperatorExtensions.namespace | string | `"giantswarm"` |  |
| apps.chartOperatorExtensions.version | string | `"1.1.2"` |  |
| apps.ciliumServiceMonitors.appName | string | `"cilium-servicemonitors"` |  |
| apps.ciliumServiceMonitors.catalog | string | `"default"` |  |
| apps.ciliumServiceMonitors.chartName | string | `"cilium-servicemonitors"` |  |
| apps.ciliumServiceMonitors.clusterValues.configMap | bool | `false` |  |
| apps.ciliumServiceMonitors.clusterValues.secret | bool | `false` |  |
| apps.ciliumServiceMonitors.dependsOn | string | `"prometheus-operator-crd"` |  |
| apps.ciliumServiceMonitors.namespace | string | `"kube-system"` |  |
| apps.ciliumServiceMonitors.version | string | `"0.1.2"` |  |
| apps.etcdKubernetesResourceCountExporter.appName | string | `"etcd-k8s-res-count-exporter"` |  |
| apps.etcdKubernetesResourceCountExporter.catalog | string | `"default"` |  |
| apps.etcdKubernetesResourceCountExporter.chartName | string | `"etcd-kubernetes-resources-count-exporter"` |  |
| apps.etcdKubernetesResourceCountExporter.clusterValues.configMap | bool | `true` |  |
| apps.etcdKubernetesResourceCountExporter.clusterValues.secret | bool | `false` |  |
| apps.etcdKubernetesResourceCountExporter.forceUpgrade | bool | `false` |  |
| apps.etcdKubernetesResourceCountExporter.namespace | string | `"kube-system"` |  |
| apps.etcdKubernetesResourceCountExporter.version | string | `"1.10.0"` |  |
| apps.k8sDnsNodeCache.appName | string | `"k8s-dns-node-cache"` |  |
| apps.k8sDnsNodeCache.catalog | string | `"default"` |  |
| apps.k8sDnsNodeCache.chartName | string | `"k8s-dns-node-cache-app"` |  |
| apps.k8sDnsNodeCache.namespace | string | `"kube-system"` |  |
| apps.k8sDnsNodeCache.version | string | `"2.8.1"` |  |
| apps.metricsServer.appName | string | `"metrics-server"` |  |
| apps.metricsServer.catalog | string | `"default"` |  |
| apps.metricsServer.chartName | string | `"metrics-server-app"` |  |
| apps.metricsServer.clusterValues.configMap | bool | `true` |  |
| apps.metricsServer.clusterValues.secret | bool | `false` |  |
| apps.metricsServer.forceUpgrade | bool | `true` |  |
| apps.metricsServer.namespace | string | `"kube-system"` |  |
| apps.metricsServer.version | string | `"2.4.2"` |  |
| apps.netExporter.appName | string | `"net-exporter"` |  |
| apps.netExporter.catalog | string | `"default"` |  |
| apps.netExporter.chartName | string | `"net-exporter"` |  |
| apps.netExporter.clusterValues.configMap | bool | `true` |  |
| apps.netExporter.clusterValues.secret | bool | `false` |  |
| apps.netExporter.forceUpgrade | bool | `true` |  |
| apps.netExporter.namespace | string | `"kube-system"` |  |
| apps.netExporter.version | string | `"1.21.0"` |  |
| apps.nodeExporter.appName | string | `"node-exporter"` |  |
| apps.nodeExporter.catalog | string | `"default"` |  |
| apps.nodeExporter.chartName | string | `"node-exporter-app"` |  |
| apps.nodeExporter.clusterValues.configMap | bool | `true` |  |
| apps.nodeExporter.clusterValues.secret | bool | `false` |  |
| apps.nodeExporter.forceUpgrade | bool | `true` |  |
| apps.nodeExporter.namespace | string | `"kube-system"` |  |
| apps.nodeExporter.version | string | `"1.19.0"` |  |
| apps.observabilityBundle.appName | string | `"observability-bundle"` |  |
| apps.observabilityBundle.catalog | string | `"default"` |  |
| apps.observabilityBundle.chartName | string | `"observability-bundle"` |  |
| apps.observabilityBundle.clusterValues.configMap | bool | `true` |  |
| apps.observabilityBundle.clusterValues.secret | bool | `false` |  |
| apps.observabilityBundle.forceUpgrade | bool | `false` |  |
| apps.observabilityBundle.inCluster | bool | `true` |  |
| apps.observabilityBundle.namespace | string | `"kube-system"` |  |
| apps.observabilityBundle.version | string | `"1.5.2"` |  |
| apps.observabilityPolicies.appName | string | `"observability-policies"` |  |
| apps.observabilityPolicies.catalog | string | `"default"` |  |
| apps.observabilityPolicies.chartName | string | `"observability-policies"` |  |
| apps.observabilityPolicies.clusterValues.configMap | bool | `false` |  |
| apps.observabilityPolicies.clusterValues.secret | bool | `false` |  |
| apps.observabilityPolicies.dependsOn | string | `"kyverno-crds"` |  |
| apps.observabilityPolicies.namespace | string | `"kube-system"` |  |
| apps.observabilityPolicies.version | string | `"0.0.1"` |  |
| apps.securityBundle.appName | string | `"security-bundle"` |  |
| apps.securityBundle.catalog | string | `"giantswarm"` |  |
| apps.securityBundle.chartName | string | `"security-bundle"` |  |
| apps.securityBundle.clusterValues.configMap | bool | `true` |  |
| apps.securityBundle.clusterValues.secret | bool | `false` |  |
| apps.securityBundle.forceUpgrade | bool | `false` |  |
| apps.securityBundle.inCluster | bool | `true` |  |
| apps.securityBundle.namespace | string | `"kube-system"` |  |
| apps.securityBundle.version | string | `"1.8.0"` |  |
| apps.teleport-kube-agent.appName | string | `"teleport-kube-agent"` |  |
| apps.teleport-kube-agent.catalog | string | `"default"` |  |
| apps.teleport-kube-agent.chartName | string | `"teleport-kube-agent"` |  |
| apps.teleport-kube-agent.clusterValues.configMap | bool | `true` |  |
| apps.teleport-kube-agent.clusterValues.secret | bool | `true` |  |
| apps.teleport-kube-agent.extraConfigs[0].kind | string | `"configMap"` |  |
| apps.teleport-kube-agent.extraConfigs[0].name | string | `"{{ $.Values.clusterName }}-teleport-kube-agent-config"` |  |
| apps.teleport-kube-agent.extraConfigs[0].namespace | string | `"{{ $.Release.Namespace }}"` |  |
| apps.teleport-kube-agent.forceUpgrade | bool | `true` |  |
| apps.teleport-kube-agent.namespace | string | `"kube-system"` |  |
| apps.teleport-kube-agent.version | string | `"0.9.2"` |  |
| apps.vpa.appName | string | `"vertical-pod-autoscaler"` |  |
| apps.vpa.catalog | string | `"default"` |  |
| apps.vpa.chartName | string | `"vertical-pod-autoscaler-app"` |  |
| apps.vpa.clusterValues.configMap | bool | `true` |  |
| apps.vpa.clusterValues.secret | bool | `false` |  |
| apps.vpa.dependsOn | string | `"vertical-pod-autoscaler-crd"` |  |
| apps.vpa.forceUpgrade | bool | `false` |  |
| apps.vpa.namespace | string | `"kube-system"` |  |
| apps.vpa.version | string | `"5.2.4"` |  |
| apps.vpaCRD.appName | string | `"vertical-pod-autoscaler-crd"` |  |
| apps.vpaCRD.catalog | string | `"default"` |  |
| apps.vpaCRD.chartName | string | `"vertical-pod-autoscaler-crd"` |  |
| apps.vpaCRD.clusterValues.configMap | bool | `true` |  |
| apps.vpaCRD.clusterValues.secret | bool | `false` |  |
| apps.vpaCRD.forceUpgrade | bool | `false` |  |
| apps.vpaCRD.namespace | string | `"kube-system"` |  |
| apps.vpaCRD.version | string | `"3.1.0"` |  |
| clusterName | string | `""` |  |
| managementCluster | string | `""` |  |
| organization | string | `""` |  |
| userConfig.certExporter.configMap.values.ciliumNetworkPolicy.enabled | bool | `true` |  |
| userConfig.certManager.configMap.values.ciliumNetworkPolicy.enabled | bool | `true` |  |
| userConfig.certManager.configMap.values.enableServiceLinks | bool | `true` |  |
| userConfig.certManager.configMap.values.ingressShim.defaultIssuerGroup | string | `"cert-manager.io"` |  |
| userConfig.certManager.configMap.values.ingressShim.defaultIssuerKind | string | `"ClusterIssuer"` |  |
| userConfig.certManager.configMap.values.ingressShim.defaultIssuerName | string | `"letsencrypt-giantswarm"` |  |
| userConfig.etcdKubernetesResourceCountExporter.configMap.values.etcd.cacertpath | string | `"/certs/ca.crt"` |  |
| userConfig.etcdKubernetesResourceCountExporter.configMap.values.etcd.certpath | string | `"/certs/server.crt"` |  |
| userConfig.etcdKubernetesResourceCountExporter.configMap.values.etcd.hostPath | string | `"/etc/kubernetes/pki/etcd/"` |  |
| userConfig.etcdKubernetesResourceCountExporter.configMap.values.etcd.keypath | string | `"/certs/server.key"` |  |
| userConfig.etcdKubernetesResourceCountExporter.configMap.values.etcd.prefix | string | `"/registry/"` |  |
| userConfig.etcdKubernetesResourceCountExporter.configMap.values.events.prefix | string | `"/registry/events/"` |  |
| userConfig.metricsServer.configMap.values.ciliumNetworkPolicy.enabled | bool | `true` |  |
| userConfig.netExporter.configMap.values.ciliumNetworkPolicy.enabled | bool | `true` |  |
| userConfig.nodeExporter.configMap.values.disableConntrackCollector | bool | `true` |  |
| userConfig.nodeExporter.configMap.values.disableNvmeCollector | bool | `true` |  |
| userConfig.vpa.configMap.values.ciliumNetworkPolicy.enabled | bool | `true` |  |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.11.0](https://github.com/norwoodj/helm-docs/releases/v1.11.0)
