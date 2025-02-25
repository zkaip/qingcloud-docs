---
title: "配置集群参数"
description: 介绍如何修改 QKE 集群参数。
draft: false
weight: 10
keyword: 青云, QingCloud, 云计算, QKE 参数
---

QKE 支持自定义部分参数的值，您可以根据自己的业务情况对集群运行参数进行调整。

## 操作步骤

1. 登录 QingCloud 管理控制台。

2. 在控制台顶部的导航菜单中，选择**产品与服务** > **容器服务** > **容器引擎 QKE**，进入 QKE 集群列表页面。

3. 在集群列表，点击待查看集群的名称，进入**集群概览**页面。

4. 在左侧导航栏，点击**集群信息**，进入**集群信息**页面。

4. 在页面右侧的**环境参数**区域，展示了集群当前的参数配置。

   参数包括**kubernetes 配置**、**网络参数**、**镜像参数**及**其他参数**。

   ![参数配置](../../../_images/paras_setting.png)

6. 点击**修改参数**，参数值变为可编辑状态。

   > **说明**
   >
   > 部分参数仅支持在创建集群时配置，此处不可修改，仅作为展示。
   >
   > 可同时修改不同类型的参数。

7. 根据实际情况进行参数值修改。

   详细说明请参见下述[参数说明](#参数说明)。

8. 修改完成后，点击**确认修改**进行保存，弹出提示框。

9. 确认无误后，点击**确认**。（还需验证）

## 参数说明

#### Kubernetes 配置

| 参数名称          | 参数说明                                                     | 备注                 |
| ----------------- | ------------------------------------------------------------ | -------------------- |
| K8s apiserver EIP | 如果希望通过公网访问 K8s apiserver，可在此处填写可用的 EIP，系统将会自动创建一个 LB 并绑定此 EIP。<br/>**SSH 登录集群**：自管版集群支持设置是否开启 SSH 登录集群功能。开启时，需要设置密钥或者用户密码（二选一）。开启后，用户可以通过 SSH 的方式登录集群。 | -                    |
| 集群内 DNS 域名   | 集群内的 DNS 域名，用于 Kubernetes Services。                | 集群创建后无法修改。 |
| NodePort 范围     | 每个节点可分配的 NodePort 范围，例如 `30000-32767`。<br/>由于 KubeSphere 的对外端口号是 30880，若您需要安装 KubeSphere，请保证 30880 在该范围内。 | 集群创建后无法修改。 |
| 最大 pod 数量     | 每个节点上可运行的最大 pod 数量，默认为 120。                | -                    |

#### 网络参数

| 参数名称     | 参数说明                                                     | 备注                 |
| ------------ | ------------------------------------------------------------ | -------------------- |
| Proxy Mode   | 选择 kube-proxy 的模式：iptables 或 ipvs。<br/>kube-proxy 用于在服务和其后端 Pod 之间进行负载均衡。其详细说明，请参考 [Kubernetes 指南](https://feisky.gitbooks.io/kubernetes/content/components/kube-proxy.html)。 | 集群创建后无法修改。 |
| 网卡插件     | 选择一种网卡插件：calico 或 flannel。<br/>插件具体说明，可参考[插件支持](/container/qke_plus/intro/plugin/)。 | 集群创建后无法修改。 |
| Pod 网段     | 设置 Pod 使用的网段。<br/>请按照标准的 CIDR 格式填写，例如：`10.10.0.0/16`。 | 集群创建后无法修改。 |
| Service 网段 | 设置 Service 使用的网段。<br/>请按照标准的 CIDR 格式填写，例如：`10.96.0.0/16`。 | 集群创建后无法修改。 |

#### 镜像参数

| 参数名称            | 配置说明                                                     |
| ------------------- | ------------------------------------------------------------ |
| registry-mirrors    | 填写完整的 Docker 镜像服务地址。 <br/>填写示例：`https://mirror.harbor.local`。多个地址之间使用逗号（,）分隔。 |
| insecure-registries | 若需要通过非安全的 HTTP 或不受信任的 HTTPS 访问的 Docker 仓库，则在此处填写仓库地址。<br/>填写示例：`mirror.harbor.local`。多个地址之间使用逗号（,）分隔。 |
| docker-auths        | 填写镜像仓库密钥，以获得访问、拉取、推送镜像得权限。<br/>填写示例：`{"dockerhub.qingcloud.com":{"auth":"YWRtaW46MTIzNDU2"},"index.docker.io":{"auth":"YWRtaW46MTIzNDU2"}}`。<br/>具体配置说明请参见[配置镜像仓库信息](/container/qke_plus/quickstart/cfg_mirror_repo/#步骤二配置镜像仓库信息)。 |

#### 其他参数

| 参数名称    | 参数说明                                                     | 备注                 |
| ----------- | ------------------------------------------------------------ | -------------------- |
| API 密钥 ID | 此密钥用于创建云平台的资源，比如负载均衡器、PV 挂盘等。<br/>若无可用密钥，请前往 [API 密钥管理](https://console.qingcloud.com/access_keys/)页面进行创建。 | 集群创建后无法修改。 |







