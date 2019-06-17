# AssociateACL {#doc_api_1162897 .reference}

Associates an Access Control List \(ACL\) with a Smart Access Gateway instance.

## Debug {#apiExplorer .section}

By using [OpenAPI Explorer](https://api.aliyun.com/#product=Smartag&api=CreateACL), you can easily debug APIs, automatically generate SDK code examples, and quickly search for APIs.

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|Action|String|No|AssociateACL| The name of this action.

 Value: **AssociateACL**

 |
|AclId|String|Yes|acl-ohlexqptfhy\*\*\*\*\*\*| The ID of the ACL.

 |
|RegionId|String|Yes|cn-hangzhou| The ID of the region to which the ACL belongs.

 |
|SmartAGId|String|Yes|sag-4yr0p2xa6o3k\*\*\*\*\*\*\*| The Smart Access Gateway instance to be associated with the ACL.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|RequestId|String|C9A75915-0260-4335-851A-D866A7ED396C| The ID of the request.

 |

## Examples {#demo .section}

**Request example**

``` {#request_demo}

http(s)://[Endpoint]/?AclId=acl-ohlexqptfhy******
&RegionId=cn-hangzhou
&SmartAGId=sag-4yr0p2xa6o3k*******
&<CommonParameters>

```

**Response example**

`XML` format

``` {#xml_return_success_demo}
<AssociateACL>
  <RequestId>00546174-2CE6-4587-9550-04B6A3313938</RequestId>
</AssociateACL>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"C9A75915-0260-4335-851A-D866A7ED396C"
}
```

## Error codes { .section}

|HTTP status code|Error code|Error message|Description|
|----------------|----------|-------------|-----------|
|403|Forbidden|User not authorized to operate on the specified resource.|You are not authorized to operate on this resource.|
|403|MissingParameter|The input parameter is missing, please check your input.|The input parameter is missing. Please check your input.|
|403|InvalidId.SMARTAG|The specified smart access gateway instance id is invalid.|The Smart Access Gateway ID is invalid.|
|403|FeatureNotSupport|The current edition of the smart access gateway does not support this feature.|The current version of the Smart Access Gateway device does not support this feature.|
|403|FeatureNotSupportForActiveSmartAG|The current edition of the active smart access gateway does not support this feature.|The current version of the active Smart Access Gateway device does not support this feature.|
|403|FeatureNotSupportForStandBySmartAG|The current edition of the standby smart access gateway does not support this feature.|The current version of the standby Smart Access Gateway device does not support this feature.|
|403|SmartAGAlreadyAssociateAcl|The specified smart access gateway has already been associated with the specified ACL.|The specified Smart Access Gateway is already associated with the specified ACL.|
|403|AclPerSmartagAmountLimit|No more ACL can be associated with this smart access gateway.|The quota for ACLs that can be associated with the Smart Access Gateway has been reached.|
|403|InternalError|An internal server error occurred.|An internal server error has occured.|
|403|InvalidId.ACL|The specified ACL ID is invalid.|The specified ACL ID is invalid.|

[See common error codes](https://error-center.aliyun.com/status/product/Smartag)

