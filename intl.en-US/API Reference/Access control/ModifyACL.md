# ModifyACL

You can call this operation to modify the name of an access control list \(ACL\).

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=ModifyACL&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|ModifyACL|The operation that you want to perform.

 Set the value to **ModifyACL**. |
|AclId|String|Yes|acl-e30a66to95cs\*\*\*\*\*\*|The ID of the ACL. |
|Name|String|Yes|test|The name of the ACL.

 The name must be 2 to 100 characters in length, and can contain digits, underscores \(\_\), periods \(.\), and hyphens \(-\). It must start with a letter or Chinese character. |
|RegionId|String|Yes|cn-hangzhou|The ID of the region to which the ACL belongs. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|076FD0BE-67D5-4338-A2A1-C54DE7D78B16|The ID of the request. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=ModifyACL
&AclId=acl-e30a66to95cs******
&Name=test
&RegionId=cn-hangzhou
&<Common request parameters>
```

Sample success responses

`XML` format

```
<ModifyACLResponse>
	  <RequestId>076FD0BE-67D5-4338-A2A1-C54DE7D78B16</RequestId>
</ModifyACLResponse>
```

`JSON` format

```
{
    "RequestId": "076FD0BE-67D5-4338-A2A1-C54DE7D78B16"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|403|Forbidden|User not authorized to operate on the specified resource.|The error message returned because you do not have the permission to manage the resource.|
|403|MissingParameter|The input parameter is missing, please check your input.|The error message returned because a request parameter is not set. Check the request parameters.|
|403|InvalidName|Name not valid.|The error message returned because the specified ACL name is invalid.|
|403|InvalidId.ACL|The specified ACL ID is invalid.|The error message returned because the specified ACL ID is invalid.|
|403|InternalError|An internal server error occurred.|The error message returned because an internal server error has occurred.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

