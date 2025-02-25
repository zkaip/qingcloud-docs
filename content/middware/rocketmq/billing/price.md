---
title: "计费说明"
description: 本小节主要介绍 RocketMQ 的计费说明。
keyword: 云计算,大数据,消息队列,中间件,价格,计费,费用,RocketMQ,
weight: 10
draft: false
---

## 计费项

RocketMQ 仅对集群所占用的资源进行收费，RocketMQ 集群提供的服务不额外收取服务费。

详细的计费项如下：

|<span style="display:inline-block;width:120px">计费项</span> |<span style="display:inline-block;width:410px">计费说明</span>|
|:----|:----|
|   节点主机实例     | 根据您选择的节点主机实例规格和数量进行收费，费用包含在 RocketMQ 资源费用中。  |
|   节点硬盘资源     | 根据您选择的数据盘类型和节点容量大小进行收费，费用包含在 RocketMQ 资源费用中。  |  
|   VPC 资源        |  RocketMQ 集群依赖 VPC 网络资源，VPC 产生的费用将会另外单独计算。价格请参考 [VPC 网络计费](/network/vpc/billing/price/)。 |  
|   监控告警（可选）  |  您可以根据实际情况为 RocketMQ 集群绑定指标告警策略：<li>若绑定的策略**监控周期**为 `5 分钟`，该功能免费使用。<li>若绑定的策略**监控周期**为 `1 分钟`，该功能会产生相应的费用，该费用另外单独计算。   | 

## 计费模式

RocketMQ 支持**包年/包月**和**按需计费**两种计费模式。

|<span style="display:inline-block;width:100px">计费模式</span> |<span style="display:inline-block;width:300px">说明</span>|<span style="display:inline-block;width:230px">适用场景</span>|
|:----|:----|:----|
|   包年/包月    |  **计费方式**为`月`或`年`。您需要按照购买时长（月或年）一次性支付所选时长的费用。在购买时长期间内，您可以一直使用该资源。  |  适用于长期稳定需求，帮助您更大程度的节省支出。   |
|   按需计费     |  **计费方式**为`小时`。按秒计费，按小时扣费，且不设最低消费指标，您可以随时启动/关闭或删除集群，按实际时长进行扣费。<li>集群开启时，收取节点主机实例和节点存储空间费用。<li>集群关闭时，仅收取节点存储空间费用。|  适用于有较大波动且无法准确预测资源需求量的业务场景，或临时性和突发性的资源需求场景。如果是短期测试使用，推荐使用按需计费模式。  |

<!-- ## 产品价格

根据选择的计费模式，使用的节点主机实例和节点硬盘资源规模，总计费用会有所不同，可以通过[价格计算器](https://www.qingcloud.com/pricing#/RocketMQ)获取价格详情。 -->
