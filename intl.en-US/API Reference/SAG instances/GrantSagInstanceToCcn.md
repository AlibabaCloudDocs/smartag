# GrantSagInstanceToCcn

Authorizes a Smart Access Gateway \(SAG\) instance to communicate with a Cloud Connect Network \(CCN\) instance that is under another Alibaba Cloud account.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=GrantSagInstanceToCcn&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|GrantSagInstanceToCcn|The operation that you want to perform.

 Set the value to **GrantSagInstanceToCcn**. |
|CcnInstanceId|String|Yes|ccn-jdh\*\*\*\*\*\*\*\*\*\*|The ID of the CCN instance. |
|CcnUid|Long|Yes|123456|The user ID \(UID\) of the Alibaba Cloud account to which the CCN instance belongs. |
|RegionId|String|Yes|cn-hangzhou|The ID of the region where the SAG instance is deployed. |
|SmartAGId|String|Yes|sag-hdh\*\*\*\*\*\*\*\*\*\*\*\*|The ID of the SAG instance. |
|GrantTrafficService|Boolean|No|true|Specifies whether to grant the CCN instance permissions to manage network traffic from the SAG instance.

 After the CCN instance is granted the permissions, the CCN instance can redirect the network traffic sent from the SAG instance to the Internet to Cloud Security Access Service \(CSAS\) for security audit.

 -   **true**: grants permissions.
-   **false**: does not grant permissions.

 **Note:** If you set the value to true and the SAG instance connected to the CCN instance has the secure rerouting feature enabled, you cannot revoke the permissions. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|InstanceId|String|sgc-e8lgeu4wzf\*\*\*\*\*\*\*|The ID of the permission policy. |
|RequestId|String|6E1674AC-083C-4031-B047-7A66E418E0C6|The ID of the request. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=GrantSagInstanceToCcn
&CcnInstanceId=ccn-jdh**********
&CcnUid=123535455445666
&RegionId=cn-hangzhou
&SmartAGId=sag-hdh************
&<Common request parameters>
```

Sample success responses

`XML` format

```
<GrantSagInstanceToCcnResponse>
  <InstanceId>sgc-e8lgeu4w********</InstanceId>
  <RequestId>5F40561D-1EB7-48CB-AA5B-79713E003356</RequestId>
</GrantSagInstanceToCcnResponse>
```

`JSON` format

```
{
    "InstanceId":"sgc-e8lgeu4w********",
    "RequestId":"5F40561D-1EB7-48CB-AA5B-79713E003356"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|CCN.InvalidUid|The specified CCN user ID is invalid.|The error message returned because the specified UID of the Alibaba Cloud account to which the specified CCN instance belongs is invalid.|
|400|CCN.InvalidId|You must specify the CCN instance ID.|The error message returned because the specified CCN instance ID does not exist.|
|400|SAG.InstanceIdEmpty|You must specify the SAG instance ID.|The error message returned because the specified SAG instance ID is not specified.|
|400|SAG.InstanceNoFound|The specified SAG instance does not exist.|The error message returned because the specified SAG instance does not exist.|
|400|SAG.GrantDuplicated|You have authorized another CCN instance to bind to the specified SAG instance. Revoke the authorization first.|The error message returned because the specified SAG instance is already associated with another CCN instance. Disassociate the SAG instance from the CCN instance first.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

