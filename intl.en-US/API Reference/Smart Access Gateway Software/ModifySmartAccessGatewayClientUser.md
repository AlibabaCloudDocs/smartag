# ModifySmartAccessGatewayClientUser {#doc_api_Smartag_ModifySmartAccessGatewayClientUser .reference}

Modifies the bandwidth for a Smart Access Gateway \(SAG\) Software user.

## Debug {#apiExplorer .section}

Use [OpenAPI Explorer](https://api.aliyun.com/#product=Smartag&api=ModifySmartAccessGatewayClientUser) to perform debug operations and generate SDK code examples.

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|Bandwidth|Integer|Yes|2| The bandwidth. Unit: Kbps. Maximum value: 2,000 Kbps.

 |
|RegionId|String|Yes|cn-shanghai| The ID of the region to which the SAG Software instance belongs.

 |
|SmartAGId|String|Yes|sag-kdhej\*\*\*\*\*\*\*8| The ID of the SAG Software instance.

 |
|UserName|String|Yes|doctest| The username. Usernames associated with the same SAG Software instance must be unique.

 The username and password are mutually dependent. If one is specified, the other must also be specified.

 |
|Action|String|No|ModifySmartAccessGatewayClientUser| The name of this action.

 Value: **ModifySmartAccessGatewayClientUser**

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|Bandwidth|Integer|2| Bandwidth.

 |
|ClientIp|String|10.\*\*. \*\*. \*\*| The IP address of the software client.

 |
|RequestId|String|5F0078B5-8AAD-4B53-8351-4C91B8EA528A| The ID of the request.

 |
|UserMail|String|test@example.com| The email address of a common user.

 |
|UserName|String|doctes| The name of the user.

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/? Action=ModifySmartAccessGatewayClientUser
&Bandwidth=2
&RegionId=cn-shanghai
&SmartAGId=sag-kdhej*******8
&UserName=doctest
&<CommonParameters>

```

Response example

`XML` format

``` {#xml_return_success_demo}
<ModifySmartAccessGatewayClientUser> 
  <RequestId>5F0078B5-8AAD-4B53-8351-4C91B8EA528A</RequestId> 
  <UserMail>dd@example.com</UserMail>
  <UserName>dd@example.com</UserName>
  <Bandwidth>1</Bandwidth> 
</ModifySmartAccessGatewayClientUser> 

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"5F0078B5-8AAD-4B53-8351-4C91B8EA528A",
	"UserMail":"dd@example.com",
	"UserName":"dd@example.com",
	"Bandwidth":1
}
```

## Error codes {#section_y03_lyn_43z .section}

|HTTP status code|Error code|Error message|Description|
|----------------|----------|-------------|-----------|
|400|ClientUser.BandwidthInvalid|The specified Bandwidth is invalid.|The specified bandwidth is invalid.|
|400|ClientUser.NameEmpty|You must specify UserName.|The username cannot be empty.|
|400|ClientUser.NameInvalid|The specified UserName is invalid.|The specified username is invalid.|
|400|SAG.InstanceIdEmpty|You must specify the SAG instance ID.|The ID of the specified SAG instance is empty.|
|400|SAG.InstanceNoFound|The specified SAG instance does not exist.|The specified SAG instance does not exist.|

[See common error codes](https://error-center.aliyun.com/status/product/Smartag)

