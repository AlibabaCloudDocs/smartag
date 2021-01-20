# GrantInstanceToCbn

Authorizes a Cloud Enterprise Network \(CEN\) instance to communicate with a Cloud Connect Network \(CCN\) instance that is under another Alibaba Cloud account.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=GrantInstanceToCbn&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|GrantInstanceToCbn|The operation that you want to perform.

 Set the value to **GrantInstanceToCbn**. |
|CcnInstanceId|String|Yes|ccn-n2935s1mnwv8i\*\*\*\*\*|The ID of the CCN instance. |
|CenInstanceId|String|Yes|cen-7qthudw0ll6jm\*\*\*\*\*|The ID of the CEN instance. |
|CenUid|Long|Yes|123456789|The user ID \(UID\) of the Alibaba Cloud account to which the Cloud Enter Network \(CEN\) instance belongs. |
|RegionId|String|Yes|cn-shanghai|The ID of the region where the CCN instance is deployed. |
|GrantTrafficService|Boolean|No|true|Specifies whether to grant the CEN instance permissions to manage network traffic from the CCN instance. Valid values:

 -   **true**: grants permissions.
-   **false**: does not grant permissions. This is the default value.

 **Note:** If you set the value to true and the SAG instance connected to the CCN instance has the secure rerouting feature enabled, you cannot revoke the permissions. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|22840034-ADE9-41D8-A5DC-A7CF435CEE75|The ID of the request. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=GrantInstanceToCbn
&CcnInstanceId=ccn-n2935s1mnwv8i*****
&CenInstanceId=cen-7qthudw0ll6jm*****
&CenUid=123456789
&RegionId=cn-shanghai
&<Common request parameters>
```

Sample success responses

`XML` format

```
<GrantInstanceToCbnResponse>
  <RequestId>22840034-ADE9-41D8-A5DC-A7CF435CEE75</RequestId>
</GrantInstanceToCbnResponse>
```

`JSON` format

```
{
	"RequestId": "22840034-ADE9-41D8-A5DC-A7CF435CEE75"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

