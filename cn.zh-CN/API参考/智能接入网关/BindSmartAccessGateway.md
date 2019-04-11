# BindSmartAccessGateway {#doc_api_1108016 .reference}

调用BindSmartAccessGateway接口将智能接入网关绑定到指定的云连接网中。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Smartag&api=BindSmartAccessGateway)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|CcnId|String|是|ccn-isdjvvkexkrpk\*\*\*\*\*|要绑定的云连接网ID。

 |
|SmartAGId|String|是|sag-m7ez44zpayma\*\*\*\*\*|智能接入网关ID。

 |
|Action|String|否|BindSmartAccessGateway|执行的操作。

 取值： **BindSmartAccessGateway**

 |
|RegionId|String|否|cn-hangzhou|智能接入网关的所属区域。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|8A3FF8DD-B27D-4ED2-B032-5EF90B38195D|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=BindSmartAccessGateway
&CcnId=ccn-isdjvvkexkrpk*****
&SmartAGId=sag-m7ez44zpayma*****
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<BindSmartAccessGatewayResponse>
  <RequestId>6877D55B-08F7-4DA3-916B-32A6FD402E06</RequestId>
</BindSmartAccessGatewayResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"6877D55B-08F7-4DA3-916B-32A6FD402E06"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|CidrConflict|Cidr is conflict, Please Check your input.|子网网段冲突，请检查输入|
|403|MissingParameter|The input parameter is missing, please check your input.|输入参数缺失，请检查您的输入|
|403|InvalidId.CCN|Invalid cloud connect network id.|无效的云连接网ID|
|403|InvalidId.SMARTAG|The specified smart access gateway instance id is invalid.|无效的智能接入网关ID|
|403|SmartAccessGatewayAlreadyBound|The smart access gateway already bound.|该智能接入网关已经绑定|
|500|TunnelIdDistributeError|Tunnel id distribute error.|隧道ID分配出错|
|403|TunnelIdNotEnough|Tunnel id is not enough.|隧道ID不足|
|500|UpdateError.SMARTAG|Update smart access gateway error.|更新智能接入网关出错|
|403|Forbidden|User not authorized to operate on the specified resource.|用户没有操作此资源的权限|
|500|SmartAccessGatewayInArrears|The specified Smart Access Gateway has expired.|该智能接入网关已经到期停服，请续费。|
|500|SmartAccessGatewayNotActivated|The specified Smart Access Gateway has not been activated.|该智能接入网关尚未激活，请先激活该实例。|

[查看本产品错误码](https://error-center.aliyun.com/status/product/Smartag)

