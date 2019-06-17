# DisassociateACL {#doc_api_1162918 .reference}

Disassociates a Smart Access Gateway instance from an access control list \(ACL\).

## Debug {#apiExplorer .section}

By using [OpenAPI Explorer](https://api.aliyun.com/#product=Smartag&api=DescribeACLs), you can easily debug APIs, automatically generate SDK code examples, and quickly search for APIs.

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|Action|String|No|DisassociateACL| The name of this action.

 Value: **DisassociateACL**

 |
|AclId|String|Yes|acl-xhwhyuo43l0\*\*\*\*\*\*\*| The ID of the ACL.

 |
|RegionId|String|Yes|cn-hangzhou| The ID of the region to which the ACL belongs.

 |
|SmartAGId|String|Yes|sag-ke3kq4evpi8\*\*\*\*\*\*\*\*| The ID of the Smart Access Gateway instance to be disassociated from the ACL.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|RequestId|String|B28A9AB3-05BD-4A88-AB6A-A555A0BF70C0| The ID of the request.

 |

## Examples {#demo .section}

 **Request example** 

``` {#request_demo}

http(s)://[Endpoint]/?AclId=acl-xhwhyuo43l0*******
&RegionId=cn-hangzhou
&SmartAGId=sag-ke3kq4evpi8********
&<CommonParameters>

```

 **Response example** 

`XML` format

``` {#xml_return_success_demo}
<DisassociateACL>
  <RequestId>00546174-2CE6-4587-9550-04B6A3313938</RequestId>
</DisassociateACL>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"B28A9AB3-05BD-4A88-AB6A-A555A0BF70C0"
}
```

## Error codes {#section_xn4_b3n_8gf .section}

|HTTP status code|Error code|Error message|Description|
|----------------|----------|-------------|-----------|
|403|Forbidden|User not authorized to operate on the specified resource.|You are not authorized to operate on this resource.|
|403|MissingParameter|The input parameter is missing, please check your input.|The input parameter is missing. Please check your input.|
|403|InvalidId.SMARTAG|The specified smart access gateway instance id is invalid.|The specified Smart Access Gateway ID is invalid.|
|403|FeatureNotSupport|The current edition of the smart access gateway does not support this feature.|The current version of the Smart Access Gateway device does not support this feature.|
|403|FeatureNotSupportForActiveSmartAG|The current edition of the active smart access gateway does not support this feature.|The current version of the active Smart Access Gateway device does not support this feature.|
|403|FeatureNotSupportForStandBySmartAG|The current edition of the standby smart access gateway does not support this feature.|The current version of the standby Smart Access Gateway device does not support this feature.|
|403|InvalidId.ACL|The specified ACL ID is invalid.|The specified ACL ID is invalid.|
|403|SmartAGNotAssociateAcl|The specified smart access gateway is not associated with the specified ACL.|The specified Smart Access Gateway is not associated with the specified ACL.|
|403|InternalError|An internal server error occurred.|An internal server error has occurred.|

[See common error codes](https://error-center.aliyun.com/status/product/Smartag)

