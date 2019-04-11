# UpgradeSmartAccessGateway {#doc_api_1109003 .reference}

调用UpgradeSmartAccessGateway接口升高智能接入网关实例的带宽。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Smartag&api=UpgradeSmartAccessGateway)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|AutoPay|Boolean|是|true|是否是自动支付预付费实例的账单。

 取值：**true|false**（默认值）

 |
|BandWidthSpec|Long|是|3|智能接入网关的带宽。

 -   如果网关设备规格为sag-100wm，带宽取值：2~50Mbps
-   如果网关设备规格为sag-1000，带宽取值：10~500Mbps

 |
|RegionId|String|是|cn-hangzhou|智能接入网关的地域ID。

 |
|SmartAGId|String|是|sag-d3m51apgw4po\*\*\*\*\*\*|智能接入网关实例ID。

 |
|Action|String|否|UpgradeSmartAccessGateway|要执行的操作。

 取值： **UpgradeSmartAccessGateway**

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|OrderId|String|203384676330296|订单ID。

 |
|RequestId|String|45F07029-1783-4B2D-B4CE-45B9EAA58440|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?AutoPay=true
&BandWidthSpec=3
&RegionId=cn-hangzhou
&SmartAGId=sag-d3m51apgw4po******
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<UpgradeSmartAccessGateway>
  <RequestId>45F07029-1783-4B2D-B4CE-45B9EAA58440</RequestId>
  <OrderId>203384676330296</OrderId>
</UpgradeSmartAccessGateway>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"OrderId":203384676330296,
	"RequestId":"45F07029-1783-4B2D-B4CE-45B9EAA58440"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Smartag)

