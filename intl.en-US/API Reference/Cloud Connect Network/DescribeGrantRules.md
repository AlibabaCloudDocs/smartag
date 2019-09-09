# DescribeGrantRules {#doc_api_Smartag_DescribeGrantRules .reference}

Queries the authorization rules of the associated CCN instance.

## Debug {#api_explorer .section}

[Use OpenAPI Explorer to perform debug operations and generate SDK code examples.](https://api.aliyun.com/#product=Smartag&api=DescribeGrantRules&type=RPC&version=2018-03-13)

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|RegionId|String|Yes|cn-shanghai|The ID of the region to which the CEN instance belongs.

 |
|Action|String|No|DescribeGrantRules|The name of this action. Value: **DescribeGrantRules**.

 |
|AssociatedCcnId|String|No|ccn-n2935s1mnwv8i\*\*\*\*\*|The ID of the associated CCN instance.

 |
|PageNumber|String|No|1|The page number. Default value: **1**.

 |
|PageSize|String|No|10|The number of rows per page. Default value: **10**. Maximum value: **50**.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|GrantRules| | |The authorization list.

 |
|CcnInstanceId|String|ccn-n2935s1mnwv8i\*\*\*\*\*|The ID of the CCN instance.

 |
|CcnUid|Long|213213|The user ID of the CCN instance.

 |
|CenInstanceId|String|3213214|The ID of the CEN instance.

 |
|CenUid|Long|213213|The user ID of the CEN instance.

 |
|GmtCreate|Long|1563439920000|The long-format timestamp of the rule creation. If the priorities of two rules are the same, the smaller timestamp takes effect first.

 |
|GmtModified|Long|1563439920000|The long-format timestamp of the last rule modification. If the priorities of two rules are the same, the smaller timestamp takes effect first.

 |
|GrantRuleId|String|18313265-d988-406c-965d-3e110ff\*\*\*\*\*|The ID of the authorization rule instance.

 |
|RegionId|String|cn-shanghai|The ID of the region.

 |
|PageNumber|Integer|1|The page number.

 |
|PageSize|Integer|10|The page size.

 |
|RequestId|String|FA579C2D-84A0-4BA1-B9C3-1E5A3B15F1B6| The ID of the request.

 |
|TotalCount|Integer|1|The total number of records.

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeGrantRules
&RegionId=cn-shanghai
&<CommonParameters>

```

Response example

`XML` format

``` {#xml_return_success_demo}
<DescribeGrantRulesResponse>
	  <PageNumber>1</PageNumber>
	  <GrantRules>
		    <GrantRule>
			      <GrantRuleId>18313265-d988-406c-965d-3e110ff*****</GrantRuleId>
			      <CenUid>213213</CenUid>
			      <CcnInstanceId>ccn-n2935s1mnwv8i*****</CcnInstanceId>
			      <CenInstanceId>3213214</CenInstanceId>
			      <RegionId>cn-shanghai</RegionId>
			      <GmtCreate>1563439920000</GmtCreate>
			      <GmtModified>1563439920000</GmtModified>
		    </GrantRule>
	  </GrantRules>
	  <TotalCount>1</TotalCount>
	  <PageSize>10</PageSize>
	  <RequestId>FA579C2D-84A0-4BA1-B9C3-1E5A3B15F1B6</RequestId>
</DescribeGrantRulesResponse>
```

`JSON` format

``` {#json_return_success_demo}
{
	"PageNumber":1,
	"GrantRules":{
		"GrantRule":[
			{
				"GrantRuleId":"18313265-d988-406c-965d-3e110ff*****",
				"CenUid":213213,
				"CcnInstanceId":"ccn-n2935s1mnwv8i*****",
				"CenInstanceId":"3213214",
				"RegionId":"cn-shanghai",
				"GmtCreate":1563439920000,
				"GmtModified":1563439920000
			}
		]
	},
	"TotalCount":1,
	"PageSize":10,
	"RequestId":"FA579C2D-84A0-4BA1-B9C3-1E5A3B15F1B6"
}
```

## Errors { .section}

