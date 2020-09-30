# ModifyCloudConnectNetwork

You can call this operation to modify the configurations of a Cloud Connect Network \(CCN\) instance.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=ModifyCloudConnectNetwork&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|ModifyCloudConnectNetwork|The operation that you want to perform.

 Set the values to **ModifyCloudConnectNetwork**. |
|CcnId|String|Yes|ccn-l9340rlu5ens\*\*\*\*\*|The ID of the CCN instance. |
|RegionId|String|Yes|cn-hangzhou|The ID of the region where the CCN instance is deployed. |
|Name|String|No|The name of the CCN instance|The name of the CCN instance.

 The name must be 2 to 128 characters in length, and can contain digits, periods \(.\), underscores \(\_\), and hyphens \(-\). It must start with a letter or Chinese character, but cannot start with `http://` or `https://`. |
|Description|String|No|CCN description|The description of the CCN instance.

 The description must be 2 to 256 characters in length. It must start with a letter or Chinese character, but cannot start with `http://` or `https://`. |
|CidrBlock|String|No|10.10.10.0/24|The CIDR block of the private network. |
|InterworkingStatus|String|No|enable|Specifies whether to allow the SAG instance associated with the CCN instance to communicate with each other.

 -   **enable**: enables the communication.
-   **disable**: disables the communication. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|0BAAF2B9-88B8-4574-BDBE-102A90EE3FEE|The ID of the request. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=ModifyCloudConnectNetwork
&CcnId=ccn-l9340rlu5ens*****
&RegionId=cn-hangzhou
&<Common request parameters>
```

Sample success responses

`XML` format

```
<ModifyCloudConnectNetworkResponse>
    <RequestId>0BAAF2B9-88B8-4574-BDBE-102A90EE3FEE</RequestId>
</ModifyCloudConnectNetworkResponse>
```

`JSON` format

```
{
   "RequestId":"0BAAF2B9-88B8-4574-BDBE-102A90EE3FEE"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|403|MissingParameter|The input parameter is missing, please check your input.|The error message returned because a request parameter is not set. Check the request parameters.|
|403|InvalidId.CCN|Invalid cloud connect network id.|The error message returned because the specified CCN instance ID is invalid.|
|403|UpdateError.CCN|Update cloud connect network error.|The error message returned because the system failed to update the CCN instance.|
|403|Forbidden|User not authorized to operate on the specified resource.|The error message returned because you do not have the permission to manage the resource.|
|400|CCN.CidrEmpty|You must specify the CCN CIDR block.|The error message returned because the CIDR block of the CCN instance is not specified.|
|400|CCN.CidrAmountLimit|The maximum number of CCN CIDR blocks is exceeded.|The error message returned because the number of CIDR blocks of the CCN instance exceeds the upper limit.|
|400|CCN.CidrInUse|The specified CCN CIDR block is being used.|The error message returned because the specified CIDR block of the CCN instance is already used.|
|400|CCN.InvalidCidr|The specified CCN CIDR block is invalid.|The error message returned because the specified CIDR block of the CCN instance is invalid.|
|400|CCN.InvalidId|You must specify the CCN instance ID.|The error message returned because the specified CCN instance ID does not exist.|
|400|CCN.InvalidSnatCidr|The SNAT CIDR block of CCN is invalid.|The error message returned because the specified SNAT CIDR block of the CCN instance is invalid.|
|400|CCN.SnatCidrConflict|The specified SNAT CIDR block is invalid.|The error message returned because the specified SNAT CIDR block overlaps with another one.|
|400|CCN.SnatCidrInUse|The SNAT CIDR block of the CCN is being used and cannot be changed.|The error message returned because the specified SNAT CIDR block is being used and cannot be modified.|
|400|CCN.SnatCidrNoConfig|You must configure the SNAT CIDR block of the CCN.|The error message returned because the SNAT CIDR block of the CCN instance is not specified.|
|400|SAG.CcnCidrNoConfig|You must configure the CIDR block of CCN.|The error message returned because the CIDR block of the SAG instance associated with the CCN instance is not specified.|
|400|CCN.InvalidInterworkingStatus|The specified connection status is invalid. Specify the connection status to enable or disable.|The error message returned because the specified communication status between the SAG instance and the CCN instance is invalid.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

