# Release Planning

This document outlines Dragonfly process for planning and scheduling releases, so you can familiarize yourself with the flow of work from opening an issue to seeing it published in a release. We aim to ship updates to production approximately every 6 months, to ensure a continuous flow of improvements to our users.

## Release Version

All release artifacts must follow [Semantic Versioning](https://semver.org). Each release milestone increments the minor version. In exceptional cases, the major version can be increased too.

### Tag Naming Convention

Milestones and Release tags are followed [Semantic Versioning](https://semver.org).

We organize Release tags in two ways:

- Stable releases are tagged with a version number:
  - **for example: v2.1.0, v2.2.0, etc.**
- Pre-release versions are tagged with a version number and a suffix:
  - **for example: v2.1.0-alpha.x, v2.1.0-beta.x, v2.1.0-rc.x, etc.**

### Stable Branch Naming Convention

Stable branches correspond to specific release milestones and use the format `release-<major>.<minor>`. For example, the stable branch for
the `2.1` milestone is named `release-2.1`.

- Alpha, and Beta tags are created from the main branch. For instance, the alpha tag `v2.1.0-alpha.0` would be created from the `main` branch.
- Release-Candidate tags are created from these stable branches. For instance, the release tag `v2.1.1-rc.0` would be created from the `release-2.1` branch.
- Release tags are created from these stable branches. For instance, the release tag `v2.1.1` would be created from the `release-2.1` branch.

## Release Milestone

The Dragonfly project maintains a dynamic development cycle, addressing both existing feature bugs and implementing new functionalities. Each release follows a structured 26-week (6-month) timeline, divided into three key phases:

- Feature definition (~ 4 weeks)
- Feature implementation (~ 18 weeks)
- Stabilization and release (~ 4 weeks)

Given the complexity of significant features, their full integration often spans multiple release cycles. As a release nears completion, it's not uncommon for complex features to be rescheduled for the subsequent milestone. This approach ensures each feature meets the rigorous requirements of the project's feature lifecycle, maintaining the high quality standards of the Dragonfly project.

## Release Lifecycle

The release lifecycle is a structured process that ensures the quality and stability of Dragonfly releases. It consists of several key phases:

1. **Stabilization Phase**: This phase concentrates on fixing bugs and ensuring the stability of the upcoming release. It spans the 4 weeks
   leading up to the Release Date, starting with the Code Freeze. The Code Freeze takes place 4 weeks before the scheduled Release Date,
   at which point a dedicated release branch is created from the main branch. During this stabilization period, only bug fixes are merged into
   the release branch, while new features continue to be integrated into the main branch.

2. **Maintenance Phase**: During this phase, the release is maintained, and critical bugs are addressed. This phase lasts for 6 months,
   starting from the current version Release date and continuing until the next version is released. However, maintenance support is provided
   only for the immediately preceding version. For example, release-2.1 branch is kept open for bug fixes, and the main branch is used for
   v2.2 features and improvements.

### Stabilization Phase

Stabilization is a critical phase in the release lifecycle, focusing on ensuring the quality and stability of the upcoming release. It spans the 4 weeks leading up to the Release Date, starting with the Code Freeze.

#### Bug Fixes

During the stabilization phase, only bug fixes are merged into the release branch. This approach allows for a clear separation between
ongoing development and the stabilization of the release. The bug fixes need to be merged into the main branch first, and then cherry-picked
into the release branch.

#### Release Procedure(WIP)

If the release branch is stable and the final time is reached, the release manager will create a release tag from the release branch.

#### Announcement

The release manager will announce the release on the Dragonfly mailing list <dragonfly-discuss@googlegroups.com> and the Slack channel
[#dragonfly](https://cloud-native.slack.com/messages/dragonfly/) on [CNCF Slack](https://slack.cncf.io/).

And publish the release note on CNCF blog, refer to [Dragonfly v2.2.0 has been released](https://www.cncf.io/blog/2025/01/07/dragonfly-v2-2-0-has-been-released/).
The release manager will also publish the release note on the X (formerly Twitter) account [@dragonfly_oss](https://twitter.com/dragonfly_oss).

### Maintenance Phase

The maintenance phase ensures that the release remains stable and secure after its initial launch. This phase lasts for 6 months, starting from the current version Release date and continuing until the next version is released.

#### Bug Fixes

During the maintenance phase, only critical bug fixes are merged into the maintenance release branch.
The bug fixes need to be merged into the main branch first, and then cherry-picked into the maintenance release branch.

#### Patch Release

During the maintenance phase, if a critical bug is found, the release manager will create a patch release.
The patch release will be tagged with a version number and a suffix, such as `v2.1.1`, `v2.1.2`, etc.

#### End of Life

The maintenance phase lasts for 6 months, and after that, the release branch will be archived.

## Release Note

[Dragonfly Maintainers](https://github.com/dragonflyoss/dragonfly/blob/main/MAINTAINERS.md) from different companies take turns to prepare key information such as [release notes](https://github.com/dragonflyoss/dragonfly/releases/tag/v2.2.0).

## Release Team

The release team has the responsibility of enforcing processes to ensure the release is successfully delivered. The release team consists of the following roles:

- **Release manager.** This role oversees enforcing the processes for a release and ensuring communication to all contributors and community on the ongoing status of the release. For each release, one release manager is selected from each participating company.
