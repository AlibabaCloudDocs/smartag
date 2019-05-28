# CreateSmartAccessGatewaySoftware {#doc_api_Smartag_CreateSmartAccessGatewaySoftware .reference}

调用CreateSmartAccessGatewaySoftware创建智能接入网关软件版。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Smartag&api=CreateSmartAccessGatewaySoftware)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|AutoPay|Boolean|是|true|是否是自动支付预付费实例的账单。

 取值：**true|false**

 默认值：**false**。

 |
|ChargeType|String|是|PREPAY|实例的计费类型，取值：

 -   PayOnDemand：按量付费
-   PREPAY：预付费

 **说明：** 目前只支持预付费。

 |
|DataPlan|Long|是|5|每个账号每月赠送的流量套餐规格，单位G。

 **说明：** 目前仅支持购买5GB/月套餐。

 |
|Period|Integer|是|12|每个账号下套餐的使用时长，按月计算。如果取值超过12，必须是12的倍数。

 |
|RegionId|String|是|cn-shanghai|智能接入网关软件版实例的地域。

 |
|UserCount|Integer|是|5|软件客户端账号数规格，购买后可创建相应数量的账号，一般为每个需要登录的员工创建一个账号。

 |
|Action|String|否|CreateSmartAccessGatewaySoftware|要执行的操作。

 取值：**CreateSmartAccessGatewaySoftware**

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|OrderId|String|203782300920296|购买智能接入网关软件版订单号。

 |
|RequestId|String|24675405-74DF-4C94-82C6-B749580C498E|请求ID。

 |
|SmartAGId|String|sag-gnhe6sywtare5\*\*\*\*\*\*|智能接入网关软件版实例ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=CreateSmartAccessGatewaySoftware
&AutoPay=true
&ChargeType=PREPAY
&DataPlan=5
&Period=1
&RegionId=cn-hangzhou
&UserCount=5
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<CreateSmartAccessGatewaySoftware>
  <SmartAGId>sag-gnhe6sywtare5nt***</SmartAGId>
  <OrderId>203782300920296</OrderId>
  <RequestId>B35789C0-A570-4C2F-96D6-2B46FBB9D64A</RequestId>
</CreateSmartAccessGatewaySoftware>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"SmartAGId":"sag-gnhe6sywtare5nt***",
	"RequestId":"B35789C0-A570-4C2F-96D6-2B46FBB9D64A",
	"OrderId":203782300920296
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Smartag)

