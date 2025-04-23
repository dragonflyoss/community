# Release Procedure

This document outlines the release procedure for Dragonfly, including the steps to prepare for a release, the release process itself.
The goal is to ensure a smooth and efficient release process while maintaining high quality and stability in the software.

## Overview

Dragonfly is built and released to Github using [Go Releaser](https://goreleaser.com/). Go Releaser will run in the CI/CD pipeline and create
the release artifacts, including binaries, Docker images, and other necessary files which provide a hermetic environment that prevents build
contamination from the host environment.

## Prepare Environment

1. Install [git-chglog](https://github.com/git-chglog/git-chglog) to generate the changelog for the minor and patch releases.
2. Install [pre-commit](https://github.com/pre-commit/pre-commit) to run the pre-commit hooks for the release process.
3. Install [helm-docs](https://github.com/norwoodj/helm-docs) to generate the documentation for the helm chart.

## Create Release

### Create New Major Release

To create a new major release, follow these steps:

1. **Create a new tag from release branch**: Create a new tag from the release branch (e.g., `v3.0.0`) using the following command:

   Clone the `dragonfly` repository.

   ```bash
   git clone git@github.com:dragonflyoss/dragonfly.git
   cd dragonfly
   ```

   Create a new tag from the release branch.

   ```bash
   git checkout release-3.0
   git tag v3.0.0
   ```

2. **Update the version in `version.go`**: Update the go version in `version.go` file.

   ```go
   hack/update-version-gorelease.sh
   ```

3. **Generate the ChangeLog**: Generate the changelog using the following command:

   ```bash
   make changelog
   ```

4. **Push the tag**: Push the tag to the remote repository using the following command:

   ```bash
   git push origin v3.0.0
   ```

5. **Wait for the CI/CD pipeline**: Wait for the CI/CD pipeline to complete. The pipeline will create the release artifacts, including binaries, Docker images, and other necessary files.

Release pipeline will be triggered automatically when a new tag is pushed to the repository and release pipeline is configured in the `.github/workflows/release.yml` file.
Release pipeline link is <https://github.com/dragonflyoss/dragonfly/actions/workflows/release.yml>, wait for the pipeline to complete and check the logs for any errors.
If the pipeline finished, it will create a new release in the GitHub repository with the tag name and release notes.

6. **Create a new release**: Create a new release in the GitHub repository flowing the steps below:

Enter the [release page](https://github.com/dragonflyoss/dragonfly/releases) in the GitHub repository, and click the "edit" button to add the release notes
and release the new version. Major release should not use the `git-chglog` to generate the release notes and need to be manually edited.

7. **Archive the documentation of the old version**: Archive the documentation of the old version in the [d7y.io](https://github.com/dragonflyoss/d7y.io) repository.
   The documentation should be archived in a separate directory with the version number.

   Clone the `d7y.io` repository.

   ```bash
   git clone git@github.com:dragonflyoss/d7y.io.git
   cd d7y.io
   ```

   Install npm dependencies.

   ```bash
   npm install
   ```

   Archive the documentation of the old version, parmeter `v3.0.0` is the new release version.

   ```bash
   npm run version v3.0.0
   ```

   Push the changes to the `d7y.io` repository.

   ```bash
   git add .
   git commit -m "chore: archive the documentation of v3.0.0"
   git push origin main
   ```

   Merge the pull request to the `d7y.io` repository.

8. **Update image version of Helm Chart**: Update the image version of [helm-charts](https://github.com/dragonflyoss/helm-charts) in the `charts` directory.
   The image version should be updated to the new release version.

   ```bash
   git clone git@github.com:dragonflyoss/helm-charts.git
   cd helm-charts
   ```

   Update the image version in the `charts/dragonfly/values.yaml` file.

   ```yaml
   manager:
     image:
       tag: v3.0.0
   scheduler:
     image:
       tag: v3.0.0
   client:
     image:
       tag: v0.3.0
   seedClient:
     image:
       tag: v0.3.0
   ```

   Update the image version in the `charts/dragonfly/Chart.yaml` file.

   ```yaml
   version: 2.0.0
   appVersion: 3.0.0
   annotations:
     artifacthub.io/changes: |
       - Bump dragonfly version to v3.0.0.
     artifacthub.io/images: |
       - name: manager
         image: dragonflyoss/manager:v3.0.0
       - name: scheduler
         image: dragonflyoss/scheduler:v3.0.0
       - name: client
         image: dragonflyoss/client:v0.3.0
       - name: seed-client
         image: dragonflyoss/client:v0.3.0
       - name: dfinit
         image: dragonflyoss/dfinit:v0.3.0
   ```

   Push the changes to the `helm-charts` repository.

   ```bash
   git add .
   git commit -m "chore: bump dragonfly from v2.1.0 to v3.0.0"
   git push origin main
   ```

   Merge the pull request to the `helm-charts` repository.

9. **Announce the new release**

Announce the new release on the Dragonfly mailing list <dragonfly-discuss@googlegroups.com> and the Slack channel
[#dragonfly](https://cloud-native.slack.com/messages/dragonfly/) on [CNCF Slack](https://slack.cncf.io/).

And publish the release note on CNCF blog, refer to [Dragonfly v2.2.0 has been released](https://www.cncf.io/blog/2025/01/07/dragonfly-v2-2-0-has-been-released/).
The release manager will also publish the release note on the X (formerly Twitter) account [@dragonfly_oss](https://twitter.com/dragonfly_oss).

### Create New Minor Release

To create a new minor release, follow these steps:

1. **Create a new tag from release branch**: Create a new tag from the release branch (e.g., `v2.2.0`) using the following command:

   ```bash
   git checkout release-2.2
   git tag v2.2.0
   ```

2. **Update the version in `version.go`**: Update the go version in `version.go` file.

   ```go
   hack/update-version-gorelease.sh
   ```

3. **Generate the ChangeLog**: Generate the changelog using the following command:

   ```bash
   make changelog
   ```

4. **Push the tag**: Push the tag to the remote repository using the following command:

   ```bash
   git push origin v2.2.0
   ```

5. **Wait for the CI/CD pipeline**: Wait for the CI/CD pipeline to complete. The pipeline will create the release artifacts, including binaries, Docker images, and other necessary files.

Release pipeline will be triggered automatically when a new tag is pushed to the repository and release pipeline is configured in the `.github/workflows/release.yml` file.
Release pipeline link is <https://github.com/dragonflyoss/dragonfly/actions/workflows/release.yml>, wait for the pipeline to complete and check the logs for any errors.
If the pipeline finished, it will create a new release in the GitHub repository with the tag name and release notes.

6. **Create a new release**: Create a new release in the GitHub repository following the steps below:

Enter the [release page](https://github.com/dragonflyoss/dragonfly/releases) in the GitHub repository, and click the "edit" button to add the release notes
and release the new version. Minor release should not use the `git-chglog` to generate the release notes and need to be manually edited.

7. **Archive the documentation of the old version**: Archive the documentation of the old version in the [d7y.io](https://github.com/dragonflyoss/d7y.io) repository.
   The documentation should be archived in a separate directory with the version number.

   Clone the `d7y.io` repository.

   ```bash
   git clone git@github.com:dragonflyoss/d7y.io.git
   cd d7y.io
   ```

   Install npm dependencies.

   ```bash
   npm install
   ```

   Archive the documentation of the old version, parmeter `v2.2.0` is the new release version.

   ```bash
   npm run version v2.2.0
   ```

   Push the changes to the `d7y.io` repository.

   ```bash
   git add .
   git commit -m "chore: archive the documentation of v2.2.0"
   git push origin main
   ```

   Merge the pull request to the `d7y.io` repository.

8. **Update image version of Helm Chart**: Update the image version of [helm-charts](https://github.com/dragonflyoss/helm-charts) in the `charts` directory.
   The image version should be updated to the new release version.

   ```bash
   git clone git@github.com:dragonflyoss/helm-charts.git
   cd helm-charts
   ```

   Update the image version in the `charts/dragonfly/values.yaml` file.

   ```yaml
   manager:
     image:
       tag: v2.2.0
   scheduler:
     image:
       tag: v2.2.0
   client:
     image:
       tag: v0.3.0
   seedClient:
     image:
       tag: v0.3.0
   ```

   Update the image version in the `charts/dragonfly/Chart.yaml` file.

   ```yaml
   version: 1.1.0
   appVersion: 2.2.0
   annotations:
     artifacthub.io/changes: |
       - Bump dragonfly version to v2.2.0.
     artifacthub.io/images: |
       - name: manager
         image: dragonflyoss/manager:v2.2.0
       - name: scheduler
         image: dragonflyoss/scheduler:v2.2.0
       - name: client
         image: dragonflyoss/client:v0.3.0
       - name: seed-client
         image: dragonflyoss/client:v0.3.0
       - name: dfinit
         image: dragonflyoss/dfinit:v0.3.0
   ```

   Push the changes to the `helm-charts` repository.

   ```bash
   git add .
   git commit -m "chore: bump dragonfly from v2.1.0 to v2.2.0"
   git push origin main
   ```

   Merge the pull request to the `helm-charts` repository.

9. **Announce the new release**

Announce the new release on the Dragonfly mailing list <dragonfly-discuss@googlegroups.com> and the Slack channel
[#dragonfly](https://cloud-native.slack.com/messages/dragonfly/) on [CNCF Slack](https://slack.cncf.io/).

And publish the release note on CNCF blog, refer to [Dragonfly v2.2.0 has been released](https://www.cncf.io/blog/2025/01/07/dragonfly-v2-2-0-has-been-released/).
The release manager will also publish the release note on the X (formerly Twitter) account [@dragonfly_oss](https://twitter.com/dragonfly_oss).

### Create New Patch Release

To create a new patch release, follow these steps:

1. **Create a new tag from release branch**: Create a new tag from the release branch (e.g., `v2.2.1`) using the following command:

   ```bash
   git checkout release-2.2
   git tag v2.2.1
   ```

2. **Update the version in `version.go`**: Update the go version in `version.go` file.

   ```go
   hack/update-version-gorelease.sh
   ```

3. **Generate the ChangeLog**: Generate the changelog using the following command:

   ```bash
   make changelog
   ```

4. **Push the tag**: Push the tag to the remote repository using the following command:

   ```bash
   git push origin v2.2.1
   ```

5. **Wait for the CI/CD pipeline**: Wait for the CI/CD pipeline to complete. The pipeline will create the release artifacts, including binaries, Docker images, and other necessary files.

Release pipeline will be triggered automatically when a new tag is pushed to the repository and release pipeline is configured in the `.github/workflows/release.yml` file.
Release pipeline link is <https://github.com/dragonflyoss/dragonfly/actions/workflows/release.yml>, wait for the pipeline to complete and check the logs for any errors.
If the pipeline finished, it will create a new release in the GitHub repository with the tag name and release notes.

6. **Create a new release**: Create a new release in the GitHub repository flowing the steps below:

Enter the [release page](https://github.com/dragonflyoss/dragonfly/releases) in the GitHub repository, and click the "edit" button to release the new version.

7. **Update image version of Helm Chart**: Update the image version of [helm-charts](https://github.com/dragonflyoss/helm-charts) in the `charts` directory.
   The image version should be updated to the new release version.

   ```bash
   git clone git@github.com:dragonflyoss/helm-charts.git
   cd helm-charts
   ```

   Update the image version in the `charts/dragonfly/values.yaml` file.

   ```yaml
   manager:
     image:
       tag: v2.2.1
   scheduler:
     image:
       tag: v2.2.1
   client:
     image:
       tag: v0.3.0
   seedClient:
     image:
       tag: v0.3.0
   ```

   Update the image version in the `charts/dragonfly/Chart.yaml` file.

   ```yaml
   version: 1.1.1
   appVersion: 2.2.1
   annotations:
     artifacthub.io/changes: |
       - Bump dragonfly version to v2.2.1.
     artifacthub.io/images: |
       - name: manager
         image: dragonflyoss/manager:v2.2.1
       - name: scheduler
         image: dragonflyoss/scheduler:v2.2.1
       - name: client
         image: dragonflyoss/client:v0.3.0
       - name: seed-client
         image: dragonflyoss/client:v0.3.0
       - name: dfinit
         image: dragonflyoss/dfinit:v0.3.0
   ```

   Push the changes to the `helm-charts` repository.

   ```bash
   git add .
   git commit -m "chore: bump dragonfly from v2.1.0 to v2.2.0"
   git push origin main
   ```

   Merge the pull request to the `helm-charts` repository.

### Create a New Release Candidate Release

To create a new patch release, follow these steps:

1. **Create a new tag from release branch**: Create a new tag from the release branch (e.g., `v2.2.1-rc.0`) using the following command:

   ```bash
   git checkout release-2.2
   git tag v2.2.1-rc.0
   ```

2. **Update the version in `version.go`**: Update the go version in `version.go` file.

   ```go
   hack/update-version-gorelease.sh
   ```

3. **Generate the ChangeLog**: Generate the changelog using the following command:

   ```bash
   make changelog
   ```

4. **Push the tag**: Push the tag to the remote repository using the following command:

   ```bash
   git push origin v2.2.1-rc.0
   ```

5. **Wait for the CI/CD pipeline**: Wait for the CI/CD pipeline to complete. The pipeline will create the release artifacts, including binaries, Docker images, and other necessary files.

Release pipeline will be triggered automatically when a new tag is pushed to the repository and release pipeline is configured in the `.github/workflows/release.yml` file.
Release pipeline link is <https://github.com/dragonflyoss/dragonfly/actions/workflows/release.yml>, wait for the pipeline to complete and check the logs for any errors.
If the pipeline finished, it will create a new release in the GitHub repository with the tag name and release notes.

6. **Create a new release**: Create a new release in the GitHub repository flowing the steps below:

Enter the [release page](https://github.com/dragonflyoss/dragonfly/releases) in the GitHub repository, and click the "edit" button to release the new version.

### Create a New Alpha and Beta Release

To create a new patch release, follow these steps:

1. **Create a new tag from release branch**: Create a new tag from the main branch (e.g., `v2.2.1-alpha.0`) using the following command:

   ```bash
   git checkout main
   git tag v2.2.1-alpha.0
   ```

2. **Update the version in `version.go`**: Update the go version in `version.go` file.

   ```go
   hack/update-version-gorelease.sh
   ```

3. **Generate the ChangeLog**: Generate the changelog using the following command:

   ```bash
   make changelog
   ```

4. **Push the tag**: Push the tag to the remote repository using the following command:

   ```bash
   git push origin v2.2.1-alpha.0
   ```

5. **Wait for the CI/CD pipeline**: Wait for the CI/CD pipeline to complete. The pipeline will create the release artifacts, including binaries, Docker images, and other necessary files.

Release pipeline will be triggered automatically when a new tag is pushed to the repository and release pipeline is configured in the `.github/workflows/release.yml` file.
Release pipeline link is <https://github.com/dragonflyoss/dragonfly/actions/workflows/release.yml>, wait for the pipeline to complete and check the logs for any errors.
If the pipeline finished, it will create a new release in the GitHub repository with the tag name and release notes.

6. **Create a new release**: Create a new release in the GitHub repository flowing the steps below:

Enter the [release page](https://github.com/dragonflyoss/dragonfly/releases) in the GitHub repository, and click the "edit" button to release the new version.
