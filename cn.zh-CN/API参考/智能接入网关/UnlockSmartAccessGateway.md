# UnlockSmartAccessGateway {#doc_api_Smartag_UnlockSmartAccessGateway .reference}

调用UnlockSmartAccessGateway解锁智能接入网关实例。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=UnlockSmartAccessGateway&type=RPC&version=2018-03-13)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|SmartAGId|String|是|sag-w9unmktmupcde\*\*\*\*\*|智能接入网关实例ID。

 |
|Action|String|否|UnlockSmartAccessGateway|要执行的操作，取值：**UnlockSmartAccessGateway**。

 |
|RegionId|String|否|cn-shanghai|地域ID。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|05DC546B-DBF9-4028-88CD-1742AB4E014C|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=UnlockSmartAccessGateway
&SmartAGId=sag-w9unmktmupcde*****
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<UnlockSmartAccessGatewayResponse>
	  <RequestId>05DC546B-DBF9-4028-88CD-1742AB4E014C</RequestId>
</UnlockSmartAccessGatewayResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"05DC546B-DBF9-4028-88CD-1742AB4E014C"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|Forbidden|User not authorized to operate on the specified resource.|用户没有操作此资源的权限|
|403|InvalidId.SMARTAG|The specified smart access gateway instance id is invalid.|无效的智能接入网关ID|
|403|MissingParameter|The input parameter is missing, please check your input.|输入参数缺失，请检查您的输入|

访问[错误中心](https://error-center.aliyun.com/status/product/Smartag)查看更多错误码。

