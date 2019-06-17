# DeleteACLRule {#doc_api_Smartag_DeleteACLRule .reference}

Deletes an Access Control List \(ACL\) rule.

## Debug {#apiExplorer .section}

By using [OpenAPI Explorer](https://api.aliyun.com/#product=Smartag&api=CreateACL), you can easily debug APIs, automatically generate SDK code examples, and quickly search for APIs.

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|Action|String|No|DeleteACLRule| The name of this action.

 Valid value: **DeleteACLRule**

 |
|AclId|String|Yes|acl-xhwhyuo43l0n\*\*\*\*\*| The ACL to which the ACL rule belongs.

 |
|AcrId|String|Yes|acr-c1hkd054qywiw\*\*\*\*\*\*| The ACL rule to be deleted.

 |
|RegionId|String|Yes|cn-hangzhou| The ID of the region to which the ACL rule belongs.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|RequestId|String|39E71162-699A-4E02-AF0F-17621BA6AEF6| The ID of the request.

 |

## Examples {#demo .section}

**Request example**

``` {#request_demo}

http(s)://[Endpoint]/?AclId=acl-xhwhyuo43l0n*****
&AcrId=acr-c1hkd054qywiw******
&RegionId=cn-hangzhou
&<CommonParameters>

```

**Response example**

`XML` format

``` {#xml_return_success_demo}
<DeleteACLRule>
  <RequestId>39E71162-699A-4E02-AF0F-17621BA6AEF6</RequestId>
</DeleteACLRule>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"39E71162-699A-4E02-AF0F-17621BA6AEF6"
}
```

## Error codes { .section}

|HTTP status code|Error code|Error message|Description|
|----------------|----------|-------------|-----------|
|403|Forbidden|User not authorized to operate on the specified resource.|You are not authorized to operate on this resource.|
|403|MissingParameter|The input parameter is missing, please check your input.|The input parameter is missing. Please check your input.|
|403|InvalidId.ACL|The specified ACL ID is invalid.|The specified ACL ID is invalid.|
|403|InvalidId.ACR|The specified ACL rule ID is invalid.|The specified ACL rule ID is invalid.|
|403|FeatureNotSupport|The current edition of the smart access gateway does not support this feature.|The current version of the Smart Access Gateway device does not support this feature.|
|403|FeatureNotSupportForActiveSmartAG|The current edition of the active smart access gateway does not support this feature.|The current version of the active Smart Access Gateway device does not support this feature.|
|403|FeatureNotSupportForStandBySmartAG|The current edition of the standby smart access gateway does not support this feature.|The current version of the standby Smart Access Gateway device does not support this feature.|
|403|InternalError|An internal server error occurred.|An internal server error has occured.|

[See common error codes](https://error-center.aliyun.com/status/product/Smartag)

