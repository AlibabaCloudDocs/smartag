# DescribeUserOnlineClients {#doc_api_Smartag_DescribeUserOnlineClients .reference}

Queries the list of online connections of a user based on the username and Smart Access Gateway \(SAG\) Software instance ID.

## Debug {#apiExplorer .section}

Use [OpenAPI Explorer](https://api.aliyun.com/#product=Smartag&api=DescribeUserOnlineClients) to perform debug operations and generate SDK code examples.

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|RegionId|String|Yes|cn-shanghai| The ID of the region to which the SAG Software instance belongs.

 |
|SmartAGId|String|Yes|sag-wfjgn\*\*\*\*\*\*\*\*\*\*| The ID of the SAG Software instance.

 |
|UserName|String|Yes|doctest| The username. Usernames associated with the same SAG Software instance must be unique.

 The username and password are mutually dependent. If one is specified, the other must also be specified.

 |
|Action|String|No|DescribeUserOnlineClients| The name of this action.

 Value: **DescribeUserOnlineClients**

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|RequestId|String|7108A98F-C47D-45F7-A4D8-C2E3022735DA| The ID of the request.

 |
|Users| | | The user information.

 |
|└ClientIp|String|10.\*\*. \*\*. \*\*| The IP address of the Alibaba Cloud Software client.

 |
|└OnlineTime|String|1559125519| The time of getting online.

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeUserOnlineClients
&RegionId=cn-shanghai
&SmartAGId=sag-wfjgn**********
&UserName=doctest
&<CommonParameters>

```

Response example

`XML` format

``` {#xml_return_success_demo}
<DescribeUserOnlineClients>
  <Users>
    <User>
      <OnlineTime>1559125519</OnlineTime>
      <ClientIp>192.168.0.2</ClientIp>
    </User>
  </Users>
  <RequestId>92B22889-5451-4A1D-9432-66ED5AB3DD04</RequestId>
</DescribeUserOnlineClients> 

```

`JSON` format

``` {#json_return_success_demo}
{
	"Users" : {
		"User" : [
			{
				"OnlineTime":"1559125519",
				"ClientIp":"192.168.0.2"
			}
		]
	},
	"RequestId":"92B22889-5451-4A1D-9432-66ED5AB3DD04"
}
```

## Error codes {#section_hq9_nd6_pnc .section}

|HTTP status code|Error code|Error message|Description|
|----------------|----------|-------------|-----------|
|400|ClientUser.NameEmpty|You must specify UserName.|The username cannot be empty.|
|400|ClientUser.NameInvalid|The specified UserName is invalid.|The specified username is invalid.|
|400|SAG.InstanceIdEmpty|You must specify the SAG instance ID.|The ID of the SAG instance is empty.|
|400|SAG.InstanceNoFound|The specified SAG instance does not exist.|The Specified SAG instance does not exist.|

[See common error codes](https://error-center.aliyun.com/status/product/Smartag)

