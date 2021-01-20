# ListSmartAGApiUnsupportedFeature

Queries features that are not supported by a specified Smart Access Gateway \(SAG\) device.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=ListSmartAGApiUnsupportedFeature&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|ListSmartAGApiUnsupportedFeature|The operation that you want to perform.

 Set the value to **ListSmartAGApiUnsupportedFeature**. |
|OpenApiName|String|Yes|ModifySagWan|The name of the API operation that is performed to use the feature. |
|RegionId|String|Yes|cn-shanghai|The ID of the region where the SAG instance is deployed. |
|SerialNumber|String|Yes|sage62x052614\*\*\*\*|The serial number \(SN\) of the SAG device. |
|SmartAGId|String|Yes|sag-4d6i45zess8nj4\*\*\*\*|The ID of the SAG instance with which the SAG device is associated. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Features|Array of Feature| |A list of features that are not supported by the specified SAG device. |
|Feature|String|ISP|The feature.

 For more information about the description of each feature, see the related API reference. |
|RequestId|String|7459545D-2F0D-43E6-9957-CB7E0223332B|The ID of the request. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=ListSmartAGApiUnsupportedFeature
&OpenApiName=ModifySagWan
&RegionId=cn-shanghai
&SerialNumber=sage62x052614****
&SmartAGId=sag-4d6i45zess8nj4****
&<Common request parameters>
```

Sample success responses

`XML` format

```
<ListSmartAGApiUnsupportedFeatureResponse>
  <RequestId>7459545D-2F0D-43E6-9957-CB7E0223332B</RequestId>
  <Features>
        <Feature>Weight</Feature>
  </Features>
  <Features>
        <Feature>ISP</Feature>
  </Features>
  <Features>
        <Feature>BandWidth</Feature>
  </Features>
</ListSmartAGApiUnsupportedFeatureResponse>
```

`JSON` format

```
{
	"RequestId": "7459545D-2F0D-43E6-9957-CB7E0223332B",
	"Features": [
		{
			"Feature": "Weight"
		},
		{
			"Feature": "ISP"
		},
		{
			"Feature": "BandWidth"
		}
	]
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|InvalidSmartAGId.NotFound|The specified SmartAGId does not exist.|The error message returned because the specified SAG instance ID does not exist.|
|400|Sag.DeviceNotExist|The specified device does not exist.|The error message returned because the specified SAG device does not exist.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

