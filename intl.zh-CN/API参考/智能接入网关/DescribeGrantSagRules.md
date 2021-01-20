# DescribeGrantSagRules

调用DescribeGrantSagRules查询指定智能接入网关实例的授权信息。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=DescribeGrantSagRules&type=RPC&version=2018-03-13)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|DescribeGrantSagRules|要执行的操作。

 取值：**DescribeGrantSagRules**。 |
|RegionId|String|是|cn-hangzhou|智能接入网关实例所属的地域ID。 |
|SmartAGId|String|是|sag-hdg\*\*\*\*\*\*\*\*\*\*\*\*\*|智能接入网关实例ID。 |
|PageNumber|Integer|否|1|分页查询时的页码。

 默认值是**1**。 |
|PageSize|Integer|否|10|分页查询时每页展示的授权条目数。

 默认值为**10**，最大值为**50**。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|GrantRules|Array of GrantRule| |授权信息列表。 |
|GrantRule| | | |
|CcnInstanceId|String|ccn-hd\*\*\*\*\*\*\*\*\*\*|云连接网实例ID。 |
|CcnUid|Long|123456|云连接网实例所属的账号ID。 |
|CreateTime|Long|156576751700|创建授权的时间戳。 |
|GrantTrafficService|Boolean|false|是否给跨账号的云连接网实例授权了智能接入网关实例的流量服务能力。

 -   **true**：已授权。
-   **false**：未授权。 |
|InstanceId|String|123455|智能接入网关实例所属的账号ID。 |
|SmartAGId|String|sag-hdhgn\*\*\*\*\*|智能接入网关实例ID。 |
|PageNumber|Integer|2|分页查询时的页码。 |
|PageSize|Integer|10|分页查询时每页展示的授权条目数。 |
|RequestId|String|6E1674AC-083C-4031-B047-7A66E418E0C6|请求ID。 |
|TotalCount|Integer|2|授权条目总数。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=DescribeGrantSagRules
&RegionId=cn-hangzhou
&SmartAGId=sag-hdg*************
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<DescribeGrantSagRulesResponse>
  <TotalCount>1</TotalCount>
  <RequestId>72CD8E55-CAC3-416B-9E18-5FF60D991713</RequestId>
  <PageSize>10</PageSize>
  <PageNumber>1</PageNumber>
  <GrantRules>
        <GrantRule>
              <InstanceId>16884015959****</InstanceId>
              <GrantTrafficService>false</GrantTrafficService>
              <CcnInstanceId>ccn-al2yjgtmsls4cu****</CcnInstanceId>
              <CreateTime>1609382634000</CreateTime>
              <CcnUid>13439858877****</CcnUid>
              <SmartAGId>sag-0ep6gx9wjvly4m****</SmartAGId>
        </GrantRule>
  </GrantRules>
</DescribeGrantSagRulesResponse>
```

`JSON` 格式

```
{
	"TotalCount": 1,
	"RequestId": "72CD8E55-CAC3-416B-9E18-5FF60D991713",
	"PageSize": 10,
	"PageNumber": 1,
	"GrantRules": {
		"GrantRule": [
			{
				"InstanceId": "16884015959****",
				"GrantTrafficService": false,
				"CcnInstanceId": "ccn-al2yjgtmsls4cu****",
				"CreateTime": 1609382634000,
				"CcnUid": "13439858877****",
				"SmartAGId": "sag-0ep6gx9wjvly4m****"
			}
		]
	}
}
```

## 错误码

访问[错误中心](https://error-center.alibabacloud.com/status/product/Smartag)查看更多错误码。

