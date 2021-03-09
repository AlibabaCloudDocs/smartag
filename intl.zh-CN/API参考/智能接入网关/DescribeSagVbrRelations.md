# DescribeSagVbrRelations

调用DescribeSagVbrRelations查询指定边界路由器（VBR）实例是否绑定有智能接入网关实例。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=DescribeSagVbrRelations&type=RPC&version=2018-03-13)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeSagVbrRelations|系统规定参数。取值：DescribeSagVbrRelations。 |
|VbrInstanceIds.N|RepeatList|是|vbr-bp15ihkk93ezxppkd\*\*\*\*|边界路由器实例ID。可以一次查询多个边界路由器实例，N取值最大为**20**。 |
|VbrRegionId|String|是|cn-hangzhou|边界路由器实例所属地域ID。 |
|RegionId|String|否|cn-shanghai|智能接入网关地域ID。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|17D79124-104A-42DB-8FCA-CE2957CD1723|请求ID。 |
|SagVbrRelations|Array of SagVbrRelation| |绑定信息。 |
|SagInstanceId|String|sag-0nnteglltw6z4b\*\*\*\*|智能接入网关实例ID。 |
|SagUid|String|168840151212121212|智能接入网关实例所属账号UID。 |
|VbrInstanceId|String|vbr-bp15ihkk93ezxppk\*\*\*\*|边界路由器实例ID。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=DescribeSagVbrRelations
&VbrInstanceIds.1=vbr-bp15ihkk93ezxppkd****
&VbrRegionId=cn-hangzhou
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<DescribeSagVbrRelationsResponse>
  <RequestId>17D79124-104A-42DB-8FCA-CE2957CD1723</RequestId>
  <SagVbrRelations>
        <VbrInstanceId>vbr-bp15ihkk93ezxppkd****</VbrInstanceId>
        <SagInstanceId>sag-0nnteglltw6z4b****</SagInstanceId>
        <SagUid>16884015</SagUid>
  </SagVbrRelations>
</DescribeSagVbrRelationsResponse>
```

`JSON` 格式

```
{
	"RequestId": "17D79124-104A-42DB-8FCA-CE2957CD1723",
	"SagVbrRelations": [
		{
			"VbrInstanceId": "vbr-bp15ihkk93ezxppkd****",
			"SagInstanceId": "sag-0nnteglltw6z4b****",
			"SagUid": "16884015"
		}
	]
}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|Forbidden|User not authorized to operate on the specified resource.|用户没有操作此资源的权限。|
|400|Param.InvalidVersionComparator|The specified version comparison operator is invalid.|非法的版本比较操作值。|
|400|InvalidRegionID|The specified regionId does not exist.|指定的RegionId不存在|

访问[错误中心](https://error-center.alibabacloud.com/status/product/Smartag)查看更多错误码。

