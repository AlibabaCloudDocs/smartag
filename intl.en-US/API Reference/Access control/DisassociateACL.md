# DisassociateACL

You can call this operation to disassociate a Smart Access Gateway \(SAG\) instance from an access control list \(ACL\).

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=DisassociateACL&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|AclId|String|Yes|acl-xhwhyuo43l0\*\*\*\*\*\*\*|The ID of the ACL. |
|RegionId|String|Yes|cn-hangzhou|The ID of the region to which the ACL belongs. |
|SmartAGId|String|Yes|sag-ke3kq4evpi8\*\*\*\*\*\*\*\*|The ID of the SAG instance to be unbound from the ACL. |
|Action|String|No|DisassociateACL|The operation that you want to perform.

 Set the value to **DisassociateACL**. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|B28A9AB3-05BD-4A88-AB6A-A555A0BF70C0|The ID of the request. |

## Examples

Sample requests

```

http(s)://[Endpoint]/? AclId=acl-xhwhyuo43l0*******
&RegionId=cn-hangzhou
&SmartAGId=sag-ke3kq4evpi8********
&<Common request parameters>

```

Sample success responses

`XML` format

```
<DisassociateACL>
	  <RequestId>00546174-2CE6-4587-9550-04B6A3313938</RequestId>
    </DisassociateACL>
```

`JSON` format

```
{
	"RequestId":"B28A9AB3-05BD-4A88-AB6A-A555A0BF70C0"
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
|403|InvalidId.ACL|The specified ACL ID is invalid.|The error message returned because the specified ACL ID is invalid.|
|403|SmartAGNotAssociateAcl|The specified smart access gateway is not associated with the specified ACL.|The error message returned because the specified SAG instance is not bound with the specified ACL.|
|403|InternalError|An internal server error occurred.|The error message returned because an internal server error has occurred.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

