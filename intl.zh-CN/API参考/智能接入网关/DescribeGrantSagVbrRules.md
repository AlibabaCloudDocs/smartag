# DescribeGrantSagVbrRules

调用DescribeGrantSagVbrRules查询指定智能接入网关实例和跨账号边界路由器（VBR）实例授权信息。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=DescribeGrantSagVbrRules&type=RPC&version=2018-03-13)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|DescribeGrantSagVbrRules|要执行的操作。

 取值：**DescribeGrantSagVbrRules**。 |
|RegionId|String|是|cn-shanghai|智能接入网关实例所在地域ID。 |
|SmartAGId|String|是|sag-0nnteglltw6z4b\*\*\*\*|智能接入网关实例ID。 |
|VbrInstanceId|String|是|vbr-bp13gtbhdp0pfqg6s\*\*\*\*|边界路由器实例ID。 |
|PageNumber|Integer|否|1|分页查询时的页码。默认值为**1**。 |
|PageSize|Integer|否|10|分页查询时每页的条目数。默认值为**10**。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|GrantRules|Array of GrantRule| |授权规则详情。 |
|GrantRule| | | |
|Bound|Boolean|false|智能接入网关实例和边界路由器实例绑定状态。

 -   **false**：未绑定。
-   **true**：已经绑定。 |
|CreateTime|Long|1600743723000|授权规则创建时间。 |
|InstanceId|String|sgv-3x8djyem7vqh70\*\*\*\*|授权规则ID。 |
|SmartAGId|String|sag-0nnteglltw6z4b\*\*\*\*|智能接入网关实例ID。 |
|SmartAGUid|Long|1231571212121212|智能接入网关实例所属UID。 |
|VbrInstanceId|String|vbr-bp13gtbhdp0pfqg6s\*\*\*\*|边界路由器实例ID。 |
|VbrRegionId|String|cn-hangzhou|边界路由器实例所属地域ID。 |
|VbrUid|Long|1231571212121212|边界路由器实例所属实例UID。 |
|PageNumber|Integer|1|分页查询时的页码。 |
|PageSize|Integer|10|分页查询时每页的条目数。 |
|RequestId|String|46E98E69-FBA2-423E-9E5A-A3C6D843FED1|请求ID。 |
|TotalCount|Integer|1|授权规则总条目数。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=DescribeGrantSagVbrRules
&RegionId=cn-shanghai
&SmartAGId=sag-0nnteglltw6z4b****
&VbrInstanceId=vbr-bp13gtbhdp0pfqg6s****
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<DescribeGrantSagVbrRulesResponse>
  <TotalCount>1</TotalCount>
  <RequestId>46E98E69-FBA2-423E-9E5A-A3C6D843FED1</RequestId>
  <PageSize>10</PageSize>
  <PageNumber>1</PageNumber>
  <GrantRules>
        <GrantRule>
              <VbrUid>123157908552****</VbrUid>
              <SmartAGUid>168840159596****</SmartAGUid>
              <VbrInstanceId>vbr-bp13gtbhdp0pfqg6s****</VbrInstanceId>
              <InstanceId>sgv-3x8djyem7vqh70****</InstanceId>
              <CreateTime>1600743723000</CreateTime>
              <Bound>false</Bound>
              <VbrRegionId>cn-hangzhou</VbrRegionId>
              <SmartAGId>sag-0nnteglltw6z4b****</SmartAGId>
        </GrantRule>
  </GrantRules>
</DescribeGrantSagVbrRulesResponse>
```

`JSON` 格式

```
{
	"TotalCount": 1,
	"RequestId": "46E98E69-FBA2-423E-9E5A-A3C6D843FED1",
	"PageSize": 10,
	"PageNumber": 1,
	"GrantRules": {
		"GrantRule": [
			{
				"VbrUid": "123157908552****",
				"SmartAGUid": "168840159596****",
				"VbrInstanceId": "vbr-bp13gtbhdp0pfqg6s****",
				"InstanceId": "sgv-3x8djyem7vqh70****",
				"CreateTime": 1600743723000,
				"Bound": false,
				"VbrRegionId": "cn-hangzhou",
				"SmartAGId": "sag-0nnteglltw6z4b****"
			}
		]
	}
}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|SAG.InstanceIdEmpty|You must specify the SAG instance ID.|智能网关实例ID为空。|
|400|SAG.InstanceNoFound|The specified SAG instance does not exist.|智能网关实例不存在。|

访问[错误中心](https://error-center.alibabacloud.com/status/product/Smartag)查看更多错误码。

