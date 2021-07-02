# CreateSmartAccessGatewaySoftware

调用CreateSmartAccessGatewaySoftware创建智能接入网关APP实例。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=CreateSmartAccessGatewaySoftware&type=RPC&version=2018-03-13)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|CreateSmartAccessGatewaySoftware|系统规定参数。取值：**CreateSmartAccessGatewaySoftware**。 |
|RegionId|String|是|cn-shanghai|智能接入网关APP实例的地域ID。 |
|Period|Integer|是|12|智能接入网关APP实例的购买时长，单位：月。

 取值：**1**~**9**、**12**、**24**、**36**。 |
|AutoPay|Boolean|是|false|是否自动支付智能接入网关APP实例的账单。取值：

 -   **true**：是。
-   **false**（默认值）：否。

 如果您选择不自动支付账单，在您调用本接口后，请前往控制台的订单中心完成支付，实例才能创建成功。 |
|ChargeType|String|是|PREPAY|智能接入网关APP实例的计费类型，取值：**PREPAY**，预付费。标识智能接入网关APP实例为先付费后使用的资源。 |
|UserCount|Integer|是|5|智能接入网关APP实例的客户端账号数量规格。

 **说明：** 客户端账号数量规格只能是5的倍数，如5、10、15。 |
|DataPlan|Long|是|5|系统每月赠送给每个客户端账号的流量套餐规格，单位：GB。取值：**5**。

 **说明：** 目前仅支持每月赠送给每个客户端账号5 GB的流量套餐。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|24675405-74DF-4C94-82C6-B749580C498E|请求ID。 |
|OrderId|String|203000000000000|购买智能接入网关APP实例的订单号。 |
|SmartAGId|String|sag-gnhe6sywtare5\*\*\*\*\*\*|智能接入网关APP实例ID。 |
|ResourceGroupId|String|rg-acfm2iu4fnc\*\*\*\*|智能接入网关APP实例所属资源组ID。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=CreateSmartAccessGatewaySoftware
&RegionId=cn-shanghai
&Period=12
&AutoPay=true
&ChargeType=PREPAY
&UserCount=5
&DataPlan=5
&公共请求参数
```

正常返回示例

`XML`格式

```
HTTP/1.1 200 OK
Content-Type:application/xml

<CreateSmartAccessGatewaySoftwareResponse>
    <RequestId>24675405-74DF-4C94-82C6-B749580C498E</RequestId>
    <OrderId>203000000000000</OrderId>
    <SmartAGId>sag-gnhe6sywtare5******</SmartAGId>
    <ResourceGroupId>rg-acfm2iu4fnc****</ResourceGroupId>
</CreateSmartAccessGatewaySoftwareResponse>
```

`JSON`格式

```
HTTP/1.1 200 OK
Content-Type:application/json

{
  "RequestId" : "24675405-74DF-4C94-82C6-B749580C498E",
  "OrderId" : "203000000000000",
  "SmartAGId" : "sag-gnhe6sywtare5******",
  "ResourceGroupId" : "rg-acfm2iu4fnc****"
}
```

## 错误码

访问[错误中心](https://error-center.aliyun.com/status/product/Smartag)查看更多错误码。

