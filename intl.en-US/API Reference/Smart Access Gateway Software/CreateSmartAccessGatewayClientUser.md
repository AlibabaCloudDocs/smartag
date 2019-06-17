# CreateSmartAccessGatewayClientUser {#doc_api_Smartag_CreateSmartAccessGatewayClientUser .reference}

Creates a user for a Smart Access Gateway \(SAG\) Software instance.

## Debug {#apiExplorer .section}

Use [OpenAPI Explorer](https://api.aliyun.com/#product=Smartag&api=CreateSmartAccessGatewayClientUser) to perform debug operations and generate SDK code examples.

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|Bandwidth|Long|Yes|20| Bandwidth. Unit: Kbps. Maximum value: 2,000 Kbps.

 |
|RegionId|String|Yes|cn-shanghai| The ID of the region to which the SAG Software instance belongs.

 |
|SmartAGId|String|Yes|sag-gnhe6sywtare5\*\*\*\*\*\*| The ID of the SAG Software instance.

 |
|UserMail|String|Yes|test@example.com| The email address of a common user, which is used by the administrator to send the account information for logging on to the client of the SAG Software.

 |
|Action|String|No|CreateSmartAccessGatewayClientUser| The name of this action.

 Value: **CreateSmartAccessGatewayClientUser**

 |
|ClientIp|String|No|10.\*\*. \*\*. \*\*| -   If you enable this option, you must set the IP address of the software client. Then, the current account always accesses the client by using the specified IP address.

**Note:** The IP address of the software client must be in the private CIDR block.

-   If you disable this option, the system automatically allocates an available IP address from the private CIDR block. The IP address is reallocated each time a re-connection is initiated.

 |
|UserName|String|No|doctest| The username. Usernames associated with the same SAG Software instance must be unique.

 The username and password are mutually dependent. If one is specified, the other must also be specified.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|Bandwidth|Integer|2| Bandwidth.

 |
|ClientIp|String|10.\*\*. \*. \*\*| The IP address of the software client.

 |
|RequestId|String|72E82F5E-66E8-4C22-BF1F-5CEB7DC132E7| The ID of the request.

 |
|UserMail|String|test@example.com| The email address of a common user.

 |
|UserName|String|doc| Usernames. Usernames under the same SAG Software instance must be unique.

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/? Action=CreateSmartAccessGatewayClientUser
&Bandwidth=20
&RegionId=cn-shanghai
&SmartAGId=sag-gnhe6sywtare5******
&UserMail=test@example.com
&<CommonParameters>

```

Response example

`XML` format

``` {#xml_return_success_demo}
<CreateSmartAccessGatewayClientUser> 
  <IsStaticIp>0</IsStaticIp>
  <RequestId>72E82F5E-66E8-4C22-BF1F-5CEB7DC132E7</RequestId>
  <UserMail>dd@example.com</UserMail>
  <UserName>dd@example.com</UserName>
  <Bandwidth>2</Bandwidth>
</CreateSmartAccessGatewayClientUser>

```

`JSON` format

``` {#json_return_success_demo}
{
	"IsStaticIp":0,
	"RequestId":"72E82F5E-66E8-4C22-BF1F-5CEB7DC132E7",
	"UserMail":"dd@example.com",
	"UserName":"dd@example.com",
	"Bandwidth":2
}
```

## Error codes {#section_gh3_uaz_wpc .section}

|HTTP status code|Error code|Error message|Description|
|----------------|----------|-------------|-----------|
|400|ClientUser.BandwidthInvalid|The specified Bandwidth is invalid.|The specified bandwidth is invalid.|
|400|ClientUser.EmailEmpty|You must specify UserEmail.|The user email cannot be empty.|
|400|ClientUser.EmailInvalid|The format of the specified UserEmail is invalid.|The user email is invalid.|
|400|ClientUser.InvalidClientIp|The specified ClientIp is invalid.|The specified user IP address is invalid.|
|400|ClientUser.IpEmpty|You must specify ClientIp.|You must specify a static IP address.|
|400|ClientUser.IpInvalid|The specified ClientIp is invalid.|The specified static IP address is invalid.|
|400|ClientUser.NameEmpty|You must specify UserName.|The username cannot be empty.|
|400|ClientUser.NameInvalid|The specified UserName is invalid.|The specified username is invalid.|
|400|ClientUser.UserExist|The specified user already exists.|The specified username already exists.|
|400|ClientUser.UserOverLimit|The maximum number of users is exceeded.|The user quota has been exceeded.|
|400|SAG.CidrEmpty|You must specify the CIDR blocks of SAG.|The specified SAG CIDR block is empty.|

[See common error codes](https://error-center.aliyun.com/status/product/Smartag)

