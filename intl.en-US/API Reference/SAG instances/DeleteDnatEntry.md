# DeleteDnatEntry

You can call this operation to delete a destination network address translation \(DNAT\) entry associated with a Smart Access Gateway \(SAG\) instance.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=DeleteDnatEntry&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|DeleteDnatEntry|The operation that you want to perform.

 Set the value to **DeleteDnatEntry**. |
|RegionId|String|Yes|cn-hangzhou|The ID of the region where the SAG instance is deployed. |
|SagId|String|Yes|sag-jfh\*\*\*\*\*\*\*\*\*\*\*|The ID of the SAG instance.

 **Note:** Only SAG instances used to manage SAG devices supported DNAT. |
|DnatEntryId|String|No|fwd-kxe4fq3xuzczze\*\*\*\*|The ID of the DNAT entry. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|68CE10C0-2EFF-4B82-9907-10AB7E2B0A6C|The ID of the request. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=DeleteDnatEntry
&RegionId=cn-hangzhou
&SagId=sag-jfh***********
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DeleteDnatEntryResponse>
	  <RequestId>68CE10C0-2EFF-4B82-9907-10AB7E2B0A6C</RequestId>
</DeleteDnatEntryResponse>
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
|403|Forbidden|User not authorized to operate on the specified resource.|The error message returned because you do not have the permission to manage the specified resource.|
|403|MissingParameter|The input parameter is missing, please check your input.|The error message returned because a required parameter is not set. Check whether you have set all require parameters.|
|403|InvalidParameter|The specified parameter is invalid.|The error message returned because a specified parameter is invalid.|
|403|InternalError|An internal server error occurred.|The error message returned because an internal error occurred.|
|400|InstanceNotExit|The specified instance does not exist.|The error message returned because the specified instance does not exist.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

