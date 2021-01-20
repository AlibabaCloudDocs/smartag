# DescribeGrantSagRules

Queries the permission information about a specified Smart Access Gateway \(SAG\) instance.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=DescribeGrantSagRules&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|DescribeGrantSagRules|The operation that you want to perform.

 Set the value to **DescribeGrantSagRules**. |
|RegionId|String|Yes|cn-hangzhou|The ID of the region where the SAG instance is deployed. |
|SmartAGId|String|Yes|sag-hdg\*\*\*\*\*\*\*\*\*\*\*\*\*|The ID of the SAG instance. |
|PageNumber|Integer|No|1|The number of the page to return.

 Default value: **1**. |
|PageSize|Integer|No|10|The number of entries to return on each page.

 Default value: **10**. Maximum value: **50**. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|GrantRules|Array of GrantRule| |The permission information about the SAG instance. |
|GrantRule| | | |
|CcnInstanceId|String|ccn-hd\*\*\*\*\*\*\*\*\*\*|The ID of the CCN instance. |
|CcnUid|Long|123456|The user ID \(UID\) of the Alibaba Cloud account to which the CCN instance belongs. |
|CreateTime|Long|156576751700|The timestamp when the permissions were granted. |
|GrantTrafficService|Boolean|false|Indicates whether the CCN instance is granted permissions to manage network traffic from the SAG instance.

 -   **true**: granted
-   **false**: not granted |
|InstanceId|String|123455|The ID of the region where the SAG instance is deployed. |
|SmartAGId|String|sag-hdhgn\*\*\*\*\*|The ID of the SAG instance. |
|PageNumber|Integer|2|The page number of the returned page. |
|PageSize|Integer|10|The number of entries returned per page. |
|RequestId|String|6E1674AC-083C-4031-B047-7A66E418E0C6|The ID of the request. |
|TotalCount|Integer|2|The total number of entries returned. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=DescribeGrantSagRules
&RegionId=cn-hangzhou
&SmartAGId=sag-hdg*************
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeGrantSagRulesResponse>
  <TotalCount>1</TotalCount>
  <RequestId>72CD8E55-CAC3-416B-9E18-5FF60D991713</RequestId>
  <PageSize>10</PageSize>
  <PageNumber>1</PageNumber>
  <GrantRules>
        <GrantRule>
              <InstanceId>16884015959****</InstanceId>
              <GrantTrafficService>false</GrantTrafficService>
              <CcnInstanceId>ccn-al2yjgtmsls4cu****</CcnInstanceId>
              <CreateTime>1609382634000</CreateTime>
              <CcnUid>13439858877****</CcnUid>
              <SmartAGId>sag-0ep6gx9wjvly4m****</SmartAGId>
        </GrantRule>
  </GrantRules>
</DescribeGrantSagRulesResponse>
```

`JSON` format

```
{
	"TotalCount": 1,
	"RequestId": "72CD8E55-CAC3-416B-9E18-5FF60D991713",
	"PageSize": 10,
	"PageNumber": 1,
	"GrantRules": {
		"GrantRule": [
			{
				"InstanceId": "16884015959****",
				"GrantTrafficService": false,
				"CcnInstanceId": "ccn-al2yjgtmsls4cu****",
				"CreateTime": 1609382634000,
				"CcnUid": "13439858877****",
				"SmartAGId": "sag-0ep6gx9wjvly4m****"
			}
		]
	}
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

