# DescribeSagOnlineClientStatistics {#doc_api_Smartag_DescribeSagOnlineClientStatistics .reference}

Queries the online connection data of current users of Smart Access Gateway Software \(SAG\) instances.

## Debug {#apiExplorer .section}

Use [OpenAPI Explorer](https://api.aliyun.com/#product=Smartag&api=DescribeSagOnlineClientStatistics) to perform debug operations and generate SDK code examples.

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|RegionId|String|Yes|cn-shanghai| The ID of the region to which the SAG Software instances belongs.

 |
|Action|String|No|DescribeSagOnlineClientStatistics| The name of this action.

 Value: **DescribeSagOnlineClientStatistics**

 |
|SmartAGIds.N|RepeatList|No|12| The list of SAG Software instance IDs. Maximum value: 50.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|RequestId|String|9EC839B6-0EA5-4F19-A4B7-A9E465D057AE| The ID of the request.

 |
|SagStatistics| | | The online connection data.

 |
|└OnlineCount|String|2| The number of online clients connected to the SAG Software instance currently.

 |
|└SmartAGId|String|sag-va03wf4l4idaj\*\*\*\*\*| The ID of the SAG Software instance.

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeSagOnlineClientStatistics
&RegionId=cn-shanghai
&<CommonParameters>

```

Response example

`XML` format

``` {#xml_return_success_demo}
<DescribeSagOnlineClientStatistics>
  <RequestId>9EC839B6-0EA5-4F19-A4B7-A9E465D057AE</RequestId>
  <SagStatistics>
    <Statistics>
      <SmartAGId>sag-va03wf4l4idaj0***</SmartAGId>
      <OnlineCount>0</OnlineCount>
    </Statistics> 
  </SagStatistics>
</DescribeSagOnlineClientStatistics>

```

`JSON` format

``` {#json_return_success_demo}
{
	"SagStatistics":{
		"statistics" : {
			{
				"SmartAGId":"sag-va03wf4l4idaj00***",
				"OnlineCount": 10,
			}
		]
	},
	"RequestId":"9EC839B6-0EA5-4F19-A4B7-A9E465D057AE"
}
```

## Error codes {#section_oyd_03k_omk .section}

[See common error codes](https://error-center.aliyun.com/status/product/Smartag)

