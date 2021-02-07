# UpdateSmartAccessGatewayVersion

调用UpdateSmartAccessGatewayVersion升级智能接入网关设备的软件版本。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=UpdateSmartAccessGatewayVersion&type=RPC&version=2018-03-13)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|UpdateSmartAccessGatewayVersion|执行的操作。

 取值： **UpdateSmartAccessGatewayVersion** |
|RegionId|String|是|cn-hangzhou|智能接入网关实例所属地域。 |
|SmartAGId|String|是|sag-0ovhf732a9j\*\*\*\*\*\*\*|智能接入网关实例ID。 |
|VersionCode|String|是|1.0.1|要升级的智能接入网关的版本。 |
|SerialNumber|String|否|sag233\*\*\*\*|智能接入网关设备序列号。 |
|VersionType|String|否|Device|指定要升级的软件版本类型。取值：

 -   **Device**：表示智能接入网关设备运行的操作系统软件。
-   **Dpi**：表示智能接入网关设备运行的应用特征库软件。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|CE6642D4-21EB-4168-9BF9-F217953F9892|请求ID。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=UpdateSmartAccessGatewayVersion
&RegionId=cn-hangzhou
&SmartAGId=sag-0ovhf732a9j*******
&VersionCode=1.0.1
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<UpdateSmartAccessGatewayVersionResponse>
  <RequestId>CE6642D4-21EB-4168-9BF9-F217953F9892</RequestId>
</UpdateSmartAccessGatewayVersionResponse>
```

`JSON` 格式

```
{
   "RequestId":"CE6642D4-21EB-4168-9BF9-F217953F9892"
}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|Forbidden|User not authorized to operate on the specified resource.|用户没有操作此资源的权限。|
|500|SmartAccessGatewayInArrears|The specified Smart Access Gateway has expired.|该智能接入网关已经到期停服，请续费。|
|500|SmartAccessGatewayNotActivated|The specified Smart Access Gateway has not been activated.|该智能接入网关尚未激活，请先激活该实例。|
|403|InvalidId.SMARTAG|The specified smart access gateway instance id is invalid.|无效的智能接入网关ID|
|500|PermissionError|No permission to operate the instance.|没有操作该实例的权限。|
|403|NotBoundCCN|The specified smart access gateway has not bound CCN; please bind CCN first.|该智能接入网关没有绑定CCN；请先绑定CCN。|
|403|SmartAccessGatewayNotOnline|The specified smart access gateway is not online.|该智能接入网关当前不是在线状态，无法完成操作。|
|403|GetSmartAccessGatewayVersionError|An error occurred while obtaining the smart access gateway version.|获取智能接入网关版本失败。|
|403|GetSmartAccessGatewayStateError|An error occurred while obtaining the smart access gateway status.|获取智能接入网关状态失败。|
|403|VersionTooOld|The specified version is outdated; please select a newer version.|该版本过低，请选择较新的版本。|

访问[错误中心](https://error-center.aliyun.com/status/product/Smartag)查看更多错误码。

