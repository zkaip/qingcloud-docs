---
title: "新增节点"
description: 本小节主要介绍如何新增 RocketMQ 节点实例。 
keyword: 云计算,大数据,消息队列,中间件,RocketMQ,节点添加,新增节点
weight: 10
collapsible: false
draft: false
---

本小节主要介绍如何新增 RocketMQ 集群节点。

## 前提条件

- 已获取管理控制台登录账号和密码，且已获取集群操作权限。
- 已创建 RocketMQ 集群，且集群状态为**活跃**。

## 操作步骤

1. 登录管理控制台。
2. 选择**产品与服务** > **消息队列与中间件** > **RocketMQ 服务**，进入 RocketMQ 服务管理页面。
3. 选择目标集群，点击目标集群 ID，进入集群详情页面。
4. 在**节点**页签，点击**新增节点**，弹出新增节点配置窗口。
   
   <img src="/middware/rocketmq/_images/add_node.png" alt="新增节点" style="zoom:50%;" />

5. 配置节点信息，详细参数请参见[节点参数](#节点参数)。
6. 确认配置信息无误后，点击**提交**，返回节点列表页面。

### 节点参数

|  <span style="display:inline-block;width:120px">参数</span> | <span style="display:inline-block;width:480px">说明</span>  |
|:--- |:--- |
| 节点类型   | 选择节点类型。可选择`名称服务器`、`Broker`、`Broker 副本`、`网页控制台`和`客户端`。<li>新增 `Broker` 节点时，系统将根据当前 `Broker 副本`节点数量自动为新增的 `Broker` 节点新增 `Broker 副本`节点。<li>新增 `Broker 副本`节点时，系统将自动为所有 `Broker` 节点新增相应数量的 `Broker 副本`节点。 |
| 节点数量   |  输入新增节点数量，根据已有节点数量确定可新增节点数量。|
| 节点名称   |  输入节点名称。 |
| 节点 IP   |  配置节点 IP 地址。<li>默认为`自动分配`。<li> 选择`手动配置`需为各节点配置 IP。  |
