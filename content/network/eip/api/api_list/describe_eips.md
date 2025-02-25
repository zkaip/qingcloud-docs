---
title: "DescribeEips"
description: 获取公网 IP 信息。
draft: false
weight: 2
keyword: 公网 IP API,获取公网 IP 信息
---

获取一个或多个公网 IP 信息列表。

可根据公网 IP 的 ID，状态，名称，分配的云服务器 ID 作过滤条件，来获取公网 IP 列表。如果不指定任何过滤条件，默认返回你所拥有的所有公网 IP。如果指定不存在的公网 IP，或非法状态值，则会返回错误信息。

## 请求参数

| 参数 | 参数类型 | 描述 | 是否必选 |
| --- | --- | --- | --- |
| eips.n | String | 公网 IP 的 ID | No |
| instance_id | String | 云服务器 ID，可得到已分配给此云服务器的公网 IP | No |
| status.n | String | 公网 IP 状态，有效值为 pending, available, associated, suspended，released, ceased | No |
| search_word | String | 搜索关键词，支持公网 IP 的 ID，名称 | No |
| tags.n | String | 按照标签 ID 过滤, 只返回已绑定某标签的资源 | No |
| verbose | Integer | 是否返回冗长的信息，若为 1，则返回公网 IP 相关其他资源的详细数据 | No |
| offset | Integer | 数据偏移量，默认为 0 | No |
| limit | Integer | 返回数据长度，默认为 20，最大 100 | No |
| zone | String | 区域 ID，注意要小写 | Yes |

[_公共参数_](../../get_api/parameters/)

## 返回数据

| 参数 | 参数类型 | 描述 |
| --- | --- | --- |
| action | String | 响应动作 |
| eip_set | Array | JSON 格式的公网IP数据列表，每项参数可见下面 **Response Item** |
| total_count | Integer | 根据过滤条件得到的公网 IP总数 |
| ret_code | Integer | 执行成功与否，0 表示成功，其他值则为错误代码 |

**Response Item**

| 参数 | 参数类型 | 描述 |
| --- | --- | --- |
| eip_id | String | 公网IP唯一标识 ID |
| eip_name | String | 公网IP名称 |
| description | String | 公网IP描述 |
| associate_mode | Integer | 绑定模式，0 为外部绑定，1 为内部绑定 |
| bandwidth | Integer | 带宽，以 Mbps 为单位 |
| billing_mode | String | 公网IP计费模式：bandwidth 按带宽计费，traffic 按流量计费 |
| status | String | 公网IP状态，有效值为 pending, available, associated, suspended，released, ceased<br/>pending： 等待被创建<br/>available： 可用状态，此时可以被绑定到资源上<br/>associated： 绑定状态<br/>suspended： 由于欠费，已被暂停使用<br/>released： 已被释放回资源池，此时公网 IP 不可被恢复。<br/>ceased： 已被彻底释放 |
| transition_status | String | 公网IP过渡状态，有效值为 associating, dissociating, suspending, resuming, releasing<br/>associating： 绑定到资源中，由 available 状态变成 associated 状态<br/>dissociating： 启动中，由 associated 状态变成 available 状态<br/>suspending： 欠费暂停中，由 available/associated 状态变成 suspended 状态<br/>resuming： 恢复中，由 suspended 状态变成 available 状态<br/>releasing： 删除中，由 available/associated/suspended 状态变成 released 状态 |
| icp_codes | String | 备案号 |
| create_time | TimeStamp | 公网IP创建时间，为 UTC 时间，格式可参见 [ISO8601](http://www.w3.org/TR/NOTE-datetime) |
| status_time | TimeStamp | 公网IP最近一次状态变更时间，为 UTC 时间，格式可参见 [ISO8601](http://www.w3.org/TR/NOTE-datetime) |
| resource | Dict | 若已分配到云服务器/路由器，则表示所分配的云服务器/路由器信息，数据格式为:<br/>{<br/> "resource_name":"website",<br/> "resource_type":"instance",<br/> "resource_id":"i-j32t3llb"<br/>} |
| eip_group | Dict | 公网 IP 的分组信息，数据格式为:<br/>{<br/>  "eip_group_id":"eipg-1nv8hobz",<br/>  "eip_group_name":"192.168.93.*"<br/>} |
| eip_addr | String | 公网 IP 地址 |

## 示例

**请求示例：**

```
https://api.qingcloud.com/iaas/?action=DescribeEips
&COMMON_PARAMS
```

**返回示例：**

```
{
  "action":"DescribeEipsResponse",
  "total_count":1,
  "eip_set":[
    {
      "status":"associated",
      "eip_id":"eip-amorzjgv",
      "description":null,
      "associate_mode":0,
      "need_icp":0,
      "sub_code":0,
      "transition_status":"",
      "icp_codes":"",
      "eip_group":{
        "eip_group_id":"eipg-00000000",
        "eip_group_name":"BGP multi-line"
      },
      "bandwidth":4,
      "billing_mode":"traffic",
      "create_time":"2013-08-30T10:15:47Z",
      "status_time":"2013-08-30T10:15:56Z",
      "eip_name":"demo",
      "resource":{
        "resource_name":"demo",
        "resource_type":"router",
        "resource_id":"rtr-b0u6sdj6"
      },
      "eip_addr":"192.168.7.69"
    }
  ],
  "ret_code":0
}
```
