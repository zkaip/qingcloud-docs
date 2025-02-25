---
title: "修改配置参数"
description: 本小节主要介绍如何修改 RocketMQ 配置参数。 
keyword: 数据库,MySQL PLus,关系型数据库,MySQL,修改账号,
weight: 15
collapsible: false
draft: false
---

本小节主要介绍如何修改 RocketMQ 集群的配置参数。

## 注意事项

各参数的值设置需根据云服务器、存储磁盘配置情况，以及数据库其他参数情况进行调整。
当 Broker 参数值发生变化时，可能会重启整个集群，可能会造成部分消息发送失败（发送失败的消息建议重试发送），建议在业务低峰时修改 Broker 配置参数。

## 前提条件

- 已获取管理控制台登录账号和密码，且已获取集群操作权限。
- 已创建 RocketMQ 集群，且集群状态为**活跃**。

## 操作步骤

1. 登录管理控制台。
2. 选择**产品与服务** > **消息队列与中间件** > **RocketMQ 服务**，进入 RocketMQ 服务管理页面。
3. 选择目标集群，点击目标集群 ID，进入集群详情页面。
4. 点击**配置参数**页签，进入集群配置参数管理页面。

   <img src="/middware/rocketmq/_images/para_list.png" alt="配置参数列表" style="zoom:50%;" />

5. 在参数列表上方的下拉框选择修改的角色，点击**修改属性**，对应角色的参数**值**进入可编辑状态。
   
   <img src="/middware/rocketmq/_images/modify_para.png" alt="修改配置参数" style="zoom:50%;" />

6. 参考配置参数取值范围和描述，修改参数值。
7. 确认参数信息无误后，点击**保存**，弹出提示框。
8. 点击**确认**，返回参数列表页面。

