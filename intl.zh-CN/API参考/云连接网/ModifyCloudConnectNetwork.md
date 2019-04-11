# ModifyCloudConnectNetwork {#doc_api_1109158 .reference}

调用ModifyCloudConnectNetwork修改云连接网的名称和描述。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Smartag&api=ModifyCloudConnectNetwork)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|CcnId|String|是|ccn-l9340rlu5ens\*\*\*\*\*|云连接网ID。

 |
|RegionId|String|是|cn-hangzhou|云连接网的所属区域。

 |
|Action|String|否|ModifyCloudConnectNetwork|要执行的操作。

 取值： **ModifyCloudConnectNetwork**

 |
|Description|String|否|ccn描述|云连接网的描述。

 长度为2-256个字符，必须以字母或中文开头，但不能以`http://`或 `https://`开头。

 |
|Name|String|否|ccn名称|云连接网的名称。

 长度为2-128个字符，必须以字母或中文开头，可包含数字，点号（.），下划线（\_）和短横线（-），但不能以`http://`或`https://`开头。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|0BAAF2B9-88B8-4574-BDBE-102A90EE3FEE|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://smartag.cn-shanghai.aliyuncs.com/?Action=ModifyCloudConnectNetwork
&RegionId=cn-shanghai
&CcnId=ccn-l9340rlu5enstmzj5
&Description=ConnectChina
&CommonParameters

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ModifyCloudConnectNetworkResponse>
  <RequestId>0BAAF2B9-88B8-4574-BDBE-102A90EE3FEE</RequestId>
</ModifyCloudConnectNetworkResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"0BAAF2B9-88B8-4574-BDBE-102A90EE3FEE"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|MissingParameter|The input parameter is missing, please check your input.|输入参数缺失，请检查您的输入|
|403|InvalidId.CCN|Invalid cloud connect network id.|无效的云连接网ID|
|403|UpdateError.CCN|Update cloud connect network error.|更新云连接网失败|
|403|Forbidden|User not authorized to operate on the specified resource.|用户没有操作此资源的权限|

[查看本产品错误码](https://error-center.aliyun.com/status/product/Smartag)

