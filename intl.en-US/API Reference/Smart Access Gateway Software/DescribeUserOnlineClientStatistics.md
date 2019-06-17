# DescribeUserOnlineClientStatistics {#doc_api_Smartag_DescribeUserOnlineClientStatistics .reference}

Queries the user statistics of a Smart Access Gateway \(SAG\) Software instance.

## Debug {#apiExplorer .section}

Use [OpenAPI Explorer](https://api.aliyun.com/#product=Smartag&api=DescribeUserOnlineClientStatistics) to perform debug operations and generate SDK code examples.

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|RegionId|String |Yes|cn-shanghai|The ID of the region to which the SAG Software instance belongs.

 |
|UserNames.N|RepeatList|Yes|12|The list of users. Maximum value: 50.

 |
|Action|String |No|DescribeUserOnlineClientStatistics|The name of this action.

 Value: **DescribeUserOnlineClientStatistics**

 |
|SmartAGId|String |No|sag-sfjg\*\*\*\*\*|The ID of the SAG Software instance.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|RequestId|String |14846A6A-2192-4F6A-B272-B8BD68EBC89B|The ID of the request. 

 |
|UserStatistics| | |The list of online users.

 |
|└OnlineCount|String |2|The number of online connections.

 |
|└UserName|String |doctest|The name of the user.

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeUserOnlineClientStatistics
&RegionId=cn-shanghai
&UserNames. 1 = 12
&<CommonParameters>

```

Response example

`XML` format

``` {#xml_return_success_demo}
<DescribeUserOnlineClientStatistics>
  <RequestId>14846A6A-2192-4F6A-B272-B8BD68EBC89B</RequestId>
  <UserStatistics>
    <Statistics>
      <UserName>doctest</UserName>
      <OnlineCount>0</OnlineCount>
    </Statistics>
  </UserStatistics>
</DescribeUserOnlineClientStatistics>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"14846A6A-2192-4F6A-B272-B8BD68EBC89B",
	"UserStatistics":{
		"statistics" : {
			{
				"UserName":"doctest",
				"OnlineCount":0
			}
		]
	}
}
```

## Error codes { .section}

|HTTP status code|Error code|Error message |Description|
|----------------|----------|--------------|-----------|
|400 |ClientUser.NameEmpty|You must specify UserName.|The username cannot be empty.|
|400 |ClientUser.NameInvalid|The specified UserName is invalid.|The specified username is invalid.|
|400 |SAG.InstanceIdEmpty|You must specify the SAG instance ID.|The ID of the SAG instance is empty.|
|400 |SAG.InstanceNoFound|The specified SAG instance does not exist.|The specified SAG instance does not exist.|

[See common error codes](https://error-center.aliyun.com/status/product/Smartag)

