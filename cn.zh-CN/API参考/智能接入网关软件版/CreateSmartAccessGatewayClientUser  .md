# CreateSmartAccessGatewayClientUser {#doc_api_Smartag_CreateSmartAccessGatewayClientUser .reference}

调用CreateSmartAccessGatewayClientUser创建用户。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Smartag&api=CreateSmartAccessGatewayClientUser)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Bandwidth|Long|是|20|带宽，单位Kbps，最大2000Kbps。

 |
|RegionId|String|是|cn-shanghai|智能接入网关软件版实例所在地域。

 |
|SmartAGId|String|是|sag-gnhe6sywtare5\*\*\*\*\*\*|智能接入网关软件版实例ID。

 |
|UserMail|String|是|test@example.com|普通用户的邮箱地址，用于管理员向普通用户发送登录软件版客户端的账号信息。

 |
|Action|String|否|CreateSmartAccessGatewayClientUser|要执行的操作。

 取值：**CreateSmartAccessGatewayClientUser**

 |
|ClientIp|String|否|10.\*\*.\*\*.\*\*|-   如果开启，需要设置软件版客户端的IP地址。当前账号始终保持以选择的IP地址接入。

**说明：** 设置的软件版客户端IP地址必须在私网网段内。

-   如果关闭，系统自动从私网网段内分配可用IP地址，每次重连IP地址都会重新分配。

 |
|UserName|String|否|doctest|用户名，同一个智能接入网关软件版实例下的用户名不可以重复。

 用户名和密码相互依赖，若指定用户名则必须指定密码，反之，若指定密码则必须指定用户名。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Bandwidth|Integer|2|带宽。

 |
|ClientIp|String|10.\*\*.\*.\*\*|软件版客户端的IP地址。

 |
|RequestId|String|72E82F5E-66E8-4C22-BF1F-5CEB7DC132E7|请求ID。

 |
|UserMail|String|test@example.com|普通用户的邮箱地址。

 |
|UserName|String|doc|用户名，同一个智能接入网关软件版实例下的用户名不可以重复。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=CreateSmartAccessGatewayClientUser
&Bandwidth=20
&RegionId=cn-shanghai
&SmartAGId=sag-gnhe6sywtare5******
&UserMail=test@example.com
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<CreateSmartAccessGatewayClientUser>
  <IsStaticIp>0</IsStaticIp>
  <RequestId>72E82F5E-66E8-4C22-BF1F-5CEB7DC132E7</RequestId>
  <UserMail>dd@example.com</UserMail>
  <UserName>dd@example.com</UserName>
  <Bandwidth>2</Bandwidth>
</CreateSmartAccessGatewayClientUser>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"IsStaticIp":0,
	"RequestId":"72E82F5E-66E8-4C22-BF1F-5CEB7DC132E7",
	"UserMail":"dd@example.com",
	"UserName":"dd@example.com",
	"Bandwidth":2
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|ClientUser.BandwidthInvalid|The specified Bandwidth is invalid.|用户带宽非法。|
|400|ClientUser.EmailEmpty|You must specify UserEmail.|用户邮箱不能为空。|
|400|ClientUser.EmailInvalid|The format of the specified UserEmail is invalid.|用户邮箱格式非法。|
|400|ClientUser.InvalidClientIp|The specified ClientIp is invalid.|非法的用户IP|
|400|ClientUser.IpEmpty|You must specify ClientIp.|未指定静态IP。|
|400|ClientUser.IpInvalid|The specified ClientIp is invalid.|指定的静态IP非法。|
|400|ClientUser.NameEmpty|You must specify UserName.|用户名不能为空。|
|400|ClientUser.NameInvalid|The specified UserName is invalid.|用户名格式非法。|
|400|ClientUser.UserExist|The specified user already exists.|用户已经存在。|
|400|ClientUser.UserOverLimit|The maximum number of users is exceeded.|用户数已超限|
|400|SAG.CidrEmpty|You must specify the CIDR blocks of SAG.|智能网关地址段为空。|

[查看本产品错误码](https://error-center.aliyun.com/status/product/Smartag)

