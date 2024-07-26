# Release Planning

This document outlines Dragonfly process for planning and scheduling releases, so you can familiarize yourself with the flow of work from opening an issue to seeing it published in a release. We aim to ship updates to production approximately every 6 months, to ensure a continuous flow of improvements to our users. 

## Release version

All release artifacts must follow [Semantic Versioning](https://semver.org). Each release milestone increments the minor version. In exceptional cases, the major version can be increased too.

We organize releases in two ways - marketing and milestones:

 - Marketing releases are what we use to represent stable version.
      - **for example: v2.1, v2.2, etc.**
 - Milestones are used to track issues and pull requests associated with an upcoming release, and can be [followed on GitHub](https://github.com/Dragonflyoss/Dragonfly2/milestones)
      - **for example: v2.1.x, v2.1.0-alpha.x, v2.1.0-beta.x, etc.**

Hotfixes should also be applied directly into each of the impacted release branches. Then, the fix can be merged back into master (or main) branch or cherry-picked.

## Release milestone

The Dragonfly project maintains a dynamic development cycle, addressing both existing feature bugs and implementing new functionalities. Each release follows a structured 26-week (6-month) timeline, divided into three key phases:
-	Feature definition (~ 4 weeks)
-	Feature implementation (~ 18 weeks)
-	Stabilization and release (~ 4 weeks)

Given the complexity of significant features, their full integration often spans multiple release cycles. As a release nears completion, it's not uncommon for complex features to be rescheduled for the subsequent milestone. This approach ensures each feature meets the rigorous requirements of the project's feature lifecycle, maintaining the high quality standards of the Dragonfly project.

## Release note

[Dragonfly Maintainers](https://github.com/dragonflyoss/Dragonfly2/blob/main/MAINTAINERS.md) from different companies take turns to prepare key information such as [release notes](https://d7y.io/docs/next/roadmap-v2.2/).

## Release team

The release team has the responsibility of enforcing processes to ensure the release is successfully delivered. The release team consists of the following roles:

-	**Release manager.**  This role oversees enforcing the processes for a release and ensuring communication to all contributors and community on the ongoing status of the release. For each release, one release manager is selected from each participating company.
