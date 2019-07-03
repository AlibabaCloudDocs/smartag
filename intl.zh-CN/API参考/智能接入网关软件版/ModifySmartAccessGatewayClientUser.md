# ModifySmartAccessGatewayClientUser {#doc_api_Smartag_ModifySmartAccessGatewayClientUser .reference}

调用ModifySmartAccessGatewayClientUser修改用户带宽。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Smartag&api=ModifySmartAccessGatewayClientUser)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Bandwidth|Integer|是|2|带宽，单位Kbps，最大2000Kbps。

 |
|RegionId|String|是|cn-shanghai|智能接入网关APP实例地域。

 |
|SmartAGId|String|是|sag-kdhej\*\*\*\*\*\*\*8|智能接入网关APP实例ID。

 |
|UserName|String|是|doctest|用户名，同一个智能接入网关APP实例下的用户名不可以重复。

 用户名和密码相互依赖，若指定用户名则必须指定密码，反之，若指定密码则必须指定用户名。

 |
|Action|String|否|ModifySmartAccessGatewayClientUser|要执行的操作。

 取值：**ModifySmartAccessGatewayClientUser**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Bandwidth|Integer|2|带宽。

 |
|ClientIp|String|10.\*\*.\*\*.\*\*|APP客户端的IP地址。

 |
|RequestId|String|5F0078B5-8AAD-4B53-8351-4C91B8EA528A|请求ID。

 |
|UserMail|String|test@example.com|普通用户的邮箱地址。

 |
|UserName|String|doctes|用户名。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=ModifySmartAccessGatewayClientUser
&Bandwidth=2
&RegionId=cn-shanghai
&SmartAGId=sag-kdhej*******8
&UserName=doctest
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ModifySmartAccessGatewayClientUserResponse>
  <RequestId>5F0078B5-8AAD-4B53-8351-4C91B8EA528A</RequestId>
  <UserMail>dd@example.com</UserMail>
  <UserName>dd@example.com</UserName>
  <Bandwidth>1</Bandwidth>
</ModifySmartAccessGatewayClientUserResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"5F0078B5-8AAD-4B53-8351-4C91B8EA528A",
	"UserMail":"dd@example.com",
	"UserName":"dd@example.com",
	"Bandwidth":1
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|ClientUser.BandwidthInvalid|The specified Bandwidth is invalid.|用户带宽非法。|
|400|ClientUser.NameEmpty|You must specify UserName.|用户名不能为空。|
|400|ClientUser.NameInvalid|The specified UserName is invalid.|用户名格式非法。|
|400|SAG.InstanceIdEmpty|You must specify the SAG instance ID.|智能网关实例ID为空。|
|400|SAG.InstanceNoFound|The specified SAG instance does not exist.|智能网关实例不存在。|

访问[错误中心](https://error-center.alibabacloud.com/status/product/Smartag)查看更多错误码。

