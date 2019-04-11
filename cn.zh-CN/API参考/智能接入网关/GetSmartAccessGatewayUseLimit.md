# GetSmartAccessGatewayUseLimit {#doc_api_1109140 .reference}

调用GetSmartAccessGatewayUseLimit查询可购买的智能接入网关数量。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Smartag&api=GetSmartAccessGatewayUseLimit)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|RegionId|String|是|cn-hangzhou|智能接入网关的所属区域。

 |
|Action|String|否|GetSmartAccessGatewayUseLimit|要执行的操作。

 取值： **GetSmartAccessGatewayUseLimit**

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|2265DB11-F5CC-496E-ADE7-D043AC37926A|请求ID。

 |
|TotalAmount|Integer|500|可购买的智能接入网关总数。

 |
|UsedAmount|Integer|47|已购买的智能接入网关数量。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://smartag.cn-shanghai.aliyuncs.com/?Action=GetSmartAccessGatewayUseLimit
&SmartAGId=sag-0ovhf732a9j0pt0aeo
&Name=DocTest
&CommonParameters

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
https://smartag.cn-shanghai.aliyuncs.com/?Action=GetSmartAccessGatewayUseLimit
&SmartAGId=sag-0ovhf732a9j0pt0aeo
&Name=DocTest
&CommonParameters
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"2265DB11-F5CC-496E-ADE7-D043AC37926A",
	"TotalAmount":500,
	"UsedAmount":47
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|Forbidden|User not authorized to operate on the specified resource.|用户没有操作此资源的权限|

[查看本产品错误码](https://error-center.aliyun.com/status/product/Smartag)

