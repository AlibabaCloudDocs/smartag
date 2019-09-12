# ModifySagRemoteAccess {#doc_api_Smartag_ModifySagRemoteAccess .reference}

调用ModifySagRemoteAccess修改智能接入网关设备的远程访问IP。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=ModifySagRemoteAccess&type=RPC&version=2018-03-13)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|SerialNumber|String|是|sag-100-v1p7-9|智能接入网关设备序列号。

 |
|SmartAGId|String|是|sag-r79m060r6oy55\*\*\*\*\*\*|智能接入网关实例ID。

 |
|Action|String|否|ModifySagRemoteAccess|要执行的操作。

 取值：**ModifySagRemoteAccess**。

 |
|RemoteAccessIp|String|否|10.10.10.2|远程访问IP。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|返回的状态码。

 |
|Message|String|Successful|接口调用返回的信息。

 |
|RemoteAccessIp|String|10.10.10.2|远程访问IP。

 |
|RequestId|String|4FF203D7-462D-498E-94F9-2B2FA462DD23|请求ID。

 |
|SerialNumber|String|sag61a344\*\*|智能接入网关的设备SN号。

 |
|Success|Boolean|true|接口调用是否成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=ModifySagRemoteAccess
&SerialNumber=sag-100-v1p7-9
&SmartAGId=sag-r79m060r6oy55******
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ModifySagRemoteAccessResponse>
	  <RemoteAccessIp>10.10.10.2</RemoteAccessIp>
	  <SerialNumber>sag61a344ge</SerialNumber>
	  <Message>Successful</Message>
	  <RequestId>4FF203D7-462D-498E-94F9-2B2FA462DD23</RequestId>
	  <Success>true</Success>
	  <Code>200</Code>
    </ModifySagRemoteAccessResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"SerialNumber":"sag61a344ge",
	"RemoteAccessIp":"10.10.10.2",
	"Message":"Successful",
	"RequestId":"4FF203D7-462D-498E-94F9-2B2FA462DD23",
	"Success":true,
	"Code":"200"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|FeatureNotSupport|The current edition of the smart access gateway does not support this feature.|智能接入网关当前版本不支持该功能特性|
|400|VersionNotExist|The specified version does not exist.|当前指定的版本不存在。|
|403|InvalidId.SMARTAG|The specified smart access gateway instance id is invalid.|无效的智能接入网关ID|
|403|SmartAccessGatewayNotOnline|The specified smart access gateway is not online.|该智能接入网关当前不是在线状态，无法完成操作。|
|403|FeatureNotSupportForStandBySmartAG|The current edition of the standby smart access gateway does not support this feature.|备智能接入网关的当前版本不支持该功能特性|
|403|FeatureNotSupportForActiveSmartAG|The current edition of the active smart access gateway does not support this feature.|主智能接入网关的当前版本不支持该功能特性|
|403|IllegalRemoteIp.Conflict|The specified IP address has been used.|指定的IP地址已经被使用过。|
|403|IllegalRemoteIp.RouteTableEntryConflict|The specified IP address conflicts with route table entries.|指定的IP地址与路由表条目冲突。|

访问[错误中心](https://error-center.aliyun.com/status/product/Smartag)查看更多错误码。

