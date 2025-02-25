---
title: "更改服务器类型"
description: 本小节主要介绍如何更改 RocketMQ 集群的服务器类型。 
keyword: 云计算,大数据,消息队列,中间件,RocketMQ,RocketMQ 集群更改服务器类型
weight: 04
collapsible: false
draft: false
---

RocketMQ 集群创建成功后，可以更改集群的云服务类型。

从低配主机类型升级为高配主机类型，集群将具有更高的性能。

## 前提条件

- 已获取 QingCloud 管理控制台登录账号和密码，且已获取集群操作权限。
- RocketMQ 集群状态为**活跃**。

## 操作步骤

1. 登录 QingCloud 管理控制台。
2. 选择**产品与服务** > **消息队列与中间件** > **RocketMQ 服务**，进入 RocketMQ 服务管理页面。
3. 点击目标集群 ID，进入集群详情页面。
4. 在**基本属性**模块，点击集群操作下拉菜单。
5. 展开下拉菜单，点击**更改云服务器类型**，弹出更改集群云服务器类型窗口。
   
   <img src="/middware/rocketmq/_images/switch_node_mode.png" alt="更改集群云服务器类型" style="zoom:50%;" />

6. 选择目标类型。
7. 点击**提交**，返回节点列表页面。
