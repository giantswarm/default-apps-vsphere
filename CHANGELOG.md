# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Changed

- Disable Renovate app updates.
- Actually disable Renovate updates.

## [0.16.0] - 2024-08-23

> [!WARNING]
> This release includes changes that enable the unification of cluster-vsphere and default-apps-vsphere. The unification
> of cluster-vsphere and default-apps-vsphere does not happen automatically, it must be enabled explicitly and even then
> it requires manual steps. See details below.

### Added

- Add `observability-policies` app.
- New Helm value `.Values.deleteOptions.moveAppsHelmOwnershipToClusterVSphere`, which, when enabled, will pause all apps in the default-apps-vsphere, and it will enable the below hooks. The apps are paused in order to prevent the deletion of Chart resources in the WC.
- Helm hook to remove app-operator finalizer from App CRs, so that App CRs are deleted from the MC, while Chart CRs stay on the WC.
- Helm hook to propagate pause annotation to all bundled apps.

### Changed

- Update `net-exporter` to v1.21.0.
- Update `k8s-dns-node-cache-app` to v2.8.1.
- Update `teleport-kube-agent-app` to v0.9.1.
- Update `cert-manager-app` to v3.8.0.
- Update `cert-exporter` to v2.9.1.
- Update `teleport-kube-agent-app` to v0.9.2.
- Update `observability-bundle` to v1.5.1.
- Update `security-bundle` to v1.8.0.
- Update `vertical-pod-autoscaler-app` to v5.2.4.

### ⚠️ Workload cluster upgrade with manual steps

The steps to upgrade a workload cluster, with unifying cluster-vsphere and default-apps-vsphere, are the following:
- Upgrade default-apps-vsphere App to the latest release that includes this change.
- Update default-apps-vsphere Helm value `.Values.deleteOptions.moveAppsHelmOwnershipToClusterVSphere` to `true`.
  - All App CRs, except observability-bundle and security-bundle, will get `app-operator.giantswarm.io/paused: true` annotation,
    so wait few minutes for Helm post-upgrade hook to apply the change to all required App CRs.
- Delete default-apps-vsphere CR.
  - ⚠️ In case you are removing default-apps-vsphere App CR from your gitops repo which is using Flux, and depending on
    how Flux is configured, default-apps-vsphere App CR may or may not get deleted from the management cluster. In case
    Flux does not delete default-apps-vsphere App CR from the management cluster, make sure to delete it manually.
  - App CRs (on the MC) for all default apps will get deleted. Wait few minutes for this to happen.
  - Chart CRs on the workload cluster will remain untouched, so all apps will continue running.
- Upgrade cluster-vsphere App CR to the latest (TBA release which includes [these changes](https://github.com/giantswarm/cluster-vsphere/pull/262)).
  - cluster-vsphere will deploy all default apps, so wait a few minutes for all Apps to be successfully deployed.
  - Chart resources on the workload cluster will get updated, as newly deployed App resources will take over the reconciliation
    of the existing Chart resources.

We're almost there, with just one more issue to fix manually.

VPA CRD used to installed as an App resource from default-apps-vsphere, and now it's being installed as a HelmRelease from
cluster-vsphere. Now, as a consequence of the above upgrade, we have the following situation:
- default-apps-vsphere App has been deleted, but the vertical-pod-autoscaler-crd Chart CRs remained in the workload cluster.
- cluster-vsphere has been upgraded, so now it also installs vertical-pod-autoscaler-crd HelmRelease.
- outcome: we now have vertical-pod-autoscaler-crd HelmRelease in the MC and vertical-pod-autoscaler-crd Chart CR in the WC.

Now we will remove the leftover vertical-pod-autoscaler-crd Chart CR in a safe way:

1. Pause vertical-pod-autoscaler-crd Chart CR.

Add annotation `chart-operator.giantswarm.io/paused: "true"` to vertical-pod-autoscaler-crd Chart CR in the workload cluster:

```sh
kubectl annotate -n giantswarm chart vertical-pod-autoscaler-crd chart-operator.giantswarm.io/paused="true" --overwrite
```

2. Delete vertical-pod-autoscaler-crd Chart CR in the workload cluster.

```shell
kubectl delete -n giantswarm chart vertical-pod-autoscaler-crd
```

The command line will probably hang, as the chart-operator finalizer has is not getting removed (vertical-pod-autoscaler-crd
Chart CR has been paused). Proceed to the next step to remove the finalizer and unblock the deletion.

3. Remove finalizers from the vertical-pod-autoscaler-crd Chart CR

Open another terminal window and run the following command to remove the vertical-pod-autoscaler-crd Chart CR finalizers:

```shell
kubectl patch chart vertical-pod-autoscaler-crd -n giantswarm --type=json -p='[{"op": "remove", "path": "/metadata/finalizers"}]'
```

This will unblock the deletion and vertical-pod-autoscaler-crd will get removed, **without actually deleting VPA CustomResourceDefinition**.

From now on, VPA CustomResourceDefinition will be maintained by the vertical-pod-autoscaler HelmRelease on the management cluster.

## [0.15.0] - 2024-07-08

### Changed

- Update `net-exporter` to 1.20.0.
- Update `k8s-dns-node-cache-app` to 2.7.0.

## [0.14.0] - 2024-04-09

### Added

- Add `cilium-servicemonitors` app.
- Add `capi-node-labeler` app.
- Add `k8s-dns-node-cache` app.

## [0.13.0] - 2024-02-27

### Added

- Add `security-bundle` app.

## [0.12.1] - 2024-02-12

### Added

- Include support for schemadocs to generate Chart README file

### Changed

- Bump `observability-bundle` to `1.2.1`.
- Use a YAML object for the apps configuration, so that defaults are not overwritten when users pass custom values.

## [0.12.0] - 2023-12-04

### Added

- Add 'teleport-kube-agent-app`
- Add vSphere icon.

### Fixed

- Shortened `etcd-kubernetes-resources-count-exporter` appName to `etcd-k8s-res-count-exporter`.

## [0.11.3] - 2023-11-20

## [0.11.2] - 2023-11-02

### Added

- Added `chart-operator-extension` version `v1.1.1` that contains e.g. `ServiceMonitors` for `chart-operator`.
- Add dependency between `vertical-pod-autoscaler-crd` and `vertical-pod-autoscaler`.
- Enable `ciliumNetworkPolicy` for `observabilityBundle`.

### Removed

- `unconfined` apparmor profile for `nodeExporter` app.

### Changed

- Bump `cert-exporter` from `2.6.0` to `2.8.2`.
- Bump `cert-manager-app` from `3.3.0` to `3.5.0`.
- Bump `etcd-kubernetes-resources-count-exporter` from `1.4.0` to `1.7.0`.
- Bump `metrics-server-app` from `2.2.0` to `2.4.1`.
- Bump `net-exporter` from `1.17.0` to `1.18.0`.
- Bump `node-exporter-app` from `1.17.1` to `1.18.1`.
- Bump `observability-bundle` from `0.7.5` to `0.8.9`.
- Bump `vertical-pod-autoscaler-app` from `4.0.0` to `4.2.0`.

## [0.11.1] - 2023-09-21

### Added

- `podAnnotations` for `node-exporter` app to be able to collect systemd-related metrics.

## [0.11.0] - 2023-08-31

## [0.10.2] - 2023-08-29

### Fixed

- Update `cert-manager` parameters for v3.

## [0.10.1] - 2023-08-03

### Changed

- Bump `cert-manager-app` to `3.1.0`.

## [0.10.0] - 2023-08-03

### Added

- Add `etcd-kubernetes-resources-count-exporter`.

### Changed

- Remove override of dns Service name (not required for coredns-app).
- Bump `cert-manager-app` to `2.24.1`.

## [0.9.2] - 2023-05-22

### Changed

- Add support for deploying on clusters where network traffic is completely blocked by default with cilium.
- Update dependency giantswarm/observability-bundle to v0.6.0.

## [0.9.1] - 2023-05-22

### Changed

- Bump `observability-bundle` to `0.4.2`.

### Fixed

- Fix cluster DNS service name for `net-exporter` (`kube-dns` -> `coredns`).

## [0.9.0] - 2023-04-13

### Changed

- ⚠️ Breaking: Remove the deprecated `cluster-resources` app.
- Add `cert-manager`.
- Bump `vertical-pod-autoscaler-app` to `3.4.1`.
- Bump `vertical-pod-autoscaler-crd` to `2.0.1`.
- Bump `cert-exporter` to `2.4.0`.
- Bump `kube-state-metrics-app` to `1.15.0`.
- Bump `cert-manager-app` to `2.21.0`.
- Bump `metrics-server-app` to `2.1.0`.
- Bump `net-exporter` to `1.14.0`.
- Bump `observability-bundle` to `0.4.0`.
- Enable configuration of Apps with the [extraConfig](https://github.com/giantswarm/rfc/tree/main/multi-layer-app-config#enhancing-app-cr) key.

### Removed

- Remove kube-state-metrics app as it is now included in the observability-bundle.

## [0.8.0] - 2023-03-20

### Changed

- ⚠️ Breaking: Remove `cilium` and `cloud-provider-vsphere` app since they will be part of cluster-vsphere from now on.

## [0.7.0] - 2023-01-24

### Added

- Added `vertical-pod-autoscaler@2.5.3` & `vertical-pod-autoscaler-crd@1.0.1`.

### Changed

- Update `node-exporter` to `1.15.0`

## [0.6.0] - 2023-01-06

- Bump node-exporter-app to v1.14.1

### Added

- Added `application.giantswarm.io/app-type: "bundle"` annotation
- Added `observability-bundle` as default app
- Supports installing apps `inCluster`

### Changed

- Enable renovate to update app versions.

## [0.5.0] - 2022-05-17

### Changed

- Bump `cloud-provider-vsphere-app` to v1.3.0.

## [0.4.0] - 2022-05-17

### Changed

- Bump `cloud-provider-vsphere-app` to v1.2.0.

## [0.3.0] - 2022-05-17

### Changed

- Bump `cloud-provider-vsphere-app` to v1.1.0.

## [0.2.0] - 2022-05-17

### Added

- Add `cloud-provider-vsphere-app`.

## [0.1.2] - 2022-05-12

### Fixed

- Corrected a typo in an app version.

## [0.1.1] - 2022-05-11

### Changed

- Update templated labels to baseline standard.

## [0.1.0] - 2022-05-11

### Added

- Initialise repo from template.
- Add initial implementation without vSphere-specific apps.

[Unreleased]: https://github.com/giantswarm/default-apps-vsphere/compare/v0.16.0...HEAD
[0.16.0]: https://github.com/giantswarm/default-apps-vsphere/compare/v0.15.0...v0.16.0
[0.15.0]: https://github.com/giantswarm/default-apps-vsphere/compare/v0.14.0...v0.15.0
[0.14.0]: https://github.com/giantswarm/default-apps-vsphere/compare/v0.13.0...v0.14.0
[0.13.0]: https://github.com/giantswarm/default-apps-vsphere/compare/v0.12.1...v0.13.0
[0.12.1]: https://github.com/giantswarm/default-apps-vsphere/compare/v0.12.0...v0.12.1
[0.12.0]: https://github.com/giantswarm/default-apps-vsphere/compare/v0.11.3...v0.12.0
[0.11.3]: https://github.com/giantswarm/default-apps-vsphere/compare/v0.11.2...v0.11.3
[0.11.2]: https://github.com/giantswarm/default-apps-vsphere/compare/v0.11.1...v0.11.2
[0.11.1]: https://github.com/giantswarm/default-apps-vsphere/compare/v0.11.0...v0.11.1
[0.11.0]: https://github.com/giantswarm/default-apps-vsphere/compare/v0.10.2...v0.11.0
[0.10.2]: https://github.com/giantswarm/default-apps-vsphere/compare/v0.10.1...v0.10.2
[0.10.1]: https://github.com/giantswarm/default-apps-vsphere/compare/v0.10.0...v0.10.1
[0.10.0]: https://github.com/giantswarm/default-apps-vsphere/compare/v0.9.2...v0.10.0
[0.9.2]: https://github.com/giantswarm/default-apps-vsphere/compare/v0.9.1...v0.9.2
[0.9.1]: https://github.com/giantswarm/default-apps-vsphere/compare/v0.9.0...v0.9.1
[0.9.0]: https://github.com/giantswarm/default-apps-vsphere/compare/v0.8.0...v0.9.0
[0.8.0]: https://github.com/giantswarm/default-apps-vsphere/compare/v0.7.0...v0.8.0
[0.7.0]: https://github.com/giantswarm/default-apps-vsphere/compare/v0.6.0...v0.7.0
[0.6.0]: https://github.com/giantswarm/default-apps-vsphere/compare/v0.5.0...v0.6.0
[0.5.0]: https://github.com/giantswarm/default-apps-vsphere/compare/v0.4.0...v0.5.0
[0.4.0]: https://github.com/giantswarm/default-apps-vsphere/compare/v0.3.0...v0.4.0
[0.3.0]: https://github.com/giantswarm/default-apps-vsphere/compare/v0.2.0...v0.3.0
[0.2.0]: https://github.com/giantswarm/default-apps-vsphere/compare/v0.1.2...v0.2.0
[0.1.2]: https://github.com/giantswarm/default-apps-vsphere/compare/v0.1.1...v0.1.2
[0.1.1]: https://github.com/giantswarm/default-apps-vsphere/compare/v0.1.0...v0.1.1
[0.1.0]: https://github.com/giantswarm/default-apps-vsphere/releases/tag/v0.1.0
