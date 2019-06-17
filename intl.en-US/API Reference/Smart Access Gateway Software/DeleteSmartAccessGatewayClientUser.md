# DeleteSmartAccessGatewayClientUser {#doc_api_Smartag_DeleteSmartAccessGatewayClientUser .reference}

Deletes a client that is using the target Smart Access Gateway \(SAG\) Software.

## Debug {#apiExplorer .section}

Use [OpenAPI Explorer](https://api.aliyun.com/#product=Smartag&api=DeleteSmartAccessGatewayClientUser) to perform debug operations and generate SDK code examples.

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|RegionId|String|Yes|cn-shanghai| The ID of the region to which the SAG Software instance belongs.

 |
|SmartAGId|String|Yes|sag-hdjffn\*\*\*\*\*\*| The ID of the SAG Software instance.

 |
|Action|String|No|DeleteSmartAccessGatewayClientUser| The name of this action.

 Value: **DeleteSmartAccessGatewayClientUser**

 |
|UserName|String|No|doctest| The username. Usernames associated with the same SAG Software instance must be unique.

 The username and password are mutually dependent. If one is specified, the other must also be specified.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|RequestId|String|09AD82DC-FE26-4B66-B526-2FA6BE82A4D3| The ID of the request.

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/? Action=DeleteSmartAccessGatewayClientUser
&<CommonParameters>

```

Response example

`XML` format

``` {#xml_return_success_demo}
<DeleteSmartAccessGatewayClientUser> 
  <RequestId>09AD82DC-FE26-4B66-B526-2FA6BE82A4D3</RequestId> 
</DeleteSmartAccessGatewayClientUser> 

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"09AD82DC-FE26-4B66-B526-2FA6BE82A4D3"
}
```

## Error codes {#section_uym_npx_vgi .section}

|HTTP status code|Error code|Error message|Description|
|----------------|----------|-------------|-----------|
|400|SAG.InstanceIdEmpty|You must specify the SAG instance ID.|The ID of the SAG instance is empty.|
|400|SAG.InstanceNoFound|The specified SAG instance does not exist.|The specified SAG instance does not exist.|
|400|ClientUser.NameEmpty|You must specify UserName.|The username cannot be empty.|
|400|ClientUser.NameInvalid|The specified UserName is invalid.|The specified username is invalid.|

[See common error codes](https://error-center.aliyun.com/status/product/Smartag)

