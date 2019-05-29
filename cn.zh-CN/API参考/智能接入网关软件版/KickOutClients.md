# KickOutClients {#doc_api_Smartag_KickOutClients .reference}

调用KickOutClients根据智能接入网关软件版实例ID和用户名，剔除在线连接。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Smartag&api=KickOutClients)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|RegionId|String|是|cn-shanghai|智能接入网关软件版实例所在的地域。

 |
|SmartAGId|String|是|sag-ehjfb\*\*\*\*\*\*\*|智能接入网关软件版实例ID。

 |
|Username|String|是|doctest|用户名，同一个智能接入网关软件版实例下的用户名不可以重复。

 用户名和密码相互依赖，若指定用户名则必须指定密码，反之，若指定密码则必须指定用户名。

 |
|Action|String|否|KickOutClients|要执行的操作。

 取值：**KickOutClients**

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|76FD7E08-6AA1-4B1B-99FB-8B3CA6C99A8E|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=KickOutClients
&RegionId=cn-shanghai
&SmartAGId=sag-ehjfb*******
&Username=doctest
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<KickOutClients>
  <RequestId>7108A98F-C47D-45F7-A4D8-C2E3022735DA</RequestId>
</KickOutClients>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"7108A98F-C47D-45F7-A4D8-C2E3022735DA"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|ClientUser.NameEmpty|You must specify UserName.|用户名不能为空。|
|400|SAG.InstanceNoFound|The specified SAG instance does not exist.|智能网关实例不存在。|

[查看本产品错误码](https://error-center.aliyun.com/status/product/Smartag)

