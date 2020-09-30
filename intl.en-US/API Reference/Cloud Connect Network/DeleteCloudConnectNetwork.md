# DeleteCloudConnectNetwork

You can call this operation to delete a Cloud Connect Network \(CCN\) instance.

**Note:** Make sure that the CCN instance to be deleted is not associated with a Smart Access Gateway \(SAG\) or Cloud Enterprise Network \(CEN\) instance.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=DeleteCloudConnectNetwork&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|DeleteCloudConnectNetwork|The operation that you want to perform.

 Set the value to **DeleteCloudConnectNetwork**. |
|CcnId|String|Yes|ccn-bxuau4ezctts2\*\*\*\*\*|The ID of the CCN instance. |
|RegionId|String|No|cn-hangzhou|The ID of the region where the CCN instance is deployed. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|0BAAF2B9-88B8-4574-BDBE-102A90EE3FEE|The ID of the request. |

## Examples

Sample requests

```
http(s)://smartag.cn-shanghai.aliyuncs.com/? Action=DeleteCloudConnectNetwork
&CcnId=ccn-bxuau4ezctts2*****
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DeleteCloudConnectNetworkResponse>
    <RequestId>0BAAF2B9-88B8-4574-BDBE-102A90EE3FEE</RequestId>
</DeleteCloudConnectNetworkResponse>
```

`JSON` format

```
{
   "RequestId":"0BAAF2B9-88B8-4574-BDBE-102A90EE3FEE"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|403|MissingParameter|The input parameter is missing, please check your input.|The error message returned because a request parameter is not set. Check the request parameters.|
|403|InvalidId.CCN|Invalid cloud connect network id.|The error message returned because the specified CCN instance ID is invalid.|
|403|AlreadyBound.CEN|This instance has been bound, please unbind first.|The error message returned because the specified CCN instance is bound with a CEN instance. Unbind the CEN instance from the CCN instance.|
|403|AlreadyBound.SMARTAG|This instance has been bound, please unbind smart access gateway first.|The error message returned because the specified CCN instance is bound with an SAG instance. Unbind the SAG instance from the CCN instance.|
|403|Forbidden|User not authorized to operate on the specified resource.|The error message returned because you do not have the permission to manage the resource.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

