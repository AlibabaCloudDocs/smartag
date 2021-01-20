# GetAclAttribute

Queries configuration errors of the deep packet inspection \(DPI\) feature for a specified access control list \(ACL\).

## Prerequisites

-   An application-aware ACL is created. For more information, see [AddACLRule](~~114012~~).
-   The application-aware ACL is applied to a Smart Access Gateway \(SAG\) instance. For more information, see [AssociateACL](~~114009~~).

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=GetAclAttribute&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|GetAclAttribute|The operation that you want to perform.

 Set the value to **GetAclAttribute**. |
|AclId|String|Yes|acl-xhwhyuo43l0n\*\*\*\*\*|The ID of the ACL. |
|RegionId|String|Yes|cn-shanghai|The ID of the region where the ACL is deployed. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|AclId|String|acl-xhwhyuo43l0n\*\*\*\*\*|The ID of the ACL. |
|AclName|String|dpi\_test|The name of the ACL. |
|ErrorConfigSmartAGCount|Integer|0|The number of SAG devices that are associated with the ACL who has DPI configuration errors.

 You can call the [ListDpiConfigError](~~197566~~) operation to query exception details and SAG device information. |
|RequestId|String|5D2013F0-85AB-4332-9094-8023A598C2C1|The ID of the request. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=GetAclAttribute
&AclId=acl-xhwhyuo43l0n*****
&RegionId=cn-shanghai
&<Common request parameters>
```

Sample success responses

`XML` format

```
<GetAclAttributeResponse>
  <RequestId>5D2013F0-85AB-4332-9094-8023A598C2C1</RequestId>
  <AclId>acl-j8s80200h3cli****</AclId>
  <ErrorConfigSmartAGCount>0</ErrorConfigSmartAGCount>
  <AclName>dpi_test</AclName>
</GetAclAttributeResponse>
```

`JSON` format

```
{
	"RequestId": "5D2013F0-85AB-4332-9094-8023A598C2C1",
	"AclId": "acl-j8s80200h3cli****",
	"ErrorConfigSmartAGCount": 0,
	"AclName": "dpi_test"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

