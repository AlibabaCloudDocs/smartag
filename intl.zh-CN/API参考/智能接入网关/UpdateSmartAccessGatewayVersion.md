# UpdateSmartAccessGatewayVersion {#doc_api_1139399 .reference}

调用UpdateSmartAccessGatewayVersion升级智能接入网关的软件版本。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Smartag&api=UpdateSmartAccessGatewayVersion)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|RegionId|String|是|cn-hangzhou|智能接入网关的所属区域。

 |
|SmartAGId|String|是|sag-0ovhf732a9j\*\*\*\*\*\*\*|智能接入网关的ID。

 |
|VersionCode|String|是|1.0.1|要升级的智能接入网关的版本。

 |
|Action|String|否|UpdateSmartAccessGatewayVersion|执行的操作。

 取值： **UpdateSmartAccessGatewayVersion**

 |
|SerialNumber|String|否|sag233a234i55|智能接入网关设备序列号。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|CE6642D4-21EB-4168-9BF9-F217953F9892|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://smartag.cn-shanghai.aliyuncs.com/?Action=UpdateSmartAccessGatewayVersion
&SmartAGId=sag-0ovhf732a9j0pt0aeo
&VersionCode=2.0
&CommonParameters

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<UpdateSmartAccessGatewayVersionResponse>
  <RequestId>CE6642D4-21EB-4168-9BF9-F217953F9892</RequestId>
</UpdateSmartAccessGatewayVersionResponse>

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
|403|Forbidden|User not authorized to operate on the specified resource.|用户没有操作此资源的权限|
|500|SmartAccessGatewayInArrears|The specified Smart Access Gateway has expired.|该智能接入网关已经到期停服，请续费。|
|500|SmartAccessGatewayNotActivated|The specified Smart Access Gateway has not been activated.|该智能接入网关尚未激活，请先激活该实例。|
|403|InvalidId.SMARTAG|The specified smart access gateway instance id is invalid.|无效的智能接入网关ID|
|500|PermissionError|No permission to operate the instance.|没有操作该实例的权限|
|403|NotBoundCCN|The specified smart access gateway has not bound CCN; please bind CCN first.|该智能接入网关没有绑定CCN；请先绑定CCN。|
|403|SmartAccessGatewayNotOnline|The specified smart access gateway is not online.|该智能接入网关当前不是在线状态，无法完成操作。|
|403|GetSmartAccessGatewayVersionError|An error occurred while obtaining the smart access gateway version.|获取智能接入网关版本失败。|
|403|GetSmartAccessGatewayStateError|An error occurred while obtaining the smart access gateway status.|获取智能接入网关状态失败。|
|403|VersionTooOld|The specified version is outdated; please select a newer version.|该版本过低，请选择较新的版本。|

[查看本产品错误码](https://error-center.aliyun.com/status/product/Smartag)

