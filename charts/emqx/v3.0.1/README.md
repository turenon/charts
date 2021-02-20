# 介绍
使用Helm包管理器在Kubernetes集群上部署emqx集群。

# 配置
可配置参数及其默认值如下表所示

| Parameter  | Description | Default Value |
| ---        |  ---        | ---           |
| `ingress.hosts`| emqx dashboard and websocket ingress hosts|`chart-example.local`|
| `replicaCount` | It is recommended to have odd number of nodes in a cluster, otherwise the emqx cluster cannot be automatically healed in case of net-split. |3|
| `image.repository` | EMQ X Image name |emqx/emqx|
| `image.pullPolicy`  | Global Docker registry secret names as an array |IfNotPresent|
| `persistence.enabled` | Enable EMQX persistence using PVC |false|
| `persistence.storageClass` | Storage class of backing PVC |`nil` (uses alpha storage class annotation)|
| `persistence.existingClaim` | EMQ X data Persistent Volume existing claim name, evaluated as a template |""|
| `persistence.accessMode` | PVC Access Mode for EMQX volume |ReadWriteOnce|
| `persistence.size` | PVC Storage Request for EMQX volume |20Mi|
| `resources` | CPU/Memory resource requests/limits |{}|
| `nodeSelector` | Node labels for pod assignment |`{}`|
| `tolerations` | Toleration labels for pod assignment |`[]`|
| `affinity` | Map of node/pod affinities |`{}`|
| `service.type`  | Emqx cluster service type. |ClusterIP|
| `emqxConfig` | Emqx configuration item, see the [documentation](https://github.com/emqx/emqx-docker#emq-x-configuration) | |
| `emqxAclConfig`| emqx acl configuration item| |

# 常用配置
- replicaCount
- ingress.hosts
- nodeSelector
- emqxAclConfig
- emqxConfig
