# DescribeUserOnlineClients {#doc_api_Smartag_DescribeUserOnlineClients .reference}

调用DescribeUserOnlineClients根据用户名和智能接入网关APP实例ID查询指定用户在线连接列表。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Smartag&api=DescribeUserOnlineClients)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|RegionId|String|是|cn-shanghai|智能接入网关APP实例所在的地域。

 |
|SmartAGId|String|是|sag-wfjgn\*\*\*\*\*\*\*\*\*\*|智能接入网关APP实例ID。

 |
|UserName|String|是|doctest|用户名，同一个智能接入网关APP实例下的用户名不可以重复。

 用户名和密码相互依赖，若指定用户名则必须指定密码，反之，若指定密码则必须指定用户名。

 |
|Action|String|否|DescribeUserOnlineClients|要执行的操作。

 取值：**DescribeUserOnlineClients**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|7108A98F-C47D-45F7-A4D8-C2E3022735DA|请求ID。

 |
|Users| | |用户信息。

 |
|ClientIp|String|10.\*\*.\*\*.\*\*|阿里云APP客户端IP。

 |
|OnlineTime|String|1559125519|上线时间。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeUserOnlineClients
&RegionId=cn-shanghai
&SmartAGId=sag-wfjgn**********
&UserName=doctest
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeUserOnlineClientsResponse>
  <Users>
    <User>
      <OnlineTime>1559125519</OnlineTime>
      <ClientIp>192.168.0.2</ClientIp>
    </User>
  </Users>
  <RequestId>92B22889-5451-4A1D-9432-66ED5AB3DD04</RequestId>
</DescribeUserOnlineClientsResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Users":{
		"User":[
			{
				"OnlineTime":"1559125519",
				"ClientIp":"192.168.0.2"
			}
		]
	},
	"RequestId":"92B22889-5451-4A1D-9432-66ED5AB3DD04"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|ClientUser.NameEmpty|You must specify UserName.|用户名不能为空。|
|400|ClientUser.NameInvalid|The specified UserName is invalid.|用户名格式非法。|
|400|SAG.InstanceIdEmpty|You must specify the SAG instance ID.|智能网关实例ID为空。|
|400|SAG.InstanceNoFound|The specified SAG instance does not exist.|智能网关实例不存在。|

访问[错误中心](https://error-center.alibabacloud.com/status/product/Smartag)查看更多错误码。

