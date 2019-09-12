# ModifySmartAccessGatewayUpBandwidth {#doc_api_Smartag_ModifySmartAccessGatewayUpBandwidth .reference}

调用ModifySmartAccessGatewayUpBandwidth修改智能接入网关参数实例。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=ModifySmartAccessGatewayUpBandwidth&type=RPC&version=2018-03-13)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|SmartAGId|String|是|sag-jsy\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*|智能接入网关实例ID。

 |
|Action|String|否|ModifySmartAccessGatewayUpBandwidth|要执行的操作。

 取值：**ModifySmartAccessGatewayUpBandwidth**。

 |
|RegionId|String|否|cn-hangzhou|智能接入网关实例所在的地域。

 |
|UpBandwidth4G|Integer|否|3|智能接入网关4G公网最大上行带宽。

 |
|UpBandwidthWan|Integer|否|2|智能接入网关WAN口最大上行带宽。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|EE837E9F-BD50-4C2B-9E47-260F9D848480|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=ModifySmartAccessGatewayUpBandwidth
&SmartAGId=sag-jsy******************
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ModifySmartAccessGatewayUpBandwidthResponse>
	  <RequestId>68CE10C0-2EFF-4B82-9907-10AB7E2B0A6C</RequestId>
    </ModifySmartAccessGatewayUpBandwidthResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"68CE10C0-2EFF-4B82-9907-10AB7E2B0A6C"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|MissingParameter|The input parameter is missing, please check your input.|输入参数缺失，请检查您的输入|
|400|InvalidName|The specified name is invalid.|您输入的名称不合法。|
|400|SAG.NotAllowConfigCidr|You cannot specify a static CIDR block when the dynamic routing strategy is used.|动态路由模式不允许配置静态地址段。|
|400|InvalidDescription|The specified description is invalid.|您输入的描述不合法。|
|403|InvalidCidr|Cidr is illegal, please check your input.|Cidr不合法，请检查您的输入|
|400|SAG.InvalidRoutingStrategy|The specified routing strategy is invalid.|非法的路由模式。|
|403|InvalidId.SMARTAG|The specified smart access gateway instance id is invalid.|无效的智能接入网关ID|

访问[错误中心](https://error-center.aliyun.com/status/product/Smartag)查看更多错误码。

