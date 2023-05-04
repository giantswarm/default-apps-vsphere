# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Changed

- Add support for deploying on clusters where network traffic is completely blocked by default with cilium.
- Bump `observability-bundle` to `0.4.2`.

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

[Unreleased]: https://github.com/giantswarm/default-apps-vsphere/compare/v0.9.0...HEAD
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
