# DescribeACLs

You can call this operation to query the information about access control lists \(ACLs\).

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=DescribeACLs&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|DescribeACLs|The operation that you want to perform.

 Set the value to **DescribeACLs**. |
|RegionId|String|Yes|cn-hangzhou|The ID of the region. |
|AclIds|String|No|acl-xhwhyuo43l\*\*\*\*\*\*\*|The ID of the ACL.

 Separate multiple IDs with commas \(,\). If this parameter is not set, all the ACLs in the specified region are queried by default. |
|Name|String|No|test|The name of the ACL.

 The name must be 2 to 100 characters in length, and can contain digits, underscores \(\_\), and hyphens \(-\). It must start with a letter or Chinese character. |
|PageSize|Integer|No|1|The number of entries to return on each page. Maximum value: **50**. Default value: **10**. |
|PageNumber|Integer|No|1|The number of the page to return. Pages start from page 1. Default value: **1**. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|3200E8A3-563F-4FFC-8BDB-0F1263FA69E8|The ID of the request. |
|TotalCount|Integer|3|The total number of entries returned. |
|PageNumber|Integer|1|The page number of the returned page. Default value: **1**. |
|PageSize|Integer|2|The number of entries returned on each page. |
|Acls|Array| |The ACL information. |
|AclId|String|acl-ohlexqptfhy\*\*\*\*\*\*\*|The ID of the ACL. |
|Name|String|test|The name of the ACL. |
|SagCount|String|3|The number of associated Smart Access Gateway \(SAG\) devices. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=DescribeACLs
&RegionId=cn-hangzhou
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeACLs>
      <PageNumber>1</PageNumber>
	  <TotalCount>3</TotalCount>
	  <PageSize>10</PageSize>
	  <RequestId>3200E8A3-563F-4FFC-8BDB-0F1263FA69E8</RequestId>
	  <Acls>
		    <Acl>
			      <Name>vmeixme</Name>
			      <SagCount>0</SagCount>
			      <AclId>acl-e30a66to95csjy****</AclId>
		    </Acl>
		    <Acl>
			      <Name>test</Name>
			      <SagCount>0</SagCount>
			      <AclId>acl-ohlexqptfhygf4****</AclId>
		    </Acl>
		    <Acl>
			      <Name>test</Name>
			      <SagCount>3</SagCount>
			      <AclId>acl-xhwhyuo43l0n2b****</AclId>
		    </Acl>
	  </Acls>
</DescribeACLs>
```

`JSON` format

```
{
    "PageNumber": 1, 
    "TotalCount": 3, 
    "PageSize": 10, 
    "RequestId": "3200E8A3-563F-4FFC-8BDB-0F1263FA69E8", 
    "Acls": {
        "Acl": [
            {
                "Name": "vmeixme", 
                "SagCount": 0, 
                "AclId": "acl-e30a66to95csjy****"
            }, 
            {
                "Name": "test", 
                "SagCount": 0, 
                "AclId": "acl-ohlexqptfhygf4****"
            }, 
            {
                "Name": "test", 
                "SagCount": 3, 
                "AclId": "acl-xhwhyuo43l0n2b****"
            }
        ]
    }
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|403|Forbidden|User not authorized to operate on the specified resource.|The error code returned because you do not have the permission to manage the resource.|
|403|MissingParameter|The input parameter is missing, please check your input.|The error code returned because a request parameter is not set. Check the request parameters.|
|403|InvalidParameter|The specified parameter is invalid.|The error code returned because a specified parameter is invalid.|
|403|InternalError|An internal server error occurred.|The error code returned because an internal server error occurred.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

