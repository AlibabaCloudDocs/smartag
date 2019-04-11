# UnbindSmartAccessGateway {#doc_api_1108695 .reference}

调用UnbindSmartAccessGateway将智能接入网关从指定的云连接网中解绑。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Smartag&api=UnbindSmartAccessGateway)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|CcnId|String|是|ccn-kygbldwikz\*\*\*\*\*\*\*\*|云连接网ID。

 |
|RegionId|String|是|cn-hangzhou|智能接入网关的所属区域。

 |
|SmartAGId|String|是|sag-0ovhf732a\*\*\*\*\*\*\*\*|智能接入网关的ID。

 |
|Action|String|否|UnbindSmartAccessGateway|执行的操作。

 取值： **UnbindSmartAccessGateway**

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|CE6642D4-21EB-4168-9BF9-F217953F9892|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?CcnId=ccn-kygbldwikz********
&RegionId=cn-hangzhou
&SmartAGId=sag-0ovhf732a********
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<UnbindSmartAccessGatewayResponse>
  <RequestId>CE6642D4-21EB-4168-9BF9-F217953F9892</RequestId>
</UnbindSmartAccessGatewayResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"CE6642D4-21EB-4168-9BF9-F217953F9892"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|MissingParameter|The input parameter is missing, please check your input.|输入参数缺失，请检查您的输入|
|403|InvalidId.SMARTAG|The specified smart access gateway instance id is invalid.|无效的智能接入网关ID|
|403|SmartAccessGatewayNotBind|The instance has not yet been bound.|该实例未被绑定|
|403|Forbidden|User not authorized to operate on the specified resource.|用户没有操作此资源的权限|
|500|SmartAccessGatewayNotActivated|The specified Smart Access Gateway has not been activated.|该智能接入网关尚未激活，请先激活该实例。|
|403|AlreadyBound.CEN|This instance has been bound, please unbind first.|该实例已经绑定了云企业网，请先解绑|

[查看本产品错误码](https://error-center.aliyun.com/status/product/Smartag)

