# DeleteACLRule

You can call this operation to delete an access control list \(ACL\) rule.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=DeleteACLRule&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|DeleteACLRule|The operation that you want to perform.

 Set the value to **DeleteACLRule**. |
|AclId|String|Yes|acl-xhwhyuo43l0n\*\*\*\*\*|The ID of the ACL to which the ACL rule to be deleted belongs. |
|AcrId|String|Yes|acr-c1hkd054qywiw\*\*\*\*\*\*|The ID of the ACL rule to be deleted. |
|RegionId|String|Yes|cn-hangzhou|The ID of the region to which the ACL rule to be deleted belongs. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|39E71162-699A-4E02-AF0F-17621BA6AEF6|The ID of the request. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=DeleteACLRule
&AclId=acl-xhwhyuo43l0n*****
&AcrId=acr-c1hkd054qywiw******
&RegionId=cn-hangzhou
&<Common request parameter>
```

Sample success responses

`XML` format

```
<DeleteACLRule>
      <RequestId>39E71162-699A-4E02-AF0F-17621BA6AEF6</RequestId>
</DeleteACLRule>
```

`JSON` format

```
{
    "RequestId": "39E71162-699A-4E02-AF0F-17621BA6AEF6"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|403|Forbidden|User not authorized to operate on the specified resource.|The error code returned because you do not have the permission to manage the resource.|
|403|MissingParameter|The input parameter is missing, please check your input.|The error code returned because a request parameter is not set. Check the request parameters.|
|403|InvalidId.ACL|The specified ACL ID is invalid.|The error code returned because the specified ACL ID is invalid.|
|403|InvalidId.ACR|The specified ACL rule ID is invalid.|The error code returned because the specified ACL rule ID is invalid.|
|403|FeatureNotSupport|The current edition of the smart access gateway does not support this feature.|The error code returned because the current version of the Smart Access Gateway \(SAG\) device does not support this feature.|
|403|FeatureNotSupportForActiveSmartAG|The current edition of the active smart access gateway does not support this feature.|The error code returned because the current version of the active SAG device does not support this feature.|
|403|FeatureNotSupportForStandBySmartAG|The current edition of the standby smart access gateway does not support this feature.|The error code returned because the current version of the standby SAG device does not support this feature.|
|403|InternalError|An internal server error occurred.|The error code returned because an internal server error occurred.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

