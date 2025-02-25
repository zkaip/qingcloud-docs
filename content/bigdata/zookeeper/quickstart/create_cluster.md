---
title: "创建 ZooKeeper 集群"
description: 本小节主要介绍如何快速创建 ZooKeeper 集群实例。 
keyword: ZooKeeper 实例, 创建集群,创建实例
weight: 10
collapsible: false
draft: false
---

通过 AppCenter 集群管理控制台，您可以快速创建 ZooKeeper 集群。

本小节主要介绍如何快速创建 ZooKeeper 集群。

## 前提条件

- 已获取管理控制台登录账号和密码，且账号已实名认证。
- 已获取 ZooKeeper 集群操作权限。

## 操作步骤

1. 登录管理控制台。
2. 选择**产品与服务** > **大数据服务** > **ZooKeeper 服务**，进入 ZooKeeper 集群管理页面。
3. 点击**立即部署**或**创建**，进入应用部署页面。
4. 选择**区域**。   
   根据就近原则，选择实例所在区域。
5. 配置实例基本属性、应用版本、网络信息、环境参数等信息。

   a. [基本设置](#基本设置)
   b. [ZooKeeper 节点设置](#zookeeper-节点设置)
   c. [网络设置](#网络设置)
   d. [服务环境参数设置](#服务环境参数设置)
   e. [用户协议](#用户协议)

6. 确认配置和费用信息无误后，点击**提交**，创建集群。

   集群创建成功后，可在**集群管理**页面，查看和管理 ZooKeeper 集群。

   ![集群列表](../../_images/cluster_list.png)

### 基本设置

集群名称、网络、版本、计费方式等基本信息配置。

|<span style="display:inline-block;width:140px">参数</span> |<span style="display:inline-block;width:520px">参数说明</span>|
|:----|:----|
|   UUID     |  系统默认分配的全局唯一标识码，不可修改。  |
|   名称     |  输入当前集群的名称。默认为`ZooKeeper`。  |
|   描述  |  （可选）对集群的简要描述。   |
|   版本 |  选择集群版本。|
|   计费方式 |  选择集群计费方式，可选择按`小时`、`包年包月`计费。|
|   购买有效期 |  当**计费方式**选择`包年包月`时需要设置此参数。|
|   自动续约 |  当**计费方式**选择`包年包月`时可以设置此参数。<br>开启**自动续约**后，当您的账户余额充足时，集群到期后将自动续费。|
|   自动备份时间 |  `ZooKeeper 3.4.14 - v2.0.0` 版本支持自动备份，可选择在每天指定时间段创建备份。<br>默认关闭自动备份。| 
|   部署方式 |  `ZooKeeper 3.4.14 - v2.0.0` 版本可选择`多可用区部署`和`单可用区部署`。<li>多可用区部署 ：将节点分散部署在当前区域的不同可用区，可用性高。<li>单可用区部署 ：将节点部署在当前区域同一个可用区，网络延迟最低。可指定节点所在当前区域的可用区。 | 
|   可用区 |  选择使用区域。 |

<img src="/bigdata/zookeeper/_images/zk_step_1.png" alt="基本设置" style="zoom:50%;" />

### ZooKeeper 节点设置

集群 ZooKeeper 节点的资源配置，包括云服务器规格、磁盘大小等。

|<span style="display:inline-block;width:140px">参数</span> |<span style="display:inline-block;width:520px">参数说明</span>|
|:----|:----|
|   CPU     |  选择集群节点云服务器 CPU 规格。  |
|   内存     |  选择集群节点云服务器内存大小。  |
|   主机类型  |  选择集群节点云服务器类型，可选择`基础型`和`企业型 e2`。|
|   节点数量  |  选择集群节点数量，可选择1～9个。默认3个|
|   存储容量 |  配置集群数据和日志存储磁盘大小。磁盘大小决定了数据库最大容量以及 IOPS 能力，请根据业务量，可滑动设置或输入数字配置集群磁盘大小。|

<img src="/bigdata/zookeeper/_images/zk_step_2.png" alt="节点设置" style="zoom:50%;" />

### 网络设置

通过为集群设置独享私有网络，便于网络**过滤控制**，且不影响其它私有网络的设置，可确保数据库的对不同业务进行网络隔离。数据库集群仅可加入已连接路由器的私有网络，且需确保私有网络的 DHCP 处于**打开**状态。

|<span style="display:inline-block;width:140px">参数</span> |<span style="display:inline-block;width:520px">参数说明</span>|
|:----|:----|
|   VPC 网络     |  选择 VPC 网络。<li>默认适配同区域已有 VPC 网络。可在下拉框选择已有私有网络。<li>若无可选网络，可点击**新建 VPC 网络**，创建依赖网络资源。  |
|   私有网络     |  选择私有网络。<li>默认适配同区域 VPC 网络下已有私有网络。可在下拉框选择已有私有网络。<li>若无可选网络，可点击**新建私有网络**，创建依赖网络资源。  |
|   节点 IP   |  配置节点 IP 地址。<li>默认为`自动分配`。<li> 选择`手动配置`需为各节点配置 IP。  |

<img src="/bigdata/zookeeper/_images/zk_step_3.png" alt="网络设置" style="zoom:50%;" />

### 服务环境参数设置

集群环境参数配置。

点击**展开配置**，可修改集群默认配置。或集群创建成功后，在集群详情页面的**配置参数**页签修改参数。

> **说明**
> 
> `ZooKeeper 3.4.9 - v1.0.0` 版本不支持设置服务环境参数。

<img src="/bigdata/zookeeper/_images/zk_step_4.png" alt="服务环境参数配置" style="zoom:50%;" />

### 用户协议

阅读**云平台 AppCenter 用户协议**，并勾选用户协议。

<img src="/bigdata/zookeeper/_images/zk_step_5.png" alt="用户协议" style="zoom:50%;" />
