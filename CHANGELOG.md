# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

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

[Unreleased]: https://github.com/giantswarm/default-apps-vsphere/compare/v0.6.0...HEAD
[0.6.0]: https://github.com/giantswarm/default-apps-vsphere/compare/v0.5.0...v0.6.0
[0.5.0]: https://github.com/giantswarm/default-apps-vsphere/compare/v0.4.0...v0.5.0
[0.4.0]: https://github.com/giantswarm/default-apps-vsphere/compare/v0.3.0...v0.4.0
[0.3.0]: https://github.com/giantswarm/default-apps-vsphere/compare/v0.2.0...v0.3.0
[0.2.0]: https://github.com/giantswarm/default-apps-vsphere/compare/v0.1.2...v0.2.0
[0.1.2]: https://github.com/giantswarm/default-apps-vsphere/compare/v0.1.1...v0.1.2
[0.1.1]: https://github.com/giantswarm/default-apps-vsphere/compare/v0.1.0...v0.1.1
[0.1.0]: https://github.com/giantswarm/default-apps-vsphere/releases/tag/v0.1.0
