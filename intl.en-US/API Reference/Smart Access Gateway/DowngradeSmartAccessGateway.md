# DowngradeSmartAccessGateway

You can call this operation to downgrade the bandwidth of a Smart Access Gateway \(SAG\) instance.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=DowngradeSmartAccessGateway&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|DowngradeSmartAccessGateway|The operation that you want to perform.

 Set the value to **DowngradeSmartAccessGateway**. |
|AutoPay|Boolean|Yes|true|Specifies whether it is an auto-renewal order generated by a subscription instance. Valid values:

 -   **true**: Yes
-   **false**: No \(default\) |
|BandWidthSpec|Long| Yes|20|The bandwidth of the SAG instance.

 -   If the model of the SAG device is **SAG-100WM**, set the bandwidth to **2 to 50 Mbit/s**.
-   If the model of the SAG device is **SAG-1000**, set the bandwidth to **10 to 500 Mbit/s**. |
|RegionId|String|Yes|cn-hangzhou|The ID of the region where the SAG instance is deployed. |
|SmartAGId|String|Yes|sag-nylv14tghsk26c\*\*\*\*\*|The ID of the SAG instance. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|OrderId|String|20337777855\*\*\*\*|The ID of the order. |
|RequestId|String|A6B9EB0F-57DB-4843-A372-04678ABF490E|The ID of the request. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=DowngradeSmartAccessGateway
&AutoPay=true
&BandWidthSpec=20
&RegionId=cn-hangzhou
&SmartAGId=sag-nylv14tghsk26c*****
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DowngradeSmartAccessGatewayResponse>
    <RequestId>A6B9EB0F-57DB-4843-A372-04678ABF490E</RequestId>
    <OrderId>20337777855****</OrderId>
</DowngradeSmartAccessGatewayResponse>
```

`JSON` format

```
{
	"OrderId":"20337777855****",
	"RequestId":"A6B9EB0F-57DB-4843-A372-04678ABF490E"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|SAG.InvalidUserCount|The specified UserCount is invalid.|The error message returned because the specified number of client accounts is invalid.|
|400|SAG.InvalidDataPlan|The specified DataPlan is invalid.|The error message returned because the specified data transfer plan is invalid.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

