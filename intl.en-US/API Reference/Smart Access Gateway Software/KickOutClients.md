# KickOutClients {#doc_api_Smartag_KickOutClients .reference}

Disables online connections based on the ID of the Smart Access Gateway \(SAG\) Software instance and username.

## Debug {#apiExplorer .section}

Use [OpenAPI Explorer](https://api.aliyun.com/#product=Smartag&api=KickOutClients) to perform debug operations and generate code examples.

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|RegionId|String|Yes|cn-shanghai| The ID of the region to which the SAG Software instance belongs.

 |
|SmartAGId|String|Yes|sag-ehjfb\*\*\*\*\*\*\*| The ID of the SAG Software instance.

 |
|Username|String|Yes|doctest| The username. Usernames associated with the same SAG Software instance must be unique.

 The username and password are mutually dependent. If one is specified, the other must also be specified.

 |
|Action|String|No|KickOutClients| The name of this action.

 Value: **KickOutClients**

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|RequestId|String|76FD7E08-6AA1-4B1B-99FB-8B3CA6C99A8E| The ID of the request.

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/? Action=KickOutClients
&RegionId=cn-shanghai
&SmartAGId=sag-ehjfb******* 
&Username=doctest 
&<CommonParameters>

```

Response example

`XML` format

``` {#xml_return_success_demo}
<KickOutClients>
  <RequestId>7108A98F-C47D-45F7-A4D8-C2E3022735DA</RequestId> 
</KickOutClients>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"7108A98F-C47D-45F7-A4D8-C2E3022735DA"
}
```

## Error codes {#section_t4k_yb7_mo7 .section}

|HTTP status code|Error code|Error message|Description|
|----------------|----------|-------------|-----------|
|400|ClientUser.NameEmpty|You must specify UserName.|The username cannot be empty.|
|400|SAG.InstanceNoFound|The specified DB instance does not exist.|The specified SAG instance does not exist.|

[See common error codes](https://error-center.aliyun.com/status/product/Smartag)

