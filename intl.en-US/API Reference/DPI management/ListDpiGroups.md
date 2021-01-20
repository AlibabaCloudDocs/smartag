# ListDpiGroups

Queries the information about application groups supported by Smart Access Gateway \(SAG\) instances in a specified region.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=ListDpiGroups&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|ListDpiGroups|The operation that you want to perform.

 Set the value to **ListDpiGroups**. |
|RegionId|String|Yes|cn-shanghai|The ID of the region to which the application groups belong.

 You can call the [DescribeRegions](~~69813~~) to query the most recent region list. |
|NextToken|String|No|FFPSpX59Eb\*\*\*\*|The token used to query the next page. |
|MaxResults|Integer|No|3|The number of entries to return on each page.

 Valid values: **1** to **100**.

 Default value: **20**. |
|DpiGroupIds.N|RepeatList|No|1|The ID of the application group.

 You can query information about one or more application groups by group ID. You can specify at most 10 group IDs in each call. |
|DpiGroupNames.N|RepeatList|No|P2P|The name of the application group.

 You can query information about one or more application groups by group name. You can specify at most 10 group names in each call. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|DpiGroup|Array of DpiGroup| |The information about the application group. |
|DpiGroupId|String|1|The ID of the application group. |
|DpiGroupName|String|P2P|The name of the application group. |
|MinEngineVersion|String|0-0.0.1|The earliest version of engine that supports the application group. |
|MinSignatureDbVersion|String|20201117\_1\_0-0.0.1|The earliest version of signature database that supports the application group. |
|NextToken|String|FFPSpX59Ebw\*\*\*\*|The token returned for the next query. |
|RequestId|String|EC184A86-3C93-49D6-BB34-6C193E14D37F|The ID of the request. |
|TotalCount|Integer|22|The total number of entries returned. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=ListDpiGroups
&RegionId=cn-shanghai
&<Common request parameters>
```

Sample success responses

`XML` format

```
<ListDpiGroupsResponse>
  <TotalCount>22</TotalCount>
  <RequestId>9E753114-BAF3-4676-9572-377FED18446D</RequestId>
  <NextToken>FFPSpX59Ebw****</NextToken>
  <DpiGroup>
        <MinEngineVersion>0-0.0.1</MinEngineVersion>
        <DpiGroupName>P2P</DpiGroupName>
        <MinSignatureDbVersion>20201117_1_0-0.0.1</MinSignatureDbVersion>
        <DpiGroupId>1</DpiGroupId>
  </DpiGroup>
  <DpiGroup>
        <MinEngineVersion>0-0.0.1</MinEngineVersion>
        <DpiGroupName>VoIP</DpiGroupName>
        <MinSignatureDbVersion>20201117_1_0-0.0.1</MinSignatureDbVersion>
        <DpiGroupId>2</DpiGroupId>
  </DpiGroup>
</ListDpiGroupsResponse>
```

`JSON` format

```
{
	"TotalCount": 22,
	"RequestId": "9E753114-BAF3-4676-9572-377FED18446D",
	"NextToken": "FFPSpX59Ebw****",
	"DpiGroup": [
		{
			"MinEngineVersion": "0-0.0.1",
			"DpiGroupName": "P2P",
			"MinSignatureDbVersion": "20201117_1_0-0.0.1",
			"DpiGroupId": "1"
		},
		{
			"MinEngineVersion": "0-0.0.1",
			"DpiGroupName": "VoIP",
			"MinSignatureDbVersion": "20201117_1_0-0.0.1",
			"DpiGroupId": "2"
		}
	]
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

