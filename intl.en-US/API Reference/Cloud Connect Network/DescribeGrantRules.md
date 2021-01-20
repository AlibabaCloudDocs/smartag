# DescribeGrantRules

Queries the permission information about a Cloud Connect Network \(CCN\) instance.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=DescribeGrantRules&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|DescribeGrantRules|The operation that you want to perform.

 Set the value to **DescribeGrantRules**. |
|RegionId|String|Yes|cn-shanghai|The ID of the region where the CCN instance is deployed. |
|AssociatedCcnId|String|No|ccn-n2935s1mnwv8i\*\*\*\*\*|The ID of the CCN instance. |
|PageSize|Integer|No|10|The number of entries to return on each page.

 Default value: **10**. Maximum value: **50**. |
|PageNumber|Integer|No|1|The number of the page to return.

 Default value: **1**. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|GrantRules|Array of GrantRule| |The information about the permissions. |
|GrantRule| | | |
|CcnInstanceId|String|ccn-n2935s1mnwv8i\*\*\*\*\*|The ID of the CCN instance. |
|CcnUid|Long|213213|The user ID \(UID\) of the Alibaba Cloud account to which the CCN instance belongs. |
|CenInstanceId|String|cen-0jtu0bcbika5b5\*\*\*\*|The ID of the Cloud Enterprise Network \(CEN\) instance. |
|CenUid|Long|213213|The UID of the Alibaba Cloud account to which the CEN instance belongs. |
|GmtCreate|Long|1563439920000|The timestamp when the permissions were granted. |
|GmtModified|Long|1563439920000|The timestamp when the permissions were modified. |
|GrantRuleId|String|18313265-d988-406c-965d-3e110ff\*\*\*\*\*|The ID of the permission. |
|GrantTrafficService|Boolean|false|Indicates whether the CEN instance is granted permissions to manage network traffic from the CCN instance. Valid values:

 -   **true**: granted
-   **false**: not granted |
|RegionId|String|cn-shanghai|The ID of the region where the CCN instance is deployed. |
|PageNumber|Integer|1|The page number of the returned page. |
|PageSize|Integer|10|The number of entries returned per page. |
|RequestId|String|FA579C2D-84A0-4BA1-B9C3-1E5A3B15F1B6|The ID of the request. |
|TotalCount|Integer|1|The total number of entries returned. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=DescribeGrantRules
&RegionId=cn-shanghai
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeGrantRulesResponse>
  <TotalCount>1</TotalCount>
  <RequestId>22B1031D-4367-46D6-879E-49ECD28B12D3</RequestId>
  <PageSize>10</PageSize>
  <PageNumber>0</PageNumber>
  <GrantRules>
        <GrantRule>
              <GmtCreate>1609392288000</GmtCreate>
              <CenUid>1343985887****</CenUid>
              <GrantTrafficService>false</GrantTrafficService>
              <CcnInstanceId>ccn-5ldtbj8i7nh6pp****</CcnInstanceId>
              <GrantRuleId>3a9bfd9f-48df-41ea-ad88****</GrantRuleId>
              <CenInstanceId>cen-voitp3yy1xlta8****</CenInstanceId>
              <GmtModified>1609392288000</GmtModified>
              <CcnUid>168840159596****</CcnUid>
              <RegionId>cn-shanghai</RegionId>
        </GrantRule>
  </GrantRules>
</DescribeGrantRulesResponse>
```

`JSON` format

```
{
	"TotalCount": 1,
	"RequestId": "22B1031D-4367-46D6-879E-49ECD28B12D3",
	"PageSize": 10,
	"PageNumber": 0,
	"GrantRules": {
		"GrantRule": [
			{
				"GmtCreate": 1609392288000,
				"CenUid": "1343985887****",
				"GrantTrafficService": false,
				"CcnInstanceId": "ccn-5ldtbj8i7nh6pp****",
				"GrantRuleId": "3a9bfd9f-48df-41ea-ad88****",
				"CenInstanceId": "cen-voitp3yy1xlta8****",
				"GmtModified": 1609392288000,
				"CcnUid": "168840159596****",
				"RegionId": "cn-shanghai"
			}
		]
	}
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

