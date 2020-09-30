# ModifySmartAccessGatewayUpBandwidth

You can call this operation to modify the parameters of a Smart Access Gateway \(SAG\) instance.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=ModifySmartAccessGatewayUpBandwidth&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|SmartAGId|String|Yes|sag-jsy\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*|The ID of the SAG instance. |
|Action|String|No|ModifySmartAccessGatewayUpBandwidth|The operation that you want to perform.

 Set the value to **ModifySmartAccessGatewayUpBandwidth**. |
|RegionId|String|No|cn-hangzhou|The ID of the region where the SAG instance is deployed. |
|UpBandwidth4G|Integer|No|3|The maximum upstream bandwidth of 4G network connections established by the SAG device. |
|UpBandwidthWan|Integer|No|2|The maximum upstream bandwidth of network connections established on the WAN port of the SAG device. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|EE837E9F-BD50-4C2B-9E47-260F9D848480|The ID of the request. |

## Examples

Sample requests

```

http(s)://[Endpoint]/? Action=ModifySmartAccessGatewayUpBandwidth
&SmartAGId=sag-jsy******************
&<Common request parameters>

```

Sample success responses

`XML` format

```
<ModifySmartAccessGatewayUpBandwidthResponse>
	  <RequestId>68CE10C0-2EFF-4B82-9907-10AB7E2B0A6C</RequestId>
    </ModifySmartAccessGatewayUpBandwidthResponse>
```

`JSON` format

```
{
	"RequestId":"68CE10C0-2EFF-4B82-9907-10AB7E2B0A6C"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|403|MissingParameter|The input parameter is missing, please check your input.|The error message returned because a required parameter is not set. Check whether you have set all require parameters.|
|400|InvalidName|The specified name is invalid.|The error message returned because the specified name is invalid.|
|400|SAG.NotAllowConfigCidr|You cannot specify a static CIDR block when the dynamic routing strategy is used.|The error message returned because dynamic routing mode does not support static CIDR blocks.|
|400|InvalidDescription|The specified description is invalid.|The error message returned because the specified description is invalid.|
|403|InvalidCidr|Cidr is illegal, please check your input.|The error message returned because the specified CIDR block is invalid. Check the specified CIDR block.|
|400|SAG.InvalidRoutingStrategy|The specified routing strategy is invalid.|The error message returned because the specified routing mode is invalid.|
|403|InvalidId.SMARTAG|The specified smart access gateway instance id is invalid.|The error message returned because the specified SAG instance ID is invalid.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

