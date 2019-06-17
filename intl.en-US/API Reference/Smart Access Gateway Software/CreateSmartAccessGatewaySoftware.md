# CreateSmartAccessGatewaySoftware {#doc_api_Smartag_CreateSmartAccessGatewaySoftware .reference}

Creates a Smart Access Gateway \(SAG\) Software.

## Debug {#apiExplorer .section}

Use [API Explorer](https://api.aliyun.com/#product=Smartag&api=CreateSmartAccessGatewaySoftware) to perform debug operations and generate SDK code examples.

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|AutoPay|Boolean|Yes|true| Indicates whether to automatically pay the bill of a Subscription instance.

 Valid values: **true | false**

 Default value: **false**.

 |
|ChargeType|String|Yes|PREPAY| The billing method of the instance. Valid values:

 -   PayOnDemand: Pay-As-You-Go
-   Prepay: Subscription

 **Note:** Currently, only the Subscription billing method is supported.

 |
|DataPlan|Long|Yes|5| The specification of the free data plan provided for each account each month. Unit: G.

 **Note:** Currently, only free 5G data plans are provided.

 |
|Period|Integer|Yes|12| The validity period of the data plan under each account. Unit: month. If the value exceeds 12, it must be a multiple of 12.

 |
|RegionId|String|Yes|cn-shanghai| The region to which the Smart Access Gateway Software belongs.

 |
|UserCount|Integer|Yes|5| The number of client accounts the administrator can create. Generally, one account is created for each employee that needs to log on to the client.

 |
|Action|String|No|CreateSmartAccessGatewaySoftware| The name of this action.

 Valid value: **CreateSmartAccessGatewaySoftware**

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|OrderId|String|203782300920296| The order number of the purchase.

 |
|RequestId|String|24675405-74DF-4C94-82C6-B749580C498E| The ID of the request.

 |
|SmartAGId|String|sag-gnhe6sywtare5\*\*\*\*\*\*| The ID of the Smart Access Gateway Software.

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/? Action=CreateSmartAccessGatewaySoftware
&AutoPay=true 
&ChargeType=PREPAY
&DataPlan=5
&Period=1 
&RegionId=cn-hangzhou 
&UserCount=5
&<CommonParameters>

```

Response example

`XML` format

``` {#xml_return_success_demo}
<CreateSmartAccessGatewaySoftware>
  <SmartAGId>sag-gnhe6sywtare5nt***</SmartAGId>
  <OrderId>202778336800296</OrderId>
  <RequestId>B35789C0-A570-4C2F-96D6-2B46FBB9D64A</RequestId>
</CreateSmartAccessGatewaySoftware>

```

`JSON` format

``` {#json_return_success_demo}
{
	"SmartAGId":"sag-gnhe6sywtare5nt***",
	"RequestId":"B35789C0-A570-4C2F-96D6-2B46FBB9D64A",
	"OrderId":203782300920296
}
```

## Error codes {#section_vmg_hxs_139 .section}

[See common error codes](https://error-center.aliyun.com/status/product/Smartag)

