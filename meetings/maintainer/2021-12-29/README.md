# Maintainer Meeting

## Attendees

- [allencloud](https://github.com/allencloud)
- [garfield009](https://github.com/garfield009)
- [244372610](https://github.com/244372610)
- [qwtsc](https://github.com/qwtsc)
- [lucy-cl](https://github.com/lucy-cl)
- [jim3ma](https://github.com/jim3ma)
- [gaius-qi](https://github.com/gaius-qi)
- [zzy987](https://github.com/zzy987)
- [yxxhero](https://github.com/yxxhero)

## Progress

- ***gaius-qi***: Refactor scheduler service, discover and fix problems at the same time in the testing phase.

- ***244372610***: Refactor GRPC connection pool management and completed balancer and picker features.

- ***yxxhero***: Designing application feature.

- ***zzy987***: GRPC integrates `grpc-middleware/retry` library for retry.

- ***qwtsc***: Build a stress testing environment and log collection uses `filebeat` + `elasticsearch` + `kibana`.

## Topics

- GRPC and HTTP server use the same port - 244372610
  - There is no need to use a same port

- GRPC service reslover directly request manager server - 244372610
  - needs to provide a complete solution and specific sequence diagram.

## Other Business
