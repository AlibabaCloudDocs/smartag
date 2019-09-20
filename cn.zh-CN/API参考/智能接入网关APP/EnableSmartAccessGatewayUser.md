# EnableSmartAccessGatewayUser {#doc_api_Smartag_EnableSmartAccessGatewayUser .reference}

调用EnableSmartAccessGatewayUser激活智能接入网关的用户。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=EnableSmartAccessGatewayUser&type=RPC&version=2018-03-13)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|RegionId|String|是|cn-shanghai|智能接入网关实例所属的地域ID。

 |
|SmartAGId|String|是|sag-va03wf4l4idaj\*\*\*\*\*|智能接入网关APP实例ID。

 |
|UserName|String|是|1234|用户名。

 |
|Action|String|否|EnableSmartAccessGatewayUser|要执行的操作，取值：**EnableSmartAccessGatewayUser**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|F5894299-84A2-48C1-A999-28908B99F45D|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=EnableSmartAccessGatewayUser
&RegionId=cn-shanghai
&SmartAGId=sag-va03wf4l4idaj*****
&UserName=1234
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<EnableSmartAccessGatewayUserResponse>
	  <RequestId>F5894299-84A2-48C1-A999-28908B99F45D</RequestId>
</EnableSmartAccessGatewayUserResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"F5894299-84A2-48C1-A999-28908B99F45D"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|Forbbiden.SubUser|You are not authorized to operate on the specified resource.|您不具有操作指定资源的权限|
|403|Forbidden|User not authorized to operate on the specified resource.|用户没有操作此资源的权限|

访问[错误中心](https://error-center.aliyun.com/status/product/Smartag)查看更多错误码。

