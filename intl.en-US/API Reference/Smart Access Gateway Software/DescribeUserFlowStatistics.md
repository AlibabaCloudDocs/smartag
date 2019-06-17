# DescribeUserFlowStatistics {#doc_api_Smartag_DescribeUserFlowStatistics .reference}

Queries the traffic statistics of users under a Smart Access Gateway \(SAG\) Software instance.

## Debug {#apiExplorer .section}

Use [OpenAPI Explorer](https://api.aliyun.com/#product=Smartag&api=DescribeUserFlowStatistics) to perform debug operations and generate SDK code examples.

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|RegionId|String|Yes|cn-hangzhou| The ID of the region to which the SAG Software instance belongs.

 |
|SmartAGId|String|Yes|sag-mfkg\*\*\*\*\*| The ID of the SAG Software instance.

 |
|UserNames.N|RepeatList|Yes|12| The list of usernames. Maximum value: 50.

 |
|Action|String|No|DescribeUserFlowStatistics| The name of this action.

 Value: **DescribeUserOnlineClients**

 |
|StatisticsDate|String|No|201905| The month in which the data is collected. Format: yyyyMM.

 If you do not specify this parameter, the data of the current month is collected by default.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|RequestId|String|9552AD68-18EA-4074-B27D-40040FBA9683| The ID of the request.

 |
|SagStatistics| | | The traffic statistics.

 |
|└TotalBytes|String|12| The traffic amount. Unit: Bytes.

 |
|└UserName|String|doctest| The name of the user.

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeUserFlowStatistics
&RegionId=cn-hangzhou 
&SmartAGId=sag-mfkg*****
&UserNames. 1=12
&<CommonParameters>

```

Response example

`XML` format

``` {#xml_return_success_demo}
<DescribeUserFlowStatistics>
  <SagStatistics>
    <Statistics>
      <UserName>zhanlg</UserName>
      <TotalBytes>555352</TotalBytes>
    </Statistics>
  </SagStatistics> 
  <RequestId>ADD09081-31A9-4E7D-B15C-135C6EBEEB63</RequestId>
</DescribeUserFlowStatistics>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"ADD09081-31A9-4E7D-B15C-135C6EBEEB63",
	"SagStatistics":{
		"Statistics":[
			{
				"UserName":"zhanlg",
				"TotalBytes":555352
			}
		]
	}
}
```

## Error codes {#section_td1_6gw_dva .section}

|HTTP status code|Error code|Error message|Description|
|----------------|----------|-------------|-----------|
|400|SAG.InstanceIdEmpty|You must specify the SAG instance ID.|The ID of the SAG instance is empty.|
|400|SAG.InstanceNoFound|The specified SAG instance does not exist.|The specified SAG instance does not exist.|

[See common error codes](https://error-center.aliyun.com/status/product/Smartag)

