# ActivateSmartAccessGateway {#doc_api_Smartag_ActivateSmartAccessGateway .reference}

调用ActivateSmartAccessGateway激活智能接入网关设备。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Smartag&api=ActivateSmartAccessGateway)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|RegionId|String|是|cn-hangzhou|智能接入网关实例所在的地域ID。

 |
|SmartAGId|String|是|sag-ke3kq4evpi8p7\*\*\*\*\*\*|智能接入网关实例ID。

 |
|Action|String|否|ActivateSmartAccessGateway|要执行的操作。

 取值：**ActivateSmartAccessGateway**。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|E223E535-AE11-4158-B00F-DC107887A909|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=ActivateSmartAccessGateway
&RegionId=cn-hangzhou
&SmartAGId=sag-ke3kq4evpi8p7******
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ActivateSmartAccessGatewayResponse>
  <RequestId>E223E535-AE11-4158-B00F-DC107887A909</RequestId>
</ActivateSmartAccessGatewayResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"E223E535-AE11-4158-B00F-DC107887A909"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|500|SmartAccessGatewayActivateFailed|An error has occurred while activating the specified Smart Access Gateway.|智能接入网关激活失败，请稍后再试。|

[查看本产品错误码](https://error-center.aliyun.com/status/product/Smartag)

