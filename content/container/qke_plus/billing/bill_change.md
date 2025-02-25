---
title: "费用变更"
description: 集群费用更新场景及具体价格变更说明。
draft: false
keyword: 青云, QingCloud, 云计算, QKE, 价格, 计费
weight: 20
---

在您使用 QKE 的过程中，以下场景将涉及到费用变更：

| 变更场景                   | 费用影响                                                     |
| -------------------------- | ------------------------------------------------------------ |
| 扩容集群                   | 扩容集群将升级节点规格配置，将增加费用。                     |
| 调整节点数量               | 手动新增或删除节点涉及云服务器资源的增删，将根据资源实际使用情况变更费用。 |
| 开启自动伸缩               | 当满足自动伸缩得触发条件时，将自动执行节点新增或减少，从而导致云服务器资源费用的增加或减少。 |
| 变更计费模式               | <ul><li>按需转包年包月，需要预付费，但可享受更优惠的价格。</li><li>包年包月转按需，不影响当前合约费用，待合约到期后，将按照按需计费标准进行收费，按需计费相比包年包月单价更高。</li></ul> |
| 新装可视化管理工具及其组件 | 新装可视化管理工具及其组件需要创建及挂载一定数量的硬盘，并收取硬盘费用。 |
| 可视化控制台绑定 EIP       | 为可视化控制台绑定 EIP 时，会自动创建一个负载均衡器，并收取费用。 |
| 关闭集群                   | <ul><li>按需计费集群关闭后，集群节点（云服务器）只收取硬盘费用。</li><li>包年包月集群关闭后，集群节点费用（云服务器）不受影响。</li><li>集群依赖资源费用不受集群关闭影响。</li></ul> |





