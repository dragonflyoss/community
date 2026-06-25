# Dragonfly v2.5.0 发布了

Dragonfly v2.5.0 发布了！🎉🎉🎉 感谢为此版本做出贡献的[贡献者们](https://github.com/dragonflyoss/dragonfly/graphs/contributors)，欢迎访问 [d7y.io](https://d7y.io) 网站。

![dragonfly](images/dragonfly-linear.png)

## 新增特性

### 支持直接拉取 Hugging Face 和 ModelScope 仓库

Dragonfly 客户端现已支持直接下载 Hugging Face 和 ModelScope 的模型仓库。用户可以使用 `dfget hf://deepseek-ai/DeepSeek-OCR` 和 `dfget modelscope://models/deepseek-ai/DeepSeek-OCR` 等命令拉取仓库。
其中 Git LFS 数据通过 Dragonfly P2P 加速下载，其他仓库元数据则继续通过 Git 协议获取。

![p1](images/p1.png)

更多信息，请参阅 [Hugging Face 仓库下载](https://github.com/dragonflyoss/dragonfly/issues/4419) 和 [ModelScope 仓库下载](https://github.com/dragonflyoss/dragonfly/issues/4420)。

### Dragonfly Injector 支持 Kubernetes Webhook 自动注入

Dragonfly 提供 [dragonfly-injector](https://github.com/dragonflyoss/dragonfly-injector)，这是一个用于自动注入 P2P 能力的 Kubernetes Mutating Admission Webhook。
它可以通过基于注解的策略，自动向应用 Pod 注入 Dragonfly 客户端二进制、配置、Dfdaemon Socket 挂载以及 CLI 工具，使应用镜像无需重新构建即可使用 Dragonfly 下载文件。
Helm Charts 也支持启用 Webhook Injection 部署方式。

更多信息，请参阅 [Using Dragonfly with webhook injection](https://d7y.io/docs/next/getting-started/installation/helm-charts/#using-dragonfly-with-webhook-injection)。

### Blocklist 禁用指定下载能力

Dragonfly 支持在 Manager 控制台中配置 Blocklist，用于禁用指定下载。
该功能可作为应急手段，降低突发异常请求对服务造成的影响。
当下载被 Blocklist 拦截时，gRPC 下载会返回 `PermissionDenied` 错误码，HTTP Proxy 下载会返回 `FORBIDDEN` 状态。

![p1](images/p2.png)

更多信息，请参阅 [Blocklist](https://d7y.io/docs/next/advanced-guides/blocklist/)。

### 更完善的限流能力

Dragonfly 在控制面和客户端侧提供了更完整的限流能力。
Manager 和 Scheduler 的 gRPC 服务支持可配置的请求限流。
客户端支持上传带宽、下载带宽、回源带宽、预取带宽、上传请求、下载请求以及自适应限流，以更好地保护源站服务，并提升高负载场景下的系统稳定性。

更多信息，请参阅 [Rate Limit](https://d7y.io/docs/next/advanced-guides/rate-limit/)。

### dfctl 命令行工具

Dragonfly 客户端新增 `dfctl` 命令行工具，用于管理客户端本地存储中的任务，包括普通任务、持久化任务和持久化缓存任务。
它支持列出和删除本地资源，并可以通过 Scheduler 对文件和镜像任务执行预热。

更多信息，请参阅 [dfctl](https://d7y.io/docs/next/reference/commands/client/dfctl/)。

### 容器镜像仓库代理配置简化

Dfdaemon 现在可以根据 containerd 镜像仓库镜像请求中附带的 `ns` 查询参数推断上游镜像仓库。
结合 `proxyAllRegistries: true`，用户可以通过单个 `_default/hosts.toml` 配置将所有镜像仓库流量路由到 Dragonfly，而无需为每个镜像仓库维护独立的 `hosts.toml` 文件和 `X-Dragonfly-Registry` 请求头。

更多信息，请参阅 [Infer upstream registry from containerd ns query parameter](https://github.com/dragonflyoss/client/issues/1791) 和 [proxyAllRegistries 文档更新](https://github.com/dragonflyoss/d7y.io/pull/410)。

### 客户端下载与文件传输性能优化

Dragonfly 客户端在下载效率和文件传输可靠性方面进行了多项优化。
Parent Selector 和 Piece Collector 现在可以更好地协同，在调度决策前主动收集足够数量的父节点，从而提升带宽利用率，并在父节点不稳定时保持兼容的回退行为。
文件导出和下载操作现在使用缓冲写入，同时调整了 gRPC stream buffer 大小和连接相关配置，以提升大文件传输性能。

### HTTP 处理与重定向安全增强

HTTP backend 现在使用 HTTP/1.1，并在响应中存在 `Transfer-Encoding` 但缺少 `Content-Length` 时，重试 `HEAD` 请求以获取正确的内容长度。
Dragonfly 在跨域重定向时也会移除 `Authorization`、`Cookie` 等敏感请求头，并避免缓存相对路径形式的 HTTP 307 redirect location，同时仍会在请求处理中正确解析相对路径重定向。

### 附加功能增强

- Manager 新增 ExternalRedis TLS 支持，包括 CA 证书、客户端证书、私钥以及 `insecureSkipVerify` 配置。
- 移除已废弃的 V1 预热 API，并统一使用 `/healthy` 健康检查接口。
- 优化上传和下载指标采集，并移除未使用的 gRPC Piece Download 逻辑。
- 改进 `INSTANCE_NAME` 生成逻辑，优先使用 Kubernetes 构建期环境变量，并在未设置时回退到系统 Hostname。
- 在 dfdaemon 中新增 `hickory_dns` 配置选项，使 DNS 解析行为可配置。
- 优化 OCI Registry Blob 下载的任务 ID 计算，减少跨镜像仓库重复下载和重复存储。

## 重要修复

- 修复 Redis Lua 脚本中 peer TTL 和 `concurrent_piece_count` 参数顺序不一致的问题，避免错误的 key 过期时间和 peer 状态。
- 修复 PostgreSQL 在初始化默认 Scheduler Cluster 和 Seed Peer Cluster 后 `SERIAL` 序列未推进的问题，避免创建新集群时发生主键冲突。
- 修复相对路径 HTTP 307 重定向处理逻辑：相对路径 `Location` 不再写入缓存，并会在跟随重定向前基于原始 URL 正确解析。

## Nydus

### 新增特性

- 支持为 Ondemand 数据构建 Prefetch 优化的层 Blob。
- 支持 Nydus 镜像转换为 OCI 格式，支持本地归档互转。
- Nydusify Copy 支持 zero-disk transfer。
- 为 virtio-pmem DAX 后端引入基于 uffd 的支持，以支持 Kata 场景高性能镜像按需加载。
- Storage 层支持由 Proxy 切换到 Dragonfly SDK 模式，以提高 P2P 缓存命中性能。
- 支持短容器 ID 提交，提交前同步文件系统。
- 支持恢复 Nydusd 时重发 FUSE 请求，修复热升级测试。

### 重要修复

- 修复 Blobfs 对 fuse-backend-rs 0.12.0 的兼容性。
- 修复 failover-policy 参数解析。
- 修复 Builder 中符号链接覆盖目录时的 panic。
- 修复 chunkdict 去重逻辑、DBSCAN 聚类、chunk 排序等多个问题。
- 修复 Nydus 镜像检测逻辑。
- 修复 fusedev 嵌套挂载点的 remount invalidation。
- 修复 Nydusctl 后端指标计数器重置时的数值异常。
- Nydusify 修复镜像名修改时 blob 找不到的问题。
- Nydusify 修复 plain HTTP 转换问题。

## 其他

您可以在 [CHANGELOG](https://github.com/dragonflyoss/dragonfly/blob/main/CHANGELOG.md) 中查看更多详细信息。

## 链接

- Dragonfly 网站：<https://d7y.io/>
- Dragonfly 仓库：<https://github.com/dragonflyoss/dragonfly>
- Dragonfly 客户端仓库：<https://github.com/dragonflyoss/client>
- Dragonfly Injector 仓库: <https://github.com/dragonflyoss/dragonfly-injector>
- Dragonfly 控制台仓库：<https://github.com/dragonflyoss/console>
- Dragonfly Charts 仓库：<https://github.com/dragonflyoss/helm-charts>
- Dragonfly 监控仓库：<https://github.com/dragonflyoss/monitoring>

## Dragonfly Github

![qrcode](images/qrcode.webp)
