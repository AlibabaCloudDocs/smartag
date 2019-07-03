# DeleteSmartAccessGatewayClientUser {#doc_api_Smartag_DeleteSmartAccessGatewayClientUser .reference}

调用DeleteSmartAccessGatewayClientUser删除APP客户端用户。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Smartag&api=DeleteSmartAccessGatewayClientUser)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|RegionId|String|是|cn-shanghai|智能接入网关APP实例地域。

 |
|SmartAGId|String|是|sag-hdjffn\*\*\*\*\*\*|智能接入网关APP实例ID。

 |
|UserName|String|是|doctest|用户名，同一个智能接入网关APP实例下的用户名不可以重复。

 用户名和密码相互依赖，若指定用户名则必须指定密码，反之，若指定密码则必须指定用户名。

 |
|Action|String|否|DeleteSmartAccessGatewayClientUser|要执行的操作。

 取值：**DeleteSmartAccessGatewayClientUser**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|09AD82DC-FE26-4B66-B526-2FA6BE82A4D3|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DeleteSmartAccessGatewayClientUser
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DeleteSmartAccessGatewayClientUserResponse>
  <RequestId>09AD82DC-FE26-4B66-B526-2FA6BE82A4D3</RequestId>
</DeleteSmartAccessGatewayClientUserResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"09AD82DC-FE26-4B66-B526-2FA6BE82A4D3"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|SAG.InstanceIdEmpty|You must specify the SAG instance ID.|智能网关实例ID为空。|
|400|SAG.InstanceNoFound|The specified SAG instance does not exist.|智能网关实例不存在。|
|400|ClientUser.NameEmpty|You must specify UserName.|用户名不能为空。|
|400|ClientUser.NameInvalid|The specified UserName is invalid.|用户名格式非法。|

访问[错误中心](https://error-center.alibabacloud.com/status/product/Smartag)查看更多错误码。

