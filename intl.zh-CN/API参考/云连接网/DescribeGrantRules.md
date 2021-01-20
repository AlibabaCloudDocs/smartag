# DescribeGrantRules

调用DescribeGrantRules查询云连接网实例的授权信息。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=DescribeGrantRules&type=RPC&version=2018-03-13)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|DescribeGrantRules|要执行的操作。

 取值：**DescribeGrantRules**。 |
|RegionId|String|是|cn-shanghai|云连接网实例所在的地域ID。 |
|AssociatedCcnId|String|否|ccn-n2935s1mnwv8i\*\*\*\*\*|云连接网实例ID。 |
|PageSize|Integer|否|10|分页查询时每页展示的授权条目数。

 默认值为**10**，最大值为**50**。 |
|PageNumber|Integer|否|1|分页查询时的页码。

 默认值是**1**。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|GrantRules|Array of GrantRule| |授权信息列表。 |
|GrantRule| | | |
|CcnInstanceId|String|ccn-n2935s1mnwv8i\*\*\*\*\*|云连接网实例ID。 |
|CcnUid|Long|213213|云连接网实例所属的账号ID。 |
|CenInstanceId|String|cen-0jtu0bcbika5b5\*\*\*\*|云企业网实例ID。 |
|CenUid|Long|213213|云企业网实例所属的账号ID。 |
|GmtCreate|Long|1563439920000|创建授权的时间戳。 |
|GmtModified|Long|1563439920000|授权操作最近修改的时间戳。 |
|GrantRuleId|String|18313265-d988-406c-965d-3e110ff\*\*\*\*\*|授权条目ID。 |
|GrantTrafficService|Boolean|false|是否给跨账号的云企业网实例授权云连接网实例的流量服务能力。

 -   **true**：已授权。
-   **false**：未不授权。 |
|RegionId|String|cn-shanghai|云连接网实例所属的地域ID。 |
|PageNumber|Integer|1|分页查询时的页码。 |
|PageSize|Integer|10|分页查询时每页展示的授权条目数。 |
|RequestId|String|FA579C2D-84A0-4BA1-B9C3-1E5A3B15F1B6|请求ID。 |
|TotalCount|Integer|1|授权条目总数。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=DescribeGrantRules
&RegionId=cn-shanghai
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<DescribeGrantRulesResponse>
  <TotalCount>1</TotalCount>
  <RequestId>22B1031D-4367-46D6-879E-49ECD28B12D3</RequestId>
  <PageSize>10</PageSize>
  <PageNumber>0</PageNumber>
  <GrantRules>
        <GrantRule>
              <GmtCreate>1609392288000</GmtCreate>
              <CenUid>1343985887****</CenUid>
              <GrantTrafficService>false</GrantTrafficService>
              <CcnInstanceId>ccn-5ldtbj8i7nh6pp****</CcnInstanceId>
              <GrantRuleId>3a9bfd9f-48df-41ea-ad88****</GrantRuleId>
              <CenInstanceId>cen-voitp3yy1xlta8****</CenInstanceId>
              <GmtModified>1609392288000</GmtModified>
              <CcnUid>168840159596****</CcnUid>
              <RegionId>cn-shanghai</RegionId>
        </GrantRule>
  </GrantRules>
</DescribeGrantRulesResponse>
```

`JSON` 格式

```
{
	"TotalCount": 1,
	"RequestId": "22B1031D-4367-46D6-879E-49ECD28B12D3",
	"PageSize": 10,
	"PageNumber": 0,
	"GrantRules": {
		"GrantRule": [
			{
				"GmtCreate": 1609392288000,
				"CenUid": "1343985887****",
				"GrantTrafficService": false,
				"CcnInstanceId": "ccn-5ldtbj8i7nh6pp****",
				"GrantRuleId": "3a9bfd9f-48df-41ea-ad88****",
				"CenInstanceId": "cen-voitp3yy1xlta8****",
				"GmtModified": 1609392288000,
				"CcnUid": "168840159596****",
				"RegionId": "cn-shanghai"
			}
		]
	}
}
```

## 错误码

访问[错误中心](https://error-center.alibabacloud.com/status/product/Smartag)查看更多错误码。

