# Dragonfly v2.4.0 is released

Dragonfly v2.4.0 is released!🎉🎉🎉 Thanks the [contributors](https://github.com/dragonflyoss/dragonfly/graphs/contributors) who made this release happend and welcome you to visit [d7y.io](https://d7y.io) website.

![dragonfly](images/dragonfly-linear.png)

## New features and enhancements

### load-aware scheduling algorithm

A two-stage scheduling algorithm combining central scheduling with node-level secondary scheduling to
optimize P2P download performance based on real-time load awareness.

![p1](images/p1.svg)

For more information, please refer to the [Scheduling](https://d7y.io/docs/next/operations/deployment/applications/scheduler/#scheduling).

### Vortex Protocol Support for P2P File Transfer

Dragonfly provide the new Vortex transfer protocol based on TLV to improve the download performance in internal network.
Use the TLV (Tag-Length-Value) format as a lightweight protocol to replace GRPC for data transfer between peers.
TCP-based Vortex reduces large file download time by `50%` and QUIC-based Vortex by `40%` compared to gRPC, both effectively reducing peak memory usage.

For more information, please refer to the [TCP Protocol Support for P2P File Transfer](https://github.com/dragonflyoss/design/blob/main/systems-analysis/tcp-protocol/tcp-protocol.md) and [QUIC Protocol Support for P2P File Transfer](https://github.com/dragonflyoss/design/blob/main/systems-analysis/quic-protocol/quic-protocol.md).

### Rust Request SDK

### Simple Multi‑Cluster Kubernetes Deployment with Scheduler Cluster ID

Dragonfly supports a simplified feature for deploying and managing multiple Kubernetes clusters by explicitly assigning a `schedulerClusterID` to each cluster.
This approach allows users to directly control cluster affinity without relying on location‑based scheduling metadata such as IDC, hostname, or IP.

Using this feature, each Peer, Seed Peer, and Scheduler determines its target scheduler cluster through a clearly defined scheduler cluster ID.
This ensures precise separation between clusters and predictable cross‑cluster behavior.

![p2](images/p2.png)

For more information, please refer to the [Create Dragonfly Cluster Simple](https://d7y.io/docs/next/getting-started/quick-start/multi-cluster-kubernetes/#create-dragonfly-cluster-simple).

### Performance and Resource Optimization for Manager and Scheduler Components

Enhanced service performance and resource utilization across Manager and Scheduler components while significantly reducing
CPU and memory overhead, delivering improved system efficiency and better resource management.

### Enhanced Preheating

- Support for IP-based peer selection in preheating jobs with priority-based selection logic where IP specification
  takes highest priority, followed by count-based and percentage-based selection

- Support for preheating multiple URLs in a single request.

- Support for preheating file and image via Scheduler gRPC interface.

![p3](images/p3.png)

### Calculate task ID based on image blob SHA256 to avoid redundant downloads

The Client now supports calculating task IDs directly from the SHA256 hash of image blobs instead of using the download URL.
This enhancement prevents redundant downloads and data duplication when the same blob is accessed from
different registry domains.

### Cache HTTP 307 redirects for split downloads

Support for caching HTTP 307 (Temporary Redirect) responses to optimize Dragonfly's multi-piece download performance.
When a download URL is split into multiple pieces, the redirect target is now cached,
eliminating redundant redirect requests and reducing latency.

### Go Client Deprecated and Replaced by Rust Client

The Go client has been deprecated and replaced by the [Rust Client](https://github.com/dragonflyoss/client). All future development and maintenance will focus
exclusively on the Rust client, which offers improved performance, stability, and reliability.

For more information, please refer to the [dragoflyoss/client](https://github.com/dragonflyoss/client).

### Additional Enhancements

- Enable 64K page size support for ARM64 in the Dragonfly Rust client.
- Fix missing git commit metadata in dfget version output.
- Support for `config_path` of `io.containerd.cri.v1.images` plugin for containerd V3 configuration.
- Replaces glibc DNS resolver with hickory-dns in reqwest to implement DNS caching and prevent excessive DNS lookups during piece downloads.
- Support for the --include-files flag to selectively download files from a directory.
- Add the `--no-progress flag` to disable the download progress bar output.
- Support for custom request headers in backend operations, enabling flexible header configuration for HTTP requests.
- Refactored log output to reduce redundant logging and improve overall logging efficiency.

## Significant bug fixes

- Modified the database field type from `text` to `longtext` to support storing the information of preheating job.
- Fixed panic on repeated seed peer service stops during Scheduler shutdown.
- Fixed broker authentication failure when specifying the Redis password without setting a username.

## Nydus

### New features and enhancements

- Nydusd: Add CRC32 validation support for both RAFS V5 and V6 formats, enhancing data integrity verification.
- Nydusd: Support resending FUSE requests during nydusd restoration, improving daemon recovery reliability.
- Nydusd: Enhance VFS state saving mechanism for daemon hot upgrade and failover.
- Nydusify: Introduce Nydus-to-OCI reverse conversion capability, enabling seamless migration back to OCI format.
- Nydusify: Implement zero-disk transfer for image copy, significantly reducing local disk usage during copy operations.
- Snapshotter: Builtin blob.meta in bootstrap for blob fetch reliability for RAFS v6 image.

### Significant bug fixes

- Nydusd: Fix auth token fetching for `access_token` field in registry authentication.
- Nydusd: Add recursive inode/dentry invalidation for umount API.
- Nydus Image: Fix multiple issues in optimize subcommand and add backend configuration support.
- Snapshotter: Implement lazy parent recovery for proxy mode to handle missing parent snapshots.

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
