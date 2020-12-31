# UpdateSmartAGDpiAttribute

调用UpdateSmartAGDpiAttribute开启或关闭智能接入网关实例应用识别DPI（Deep Packet Inspection）功能。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=UpdateSmartAGDpiAttribute&type=RPC&version=2018-03-13)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|UpdateSmartAGDpiAttribute|要执行的操作。

取值：**UpdateSmartAGDpiAttribute**。 |
|DpiEnabled|Boolean|是|true|是否开启智能接入网关实例DPI功能。取值：

-   **true**：开启。
-   **false**：关闭。 |
|RegionId|String|是|cn-shanghai|智能接入网关实例所属地域ID。 |
|SmartAGId|String|是|sag-tq3sazs17smldn\*\*\*\*|智能接入网关实例ID。 |
|ClientToken|String|否|02fb3da4-130e\*\*\*\*|客户端Token，用于保证请求的幂等性。

由客户端生成该参数值，要保证在不同请求间唯一，最大值不超过64个ASCII字符。 |
|DryRun|Boolean|否|false|是否只预检此次请求。取值：

-   **true**：表示只预检此次请求合法性，不会开启或关闭智能接入网关实例的DPI功能。检查项包括是否填写了必需参数、请求格式、实例状态等。如果检查不通过，则返回对应错误；如果检查通过，则返回对应请求ID。
-   **false**（默认）：表示发送正常请求，通过检查后直接开启或关闭智能接入网关实例的DPI功能。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|0C2EE7A8-74D4-4081-8236-CEBDE3BBCF50|请求ID。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=UpdateSmartAGDpiAttribute
&DpiEnabled=true
&RegionId=cn-shanghai
&SmartAGId=sag-tq3sazs17smldn****
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<UpdateSmartAGDpiAttributeResponse>
  <RequestId>0C2EE7A8-74D4-4081-8236-CEBDE3BBCF50</RequestId>
</UpdateSmartAGDpiAttributeResponse>
```

`JSON` 格式

```
{"RequestId":"0C2EE7A8-74D4-4081-8236-CEBDE3BBCF50"}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidSmartAGId.NotFound|The specified SmartAGId does not exist.|根据SmartAGId未找到对应实例。|
|403|FeatureNotSupport|The current edition of the smart access gateway does not support this feature.|智能接入网关当前版本不支持该功能特性。|
|403|FeatureNotSupportForActiveSmartAG|The current edition of the active smart access gateway does not support this feature.|主智能接入网关的当前版本不支持该功能特性。|
|403|FeatureNotSupportForStandBySmartAG|The current edition of the standby smart access gateway does not support this feature.|备智能接入网关的当前版本不支持该功能特性。|

访问[错误中心](https://error-center.aliyun.com/status/product/Smartag)查看更多错误码。

