# ResetSmartAccessGatewayClientUserPassword {#doc_api_Smartag_ResetSmartAccessGatewayClientUserPassword .reference}

Resets the password of a Smart Access Gateway \(SAG\) Software client.

## Debug {#apiExplorer .section}

Use [OpenAPI Explorer](https://api.aliyun.com/#product=Smartag&api=ResetSmartAccessGatewayClientUserPassword) to perform debug operations and generate SDK code examples.

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|RegionId|String |Yes|cn-shanghai|The ID of the region to which the SAG Software client belongs.

 |
|SmartAGId|String |Yes|sag-jdfnf\*\*\*\*\*\*\*\*\*|The ID of the SAG Software instance.

 |
|UserName|String |Yes|doctest|The username. The usernames associated with the same software instance must be unique.

 The username and password are mutually dependent. If one is specified, the other must also be specified.

 |
|Action|String|No|ResetSmartAccessGatewayClientUserPassword|The name of this action.

 Value: **ResetSmartAccessGatewayClientUserPassword**

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|RequestId|String |BE1F7E80-4558-4021-B6D2-B94DA8AAAF81|The ID of the request.

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/? Action=ResetSmartAccessGatewayClientUserPassword
&RegionId=cn-shanghai
&SmartAGId=sag-jdfnf*********
&UserName=doctest
&<CommonParameters>

```

Response example

`XML` format

``` {#xml_return_success_demo}
<ResetSmartAccessGatewayClientUserPassword> 
  <RequestId>BE1F7E80-4558-4021-B6D2-B94DA8AAAF81</RequestId> 
</ResetSmartAccessGatewayClientUserPassword> 

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"BE1F7E80-4558-4021-B6D2-B94DA8AAAF81"
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

