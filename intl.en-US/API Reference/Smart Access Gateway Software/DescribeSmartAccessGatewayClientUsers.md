# DescribeSmartAccessGatewayClientUsers {#doc_api_Smartag_DescribeSmartAccessGatewayClientUsers .reference}

Queries the list of users of a Smart Access Gateway \(SAG\) Software instance.

## Debug {#apiExplorer .section}

Use [API Explorer](https://api.aliyun.com/#product=Smartag&api=DescribeSmartAccessGatewayClientUsers) to perform debug operations and generate SDK code examples.

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|RegionId|String |Yes|cn-shanghai|The ID of the region to which the SAG Software instance belongs.

 |
|SmartAGId|String |Yes|sag-jfkskjfjf\*\*\*\*\*\*\*\*|The ID of the SAG Software instance.

 |
|Action|String |No|DescribeSmartAccessGatewayClientUsers|The name of this action.

 Value:**DescribeSmartAccessGatewayClientUsers**

 |
|PageNo|Integer  |No|1|The number of pages to return. Start value: 1

 Default value:**1**

 |
|PageSize|Integer  |No|21|The number of entries per page. Maximum value: 100.

 Default value: **50**

 |
|UserName|String |No|doctest|The username. Usernames associated with the same SAG Software instance must be unique.

 The username and password are mutually dependent. If one is specified, the other must also be specified.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|PageNo|Integer|2|The number of pages to return. Start value: 1

 Default value: 1

 |
|PageSize|Integer  |12|The number of entries per page. Maximum value: 100

 Default value:**50**

 |
|RequestId|String |62F4CF10-F909-487E-8E95-BC35457C5F50| The ID of the request.

 |
|TotalCount|Integer|2|The number of users.

 |
|Users| | |The list of client users of a SAG Software instance.

 |
|└Bandwidth|Integer|2|The bandwidth.

 |
|└ClientIp|String |10.\*\*. \*\*. \*\*|The IP address of the software client.

 |
|└UserMail|String |test@example.com|The email address of the common user.

 |
|└UserName|String |doctest|The name of the user.

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeSmartAccessGatewayClientUsers
&RegionId=cn-shanghai
&SmartAGId=sag-jfkskjfjf********
&<CommonParameters>

```

Response example

`XML` format

``` {#xml_return_success_demo}
<DescribeSmartAccessGatewayClientUsers>
  <Users>
    <User>
      <SmartAccessGatewayId>sag-va03wf***idaj00g6x</SmartAccessGatewayId> 
      <IsStaticIp>0</IsStaticIp>
      <UserMail>dd@example.com</UserMail> 
      <UserName>dd@example.com</UserName>
      <Bandwidth>2</Bandwidth>
    </User>
  </Users>
  <TotalCount>1</TotalCount> 
  <PageSize>10</PageSize> 
  <RequestId>62F4CF10-F909-487E-8E95-BC35457C5F50</RequestId> 
  <Page>1</Page>
</DescribeSmartAccessGatewayClientUsers> 

```

`JSON` format

``` {#json_return_success_demo}
{
	"Users" : {
		"User" : [
			{
				"SmartAccessGatewayId":"sag-va03****idaj00g6x",
				"IsStaticIp":0,
				"UserMail":"dd@example.com",
				"UserName":"dd@example.com",
				"Bandwidth":2
			}
		]
	},
	"TotalCount":1,
	"PageSize":10,
	"PageNo":1,
	"RequestId":"62F4CF10-F909-487E-8E95-BC35457C5F50"
}
```

## Error codes { .section}

|HTTP status code|Error code|Error message |Description|
|----------------|----------|--------------|-----------|
|400 |SAG.InstanceIdEmpty|You must specify the SAG instance ID.|The ID of the SAG instance is empty.|
|400 |SAG.InstanceNoFound|The specified SAG instance does not exist.|The specified SAG instance does not exist.|

[See common error codes](https://error-center.aliyun.com/status/product/Smartag)

