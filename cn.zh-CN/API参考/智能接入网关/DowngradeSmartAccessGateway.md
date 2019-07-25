# DowngradeSmartAccessGateway {#doc_api_Smartag_DowngradeSmartAccessGateway .reference}

使用DowngradeSmartAccessGateway接口降低智能接入网关实例的带宽。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=DowngradeSmartAccessGateway&type=RPC&version=2018-03-13)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|AutoPay|Boolean|是|true|是否是自动支付预付费实例的账单，默认值是**false**。

 |
|BandWidthSpec|Long|是|20|智能接入网关的带宽。

 -   如果网关设备规格为sag-100wm，带宽取值：2~50Mbps
-   如果网关设备规格为sag-1000，带宽取值：10~500Mbps

 |
|RegionId|String|是|cn-hangzhou|智能接入网关的地域ID。

 |
|SmartAGId|String|是|sag-nylv14tghsk26c\*\*\*\*\*|智能接入网关实例ID。

 |
|Action|String|否|DowngradeSmartAccessGateway|执行的操作，取值：**DowngradeSmartAccessGateway**。

 |
|DataPlan|Long|否|5|每个账号赠送的流量套餐规格，单位G。

 **说明：** 目前仅支持购买5GB/月套餐。

 |
|UserCount|Integer|否|5|APP账号数规格，购买后可创建相应数量的账号，一般为每个需要登陆的员工创建一个账号。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|OrderId|String|203377778550296|订单ID。

 |
|RequestId|String|A6B9EB0F-57DB-4843-A372-04678ABF490E|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DowngradeSmartAccessGateway
&AutoPay=true
&BandWidthSpec=20
&RegionId=cn-hangzhou
&SmartAGId=sag-nylv14tghsk26c*****
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DowngradeSmartAccessGatewayResponse>
    <RequestId>A6B9EB0F-57DB-4843-A372-04678ABF490E</RequestId>
    <OrderId>203377778550296</OrderId>
</DowngradeSmartAccessGatewayResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"A6B9EB0F-57DB-4843-A372-04678ABF490E",
	"OrderId":203377778550296
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|SAG.InvalidUserCount|The specified UserCount is invalid.|非法的用户数。|
|400|SAG.InvalidDataPlan|The specified DataPlan is invalid.|非法的流量包套餐。|

访问[错误中心](https://error-center.aliyun.com/status/product/Smartag)查看更多错误码。

