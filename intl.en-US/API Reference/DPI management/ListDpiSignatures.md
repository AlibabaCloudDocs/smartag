# ListDpiSignatures

Queries application information in a specified region, information about a specified application group, or information about applications supported by a specified Smart Access Gateway \(SAG\) instance in a specified region.

## Background information

This operation supports the following features:

-   Queries the information about all applications supported by the SAG instance in a specified region.
-   Queries the information about an application by application ID in a specified region.
-   Queries the information about an application by application name in a specified region.
-   Queries the information about an application group by group ID in a specified region.

If this is the first time you call this operation, we recommend that you query all applications supported by the SAG instance in the specified region by region ID. Then, you can query the information about a specified application.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=ListDpiSignatures&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|ListDpiSignatures|The operation that you want to perform.

 Set the value to **ListDpiSignatures**. |
|RegionId|String|Yes|cn-shanghai|The ID of the region to which the application or application group belongs.

 You can call the [DescribeRegions](~~69813~~) operation to query the most recent region list. |
|NextToken|String|No|caeba0bbb2\*\*\*\*|The token used to query the next page. |
|MaxResults|Integer|No|20|The number of entries to return on each page.

 Valid values: **1** to **100**.

 Default value: **20**. |
|DpiSignatureIds.N|RepeatList|No|235|The ID of the application. |
|DpiSignatureNames.N|RepeatList|No|EdgeCast|The name of the application. |
|DpiGroupId|String|No|20|The ID of the application group. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|DpiSignature|Array of DpiSignature| |The information about the application. |
|DpiGroupId|String|20|The ID of the application group to which the application belongs. |
|DpiSignatureId|String|235|The ID of the application. |
|DpiSignatureName|String|EdgeCast|The name of the application. |
|MinEngineVersion|String|0-0.0.1|The earliest version of engine that supports the application. |
|MinSignatureDbVersion|String|20201117\_1\_0-0.0.1|The earliest version of signature database that supports the application. |
|NextToken|String|FFrMV38kR4\*\*\*\*|The token returned for the next query. |
|RequestId|String|63081123-B7C0-4BC9-B9E5-59E77A616EC9|The ID of the request. |
|TotalCount|Integer|1|The total number of entries returned on the current page. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=ListDpiSignatures
&RegionId=cn-shanghai
&<Common request parameters>
```

Sample success responses

`XML` format

```
<ListDpiSignaturesResponse>
  <TotalCount>1</TotalCount>
  <RequestId>63081123-B7C0-4BC9-B9E5-59E77A616EC9</RequestId>
  <NextToken>FFrMV38kR4****</NextToken>
  <DpiSignature>
        <MinEngineVersion>0-0.0.1</MinEngineVersion>
        <MinSignatureDbVersion>20201117_1_0-0.0.1</MinSignatureDbVersion>
        <DpiSignatureId>1</DpiSignatureId>
        <DpiSignatureName>Baidu</DpiSignatureName>
        <DpiGroupId>20</DpiGroupId>
  </DpiSignature>
</ListDpiSignaturesResponse>
```

`JSON` format

```
{
	"TotalCount": 1,
	"RequestId": "63081123-B7C0-4BC9-B9E5-59E77A616EC9",
	"NextToken": "FFrMV38kR4****",
	"DpiSignature": [
		{
			"MinEngineVersion": "0-0.0.1",
			"MinSignatureDbVersion": "20201117_1_0-0.0.1",
			"DpiSignatureId": "1",
			"DpiSignatureName": "Baidu",
			"DpiGroupId": "20"
		}
	]
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

