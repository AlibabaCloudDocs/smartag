# RoamClientUser

Enables roaming for SAG APP clients. After roaming is enabled, the clients can access their private networks across areas.

## Prerequisites

Before you perform this operation, read and understand the functions and descriptions of the roaming feature. For more information, see [Configure roaming for clients](~~177220~~).

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates a sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=RoamClientUser&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|RoamClientUser|The operation that you want to perform.

 Set the value to **RoamClientUser**. |
|OriginRegionId|String|Yes|cn-shanghai|The ID of the region where the source SAG APP instance is deployed. |
|OriginSmartAGId|String|Yes|sag-m9uhqekwnqcnyy\*\*\*\*|The ID of the source SAG APP instance. |
|RegionId|String|Yes|cn-hangzhou|The ID of the region where the destination SAG APP instance is deployed. |
|TargetSmartAGId|String|Yes|sag-ghwa10ko6ndwug\*\*\*\*|The ID of the destination SAG APP instance. |
|UserName|String|Yes|test1|The usernames of the clients for which you want to enable roaming. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|3200E8A3-563F-4FFC-8BDB-0F1263FA69E8|The ID of the request. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=RoamClientUser
&OriginRegionId=cn-shanghai
&OriginSmartAGId=sag-m9uhqekwnqcnyy****
&TargetSmartAGId=sag-ghwa10ko6ndwug****
&UserName=test1
&<Common request parameters>
```

Sample success responses

`XML` format

```
<RoamClientUserResponse>
  <RequestId>26C24B63-5E5A-413A-9E49-FC0C0AE9DFB7</RequestId>
</RoamClientUserResponse>
```

`JSON` format

```
{
	"RequestId": "26C24B63-5E5A-413A-9E49-FC0C0AE9DFB7"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|SAG.InstanceNoFound|The specified SAG instance does not exist.|The error message returned because the specified SAG instance does not exist.|
|400|ClientUser.NotSupportAction|You cannot create a user in the current SAG instance.|The error message returned because the specified SAG instance does not allow you to create client accounts.|
|400|SAG.CidrEmpty|You must specify the CIDR blocks of SAG.|The error message returned because the CIDR block of the SAG instance is not specified.|
|400|ClientUser.BandwidthInvalid|The specified Bandwidth is invalid.|The error message returned because the bandwidth specified for the client account is invalid.|
|400|ClientUser.InvalidClientIp|The specified ClientIp is invalid.|The error message returned because the specified client IP address is invalid.|
|400|ClientUser.UserOverLimit|The maximum number of users is exceeded.|The error message returned because the number of client accounts added to the SAG APP instance has reached the upper limit.|
|400|ClientUser.UserExist|The specified user already exists.|The error message returned because the specified client account already exists.|
|400|ClientUser.NameInvalid|The specified UserName is invalid.|The error message returned because the format of the username is invalid.|
|400|SAG.CidrOverlap|The specified CIDR overlaps with an existing CIDR.|The error message returned because the CIDR blocks overlap with each other.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

