# DescribeGrantSagRules

You can call this operation to query rules that authorize a Smart Access Gateway \(SAG\) instance to communicate with Cloud Connect Network \(CCN\) instances that are under other Alibaba Cloud accounts.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=DescribeGrantSagRules&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|DescribeGrantSagRules|The operation that you want to perform.

 Set the value to **DescribeGrantSagRules**. |
|RegionId|String|Yes|cn-hangzhou|The ID of the region where the SAG instance is deployed. |
|SmartAGId|String|Yes|sag-hdg\*\*\*\*\*\*\*\*\*\*\*\*\*|The ID of the SAG instance. |
|PageNumber|Integer|No|1|The number of the page to return. Default value: **1**. |
|PageSize|Integer|No|10|The number of entries to return on each page. Default value: **10**. Maximum value: **50**. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|GrantRules|Array| |The rule that authorizes the SAG instance to communicate with a CCN instance under another Alibaba Cloud account. |
|GrantRule| | | |
|CcnInstanceId|String|ccn-hd\*\*\*\*\*\*\*\*\*\*|The ID of the CCN instance. |
|CcnUid|Long|13323444243434|The UID of the Alibaba Cloud account that owns the CCN instance. |
|CreateTime|Long|156576751700|The time when the rule was created. |
|InstanceId|String|1688401595963306|The UID of the Alibaba Cloud account that owns the SAG instance. |
|SmartAGId|String|sag-hdhgn\*\*\*\*\*|The ID of the SAG instance. |
|PageNumber|Integer|2|The page number of the returned page. |
|PageSize|Integer|10|The number of entries returned per page. |
|RequestId|String|6E1674AC-083C-4031-B047-7A66E418E0C6|The ID of the request. |
|TotalCount|Integer|2|The total number of rules. |

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
	  <GrantRules>
		    <GrantRule>
			      <CcnInstanceId>ccn-4dwoqcqu******</CcnInstanceId>
			      <CcnUid>1688401595963306</CcnUid>
			      <CreateTime>1565767517000</CreateTime>
			      <InstanceId>1688401595963306</InstanceId>
			      <SmartAGId>sag-7sc8ib3noaov*****</SmartAGId>
		    </GrantRule>
	  </GrantRules>
	  <PageNumber>1</PageNumber>
	  <PageSize>10</PageSize>
	  <RequestId>25B3FD03-DC56-4B88-8730-273485FAE0DC</RequestId>
	  <TotalCount>1</TotalCount>
    </DescribeGrantSagRulesResponse>
```

`JSON` format

```
{
    "GrantRules":{
        "GrantRule":[
            {
                "CcnInstanceId":"ccn-4dwoqcqu******",
                "CcnUid":1688401595963306,
                "CreateTime":1565767517000,
                "InstanceId":1688401595963306,
                "SmartAGId":"sag-7sc8ib3noaov*****"
            }
        ]
    },
    "PageNumber":1,
    "PageSize":10,
    "RequestId":"25B3FD03-DC56-4B88-8730-273485FAE0DC",
    "TotalCount":1
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

