# Dragonfly v2.4.0 is released

Dragonfly v2.4.0 is released!🎉🎉🎉 Thanks the [contributors](https://github.com/dragonflyoss/dragonfly/graphs/contributors) who made this release happend and welcome you to visit [d7y.io](https://d7y.io) website.

![dragonfly](images/dragonfly-linear.png)

## Features

### Support for OpenTelemetry Tracing

Dragonfly supports for tracing based on OpenTelemetry, covering the Manager, Scheduler, and Peers. This enables end-to-end visibility into the download process, allowing users to query detailed information, such as overall download latency, using a specific task ID. The integration ensures efficient monitoring and performance analysis across the entire system.

Add tracing configuration as follows(in Manager, Scheduler and Peer):

![p11](images/p11.webp)

You can access the Jaeger UI to visualize the traces.

![p12](images/p12.webp)

For more information, please refer to the [Tracing](https://d7y.io/docs/next/operations/best-practices/observability/tracing/).

## Security Enhancements

We extend our sincere gratitude to the [CNCF TAG Security](https://tag-security.cncf.io/) for their collaboration on a joint security audit. Their expertise and thorough review were invaluable in helping us identify areas for security improvement within Dragonfly.
For detailed information on the specific security issues addressed and the corresponding fixes, please refer to the following issue: <https://github.com/dragonflyoss/dragonfly/issues/3811>

## Nydus

### New features and enhancements

- nydusify copy: support chunked upload and retry mechanisms to handle large image blobs.
- nydusify check: refactor to support OCI v1 and nydus format images as both source and target.
- nydusd: support chunk-level CRC data validation for image data consistency.

## Significant bug fixes

- Fixed memory leaks and file descriptor leaks caused by `sysinfo` library.
- Cleans up the Unix domain socket (UDS) to prevent dfdaemon startup crashes.
- Prevent client from repeatedly downloading the same piece from multiple parents.

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

![p13](images/qrcode.webp)
