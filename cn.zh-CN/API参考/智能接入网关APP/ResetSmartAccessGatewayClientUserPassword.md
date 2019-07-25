# ResetSmartAccessGatewayClientUserPassword {#doc_api_Smartag_ResetSmartAccessGatewayClientUserPassword .reference}

调用ResetSmartAccessGatewayClientUserPassword重置APP客户端密码。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=ResetSmartAccessGatewayClientUserPassword&type=RPC&version=2018-03-13)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|RegionId|String|是|cn-shanghai|智能接入网关APP客户端地域。

 |
|SmartAGId|String|是|sag-jdfnf\*\*\*\*\*\*\*\*\*|智能接入网关APP实例ID。

 |
|UserName|String|是|doctest|用户名，同一个智能接入网关APP实例下的用户名不可以重复。

 用户名和密码相互依赖，若指定用户名则必须指定密码，反之，若指定密码则必须指定用户名。

 |
|Action|String|否|ResetSmartAccessGatewayClientUserPassword|要执行的操作。

 取值：**ResetSmartAccessGatewayClientUserPassword**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|BE1F7E80-4558-4021-B6D2-B94DA8AAAF81|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=ResetSmartAccessGatewayClientUserPassword
&RegionId=cn-shanghai
&SmartAGId=sag-jdfnf*********
&UserName=doctest
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ResetSmartAccessGatewayClientUserPasswordResponse>
	  <RequestId>BE1F7E80-4558-4021-B6D2-B94DA8AAAF81</RequestId>
    </ResetSmartAccessGatewayClientUserPasswordResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"BE1F7E80-4558-4021-B6D2-B94DA8AAAF81"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|ClientUser.NameEmpty|You must specify UserName.|用户名不能为空。|
|400|ClientUser.NameInvalid|The specified UserName is invalid.|用户名格式非法。|
|400|SAG.InstanceIdEmpty|You must specify the SAG instance ID.|智能网关实例ID为空。|
|400|SAG.InstanceNoFound|The specified SAG instance does not exist.|智能网关实例不存在。|

访问[错误中心](https://error-center.aliyun.com/status/product/Smartag)查看更多错误码。

