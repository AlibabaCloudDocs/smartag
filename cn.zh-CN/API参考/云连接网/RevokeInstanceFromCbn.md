# RevokeInstanceFromCbn {#doc_api_Smartag_RevokeInstanceFromCbn .reference}

调用RevokeInstanceFromCbn撤销云企业网对云连接网的授权。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=RevokeInstanceFromCbn&type=RPC&version=2018-03-13)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|CcnInstanceId|String|是|ccn-n2935s1mnwv8i\*\*\*\*\*|云连接网的实例ID。

 |
|CenInstanceId|String|是|cen-7qthudw0ll6jm\*\*\*\*\*|云企业网的实例ID。

 |
|RegionId|String|是|cn-shanghai|地域ID。

 |
|Action|String|否|RevokeInstanceFromCbn|要执行的操作，取值：**RevokeInstanceFromCbn**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|07D73949-2508-4169-8C64-7CCDB33871C4|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=RevokeInstanceFromCbn
&CcnInstanceId=ccn-n2935s1mnwv8i*****
&CenInstanceId=cen-7qthudw0ll6jm*****
&RegionId=cn-shanghai
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<RevokeInstanceFromCbnResponse>
	  <RequestId>07D73949-2508-4169-8C64-7CCDB33871C4</RequestId>
</RevokeInstanceFromCbnResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"07D73949-2508-4169-8C64-7CCDB33871C4"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Smartag)查看更多错误码。

