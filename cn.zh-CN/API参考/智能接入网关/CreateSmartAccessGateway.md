# CreateSmartAccessGateway {#doc_api_1105138 .reference}

调用CreateSmartAccessGateway智能接入网关实例。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Smartag&api=CreateSmartAccessGateway)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|AutoPay|Boolean|是|true|是否是自动支付预付费实例的账单。

 取值：**true|false**

 默认值：**false**。

 |
|BuyerMessage|String|是|留言|买家留言信息。

 |
|ChargeType|String|是|PREPAY|实例的计费类型，取值：

 -   PayOnDemand：按量付费
-   PREPAY：预付费

 **说明：** 当前只支持预付费。` `

 |
|HaType|String|是|no\_backup|选择一种使用方式，取值：

 -   no\_backup：只购买一台智能接入网关设备接入阿里云。
-   cold\_backup：购买两台网关设备共享带宽，主设备故障时切换到备用设备。

 |
|HardWareSpec|String|是|sag-100wm|实例类型，取值：**sag-100wm|sag-1000**

 |
|MaxBandWidth|Integer|是|12|智能接入网关的带宽。

 -   如果网关设备规格为sag-100wm，带宽取值：2~50Mbps
-   如果网关设备规格为sag-1000，带宽取值：10~500Mbps

 |
|Period|Integer|是|12|购买时长，单位月。如果取值超过12，必须是12的倍数。

 |
|ReceiverAddress|String|是|XX号|网关设备的收货地址。

 |
|ReceiverCity|String|是|杭州|收货城市。

 |
|ReceiverCountry|String|是|中国|收货国家。

 |
|ReceiverDistrict|String|是|西湖|收货街区。

 |
|ReceiverEmail|String|是|xx@example.com|收货人的电子邮箱。

 |
|ReceiverMobile|String|是|13\*\*\*\*\*\*\*\*\*|收件人手机号。

 |
|ReceiverName|String|是|张三|收件人姓名。

 |
|ReceiverState|String|是|浙江|收货省份。

 |
|ReceiverZip|String|是|310000|收货省份邮编。

 |
|RegionId|String|是|cn-hangzhou|智能接入网关实例的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|Action|String|否|CreateSmartAccessGateway|执行的操作。

 取值：**CreateSmartAccessGateway**

 |
|Description|String|否|sag|智能接入网关实例描述。

 |
|Name|String|否|test|智能接入网关实例名称。

 |
|ReceiverPhone|String|否|13\*\*\*\*\*\*\*\*\*|收件人电话。

 |
|ReceiverTown|String|否|转塘|收货乡镇。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Description|String|sag|智能接入网关实例描述。

 |
|Name|String|sag-1|智能接入网关实例名称。

 |
|OrderId|String|203377778550296|订单ID。

 |
|RequestId|String|A6B9EB0F-57DB-4843-A372-04678ABF490E|请求ID。

 |
|SmartAGId|String|sag-nylv14tghsk26c\*\*\*\*\*|智能接入网关实例ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?AutoPay=true
&BuyerMessage=留言
&ChargeType=PREPAY
&HardWareSpec=sag-100wm
&HaType= no_backup
&MaxBandWidth=12
&Period=12
&ReceiverAddress=XX号
&ReceiverCity=杭州
&ReceiverCountry=中国
&ReceiverDistrict=西湖
&ReceiverEmail=xx@example.com
&ReceiverMobile=13*********
&ReceiverName=张三
&ReceiverState=浙江
&ReceiverZip=310000
&RegionId=cn-hangzhou
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<CreateSmartAccessGateway>
  <SmartAGId>sag-nylv14tghsk26cp41n</SmartAGId>
  <RequestId>A6B9EB0F-57DB-4843-A372-04678ABF490E</RequestId>
  <OrderId>203377778550296</OrderId>
</CreateSmartAccessGateway>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"SmartAGId":"sag-nylv14tghsk26cp41n",
	"OrderId":203377778550296,
	"RequestId":"A6B9EB0F-57DB-4843-A372-04678ABF490E"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Smartag)

