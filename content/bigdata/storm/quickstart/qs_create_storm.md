---
title: "快速入门"
description: 本小节主要介绍如何快速使用 Storm。 
keyword: 快速入门,Storm
weight: 10
collapsible: false
draft: false
---

Storm 是一个开源的分布式实时计算系统，本文档主要介绍如何快速使用 Storm。

<img src="../../_images/qs_storm_flow.png" style="zoom:60%;" />

操作流程详细信息，如下表所示。

| 操作流程                                        | 流程说明                                                     |
| ----------------------------------------------- | ------------------------------------------------------------ |
| [创建 Storm](../../manual/10_create_storm)      | 创建一个 Storm 集群。集群支持横向与纵向在线伸缩，还提供了监控告警等功能，使得管理集群异常方便。 |
| [Storm 集群测试](/bigdata/storm/manual/20_test_storm/summary)    | Storm 创建完成之后可以测试其可用性。                         |
| [在线伸缩 ](../../manual/30_online_scaling/add_node)     | 集群支持横向与纵向在线伸缩，介绍如何在线伸缩。               |
| [配置参数](../../manual/40_config_param)        | 配置参数是在部署应用时填写，成为集群配置项的变量。有的配置项是公共的，有的作用于其中的一个或多个角色。您可以在这里修改参数，以更新集群配置。 |
| [配置告警](../../manual/50_config_alarm)        | 设置独立通知策略，当集群产生告警，将统一发送至独立配置的通知列表，原告警策略所关联的通知列表将无法收到告警通知，请注意运维业务分配情况。 |
| [查看监控信息](../../manual/60_view_monitoring) | Storm 集群的每个节点提供了资源的监控和告警服务，包括 CPU 使用率、内存使用率、硬盘使用率等，以帮助用户更好的管理和维护 Storm 集群。 |
