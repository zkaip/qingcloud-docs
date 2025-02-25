---
title: "网络访问控制简介"
date: 2020-12-01T00:38:25+09:00
description: 网络访问控制介绍
draft: false
enableToc: false
weight: 10
keyword: 云服务器, QingCloud, 实例, 网络访问控制
---

网络访问控制功能包括网络 ACL 和基础网络安全策略。网络 ACL 是私有网络（Vxnet）的进出流量控制表，您可以在这里创建和配置 ACL 规则， ACL 规则中声明了哪些流量可以进/出私有网络（Vxnet），所以可以通过 ACL 控制进出流量。基础网络安全策略则定义了在青云 QingCloud 环境中，用户自身的基础网络是否对其他用户开放，默认禁用也就是默认用户的基础网络内的资源只受防火墙限制。


网络 ACL 与防火墙的功能类似，但是网络 ACL 绑定给私有网络，防火墙一般直接绑定给云服务器或者负载均衡器。网络 ACL 中更适合配置私有网络 Vxnet 通用的安全规则，例如：数据库所在的网段绝对不对公网开放，可以先配置上行和下行优先级 255 （最低的优先级一般用于保底规则）拒绝 IPv4 的所有地址的规则和上行和下行优先级 255 拒绝 IPv6 的所有地址的规则。假如对内部网络（假设为 `192.168.0.0/16` ）默认全开放，则可以配置上行和下行优先级 100 允许 192.168.0.0/16 。

>注意：在创建网络 ACL 规则时，数字越小则优先级越高。

在所有流量进出的时候，会按照优先级由高到低检查数据包，假设匹配到了数据包就不再继续往下匹配。所以大的地址段（例如 `0.0.0.0/0` ）放到低优先级，小的地址段（例如 `192.168.10.2/32` ）放到高优先级，可以帮助您更好地管理私有网络的安全。
