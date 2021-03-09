# UpdateSmartAccessGatewayVersion

Upgrades an SAG instance to a later version.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=UpdateSmartAccessGatewayVersion&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|UpdateSmartAccessGatewayVersion|The operation that you want to perform.

 Set the value to **UpdateSmartAccessGatewayVersion**. |
|RegionId|String|Yes|cn-hangzhou|The ID of the region where the SAG instance is deployed. |
|SmartAGId|String|Yes|sag-0ovhf732a9j\*\*\*\*\*\*\*|The ID of the SAG instance. |
|VersionCode|String|Yes|1.0.1|The version to which you want to upgrade the SAG instance. |
|SerialNumber|String|No|sag233\*\*\*\*|The serial number of the SAG device. |
|VersionType|String|No|Device|The type of software that you want to upgrade. Valid values:

 -   **Device**: The operating system run by the SAG device.
-   **Dpi**: The signature database used by the SAG device. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|CE6642D4-21EB-4168-9BF9-F217953F9892|The ID of the request. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=UpdateSmartAccessGatewayVersion
&RegionId=cn-hangzhou
&SmartAGId=sag-0ovhf732a9j*******
&VersionCode=1.0.1
&<Common request parameters>
```

Sample success responses

`XML` format

```
<UpdateSmartAccessGatewayVersionResponse>
  <RequestId>CE6642D4-21EB-4168-9BF9-F217953F9892</RequestId>
</UpdateSmartAccessGatewayVersionResponse>
```

`JSON` format

```
{
   "RequestId":"CE6642D4-21EB-4168-9BF9-F217953F9892"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|403|Forbidden|User not authorized to operate on the specified resource.|The error message returned because you do not have the permissions to manage the specified resource.|
|500|SmartAccessGatewayInArrears|The specified Smart Access Gateway has expired.|The error message returned because the specified SAG instance has expired. Renew the SAG instance first.|
|500|SmartAccessGatewayNotActivated|The specified Smart Access Gateway has not been activated.|The error message returned because the specified SAG instance has not been activated. Activate the SAG instance first.|
|403|InvalidId.SMARTAG|The specified smart access gateway instance id is invalid.|The error message returned because the specified SAG instance ID is invalid.|
|500|PermissionError|No permission to operate the instance.|The error message returned because you do not have the permission to manage the specified instance.|
|403|NotBoundCCN|The specified smart access gateway has not bound CCN; please bind CCN first.|The error message returned because the specified SAG instance is not associated with a Cloud Connect Network \(CCN\) instance. Associate the SAG instance with a CCN instance first.|
|403|SmartAccessGatewayNotOnline|The specified smart access gateway is not online.|The error message returned because the specified SAG device is not connected to Alibaba Cloud and the system failed to process the request.|
|403|GetSmartAccessGatewayVersionError|An error occurred while obtaining the smart access gateway version.|The error message returned because the system failed to query the version of the specified SAG instance.|
|403|GetSmartAccessGatewayStateError|An error occurred while obtaining the smart access gateway status.|The error message returned because the system failed to query the status of the specified SAG instance.|
|403|VersionTooOld|The specified version is outdated; please select a newer version.|The error message returned because the specified version is outdated. Select a later version.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

