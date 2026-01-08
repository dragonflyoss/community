# Dragonfly v2.4.0 is released

Dragonfly v2.4.0 is released!🎉🎉🎉 Thanks the [contributors](https://github.com/dragonflyoss/dragonfly/graphs/contributors) who made this release happend and welcome you to visit [d7y.io](https://d7y.io) website.

![dragonfly](images/dragonfly-linear.png)

## Features

### Scheduling

### Simple Multi‑Cluster Kubernetes Deployment with Scheduler Cluster ID

Dragonfly supports a simplified feature for deploying and managing multiple Kubernetes clusters by explicitly assigning a `schedulerClusterID` to each cluster.
This approach allows users to directly control cluster affinity without relying on location‑based scheduling metadata such as IDC, hostname, or IP.

Using this feature, each Peer, Seed Peer, and Scheduler determines its target scheduler cluster through a clearly defined scheduler cluster ID.
This ensures precise separation between clusters and predictable cross‑cluster behavior.

![p1](images/p1.png)

For more information, please refer to the [Create Dragonfly Cluster Simple](https://d7y.io/docs/next/getting-started/quick-start/multi-cluster-kubernetes/#create-dragonfly-cluster-simple).

### Performance and Resource Optimization for Manager and Scheduler Components

Enhanced service performance and resource utilization across Manager and Scheduler components while significantly reducing
CPU and memory overhead, delivering improved system efficiency and better resource management.

### Enhanced Preheating

- Support for IP-based peer selection in preheating jobs with priority-based selection logic where IP specification
  takes highest priority, followed by count-based and percentage-based selection

- Support for preheating multiple URLs in a single request.

- Support for preheating file and image via Scheduler gRPC interface.

![p2](images/p2.png)

### Calculate task ID based on image blob SHA256 to avoid redundant downloads

The Client now supports calculating task IDs directly from the SHA256 hash of image blobs instead of using the download URL.
This enhancement prevents redundant downloads and data duplication when the same blob is accessed from
different registry domains.

### Cache HTTP 307 redirects for split downloads

Added support for caching HTTP 307 (Temporary Redirect) responses to optimize Dragonfly's multi-piece download performance.
When a download URL is split into multiple pieces, the redirect target is now cached,
eliminating redundant redirect requests and reducing latency.

### Go Client Deprecated and Replaced by Rust Client

The Go client has been deprecated and replaced by the [Rust Client](https://github.com/dragonflyoss/client). All future development and maintenance will focus
exclusively on the Rust client, which offers improved performance, stability, and reliability.

For more information, please refer to the [dragoflyoss/client](https://github.com/dragonflyoss/client).

## Nydus

### New features and enhancements

## Significant bug fixes

- Modified the database field type from `text` to `longtext` to support storing the information of preheating job.
- Fixed panic on repeated seed peer service stops during Scheduler shutdown.
- Fixed broker authentication failure when specifying the Redis password without setting a username.

## Others

You can see [CHANGELOG](https://github.com/dragonflyoss/dragonfly/blob/main/CHANGELOG.md) for more details.

## Links

- Dragonfly Website: <https://d7y.io/>
- Dragonfly Repository: <https://github.com/dragonflyoss/dragonfly>
- Dragonfly Client Repository: <https://github.com/dragonflyoss/client>
- Dragonfly Console Repository: <https://github.com/dragonflyoss/console>
- Dragonfly Charts Repository: <https://github.com/dragonflyoss/helm-charts>
- Dragonfly Monitor Repository: <https://github.com/dragonflyoss/monitoring>

## Dragonfly Github

![qrcode](images/qrcode.webp)
