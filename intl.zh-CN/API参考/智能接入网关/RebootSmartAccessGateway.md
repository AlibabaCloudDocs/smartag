# RebootSmartAccessGateway {#doc_api_Smartag_RebootSmartAccessGateway .reference}

调用RebootSmartAccessGateway重启智能接入网关实例。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=RebootSmartAccessGateway&type=RPC&version=2018-03-13)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|RegionId|String|是|cn-shanghai|地域ID。

 |
|SmartAGId|String|是|sag-w9unmktmupcde\*\*\*\*\*|智能接入网关实例ID。

 |
|Action|String|否|RebootSmartAccessGateway|要执行的操作，取值：**RebootSmartAccessGateway**。

 |
|SerialNumber|String|否|a1b2c3d4e5f6g7h8f9|硬件序列号。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|B1792769-5CC3-4D6F-A5A5-E6408EBFBAD0|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=RebootSmartAccessGateway
&RegionId=cn-shanghai
&SmartAGId=sag-w9unmktmupcde*****
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<RebootSmartAccessGatewayResponse>
	  <requestId>B1792769-5CC3-4D6F-A5A5-E6408EBFBAD0</requestId>
</RebootSmartAccessGatewayResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"requestId":"B1792769-5CC3-4D6F-A5A5-E6408EBFBAD0"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.alibabacloud.com/status/product/Smartag)查看更多错误码。

