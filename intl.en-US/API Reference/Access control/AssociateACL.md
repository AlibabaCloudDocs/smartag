# AssociateACL

You can call this operation to associate an access control list \(ACL\) with a Smart Access Gateway \(SAG\) instance.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=AssociateACL&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|AssociateACL|The operation that you want to perform.

 Set the value to **AssociateACL**. |
|AclId|String|Yes|acl-ohlexqptfhy\*\*\*\*\*\*|The ID of the ACL. |
|RegionId|String|Yes|cn-hangzhou|The ID of the region to which the ACL belongs. |
|SmartAGId|String|Yes|sag-4yr0p2xa6o3k\*\*\*\*\*\*\*|The ID of the SAG instance to be associated with the ACL. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|C9A75915-0260-4335-851A-D866A7ED396C|The ID of the request. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=AssociateACL
&AclId=acl-ohlexqptfhy******
&RegionId=cn-hangzhou
&SmartAGId=sag-4yr0p2xa6o3k*******
&<Common request parameters>
```

Sample success responses

`XML` format

```
<AssociateACL>
	  <RequestId>00546174-2CE6-4587-9550-04B6A3313938</RequestId>
</AssociateACL>
```

`JSON` format

```
{
	"RequestId": "C9A75915-0260-4335-851A-D866A7ED396C"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|403|Forbidden|User not authorized to operate on the specified resource.|The error message returned because you do not have the permission to manage the resource.|
|403|MissingParameter|The input parameter is missing, please check your input.|The error message returned because a request parameter is not set. Check the request parameters.|
|403|InvalidId.SMARTAG|The specified smart access gateway instance id is invalid.|The error message returned because the specified SAG instance ID is invalid.|
|403|FeatureNotSupport|The current edition of the smart access gateway does not support this feature.|The error message returned because the current version of the SAG device does not support this feature.|
|403|FeatureNotSupportForActiveSmartAG|The current edition of the active smart access gateway does not support this feature.|The error message returned because the current version of the active SAG device does not support this feature.|
|403|FeatureNotSupportForStandBySmartAG|The current edition of the standby smart access gateway does not support this feature.|The error message returned because the current version of the standby SAG device does not support this feature.|
|403|SmartAGAlreadyAssociateAcl|The specified smart access gateway has already been associated with the specified ACL.|The error message returned because the specified SAG instance is already associated with the specified ACL.|
|403|AclPerSmartagAmountLimit|No more ACL can be associated with this smart access gateway.|The error message returned because the number of ACLs associated with the specified SAG instance exceeds the upper limit.|
|403|InternalError|An internal server error occurred.|The error message returned because an internal server error has occurred.|
|403|InvalidId.ACL|The specified ACL ID is invalid.|The error message returned because the specified ACL ID is invalid.|
|400|SAG.SoftwareNotSupport|The specified SAG software edition instance does not support ACL.|The error message returned because the SAG APP instance does not support ACLs.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

