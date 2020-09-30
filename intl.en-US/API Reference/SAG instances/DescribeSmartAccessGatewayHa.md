# DescribeSmartAccessGatewayHa

You can call this operation to query the high availability \(HA\) settings of Smart Access Gateway \(SAG\) instance.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=DescribeSmartAccessGatewayHa&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|DescribeSmartAccessGatewayHa|Set the value to **DescribeSmartAccessGatewayHa**. |
|RegionId|String|Yes|cn-shanghai|The ID of the region where the SAG instance is deployed. |
|SmartAGId|String|Yes|sag-pno62188piyc6txxxxx|The ID of the SAG instance. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|582FE511-FEFE-42BC-BBF4-4F8ECF92Exxx|The ID of the request. |
|DeviceLevelBackupState|String|OFF|Indicates whether device-based HA is enabled. Valid values:

 -   **ON**: enabled
-   **OFF**: disabled |
|DeviceLevelBackupType|String|cold\_backup|The deployment mode of the SAG devices that have HA enabled. Valid values:

 -   **warm\_backup**: active-active mode
-   **cold\_backup**: active-standby mode
-   **no\_backup**: standalone mode |
|MainDeviceId|String|sag11axxxx|The serial number \(SN\) of the active SAG device. |
|BackupDeviceId|String|sag11axxxx|The SN of the standby SAG device. |
|SmartAGId|String|sag-i8mogwi9kisigc3xxxx|The ID of the SAG instance. |
|LinkBackupInfoList|Array| |The information about standby connections. |
|LinkLevelBackupState|String|ON|Indicates whether HA is enabled to provide standby connections. Valid values:

 -   **ON**: enabled
-   **OFF**: disabled |
|LinkLevelBackupType|String|StandbyMode|The HA mode. Valid values:

 -   **DedicatedLineBackupMode**: leased line and SAG.
-   **StandbyMode**: active and standby WAN ports.
-   **Off**: HA is disabled. |
|MainLinkId|String|lte|The ID of the active connection. |
|MainLinkState|String|up|The status of the active connection. Valid values:

 -   **up**: available
-   **down**: unavailable |
|BackupLinkId|String|wan1|The ID of the standby connection. |
|BackupLinkState|String|down|The status of the standby connection. Valid values:

 -   **up**: available
-   **down**: unavailable |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=DescribeSmartAccessGatewayHa
&RegionId=cn-hangzhou
&SmartAGId=sag-pno62188piyc6txxxxx
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeSmartAccessGatewayHaResponse>
	  <SmartAGId>sag-i8mogwi9kisigcxxxx</SmartAGId>
	  <DeviceLevelBackupState>OFF</DeviceLevelBackupState>
	  <LinkBackupInfoList>
		    <LinkBackupInfoList>
			      <LinkLevelBackupType>StandbyMode</LinkLevelBackupType>
			      <MainLinkId>lte</MainLinkId>
			      <BackupLinkState>down</BackupLinkState>
			      <LinkLevelBackupState>ON</LinkLevelBackupState>
			      <BackupLinkId>wan1</BackupLinkId>
			      <MainLinkState>up</MainLinkState>
		    </LinkBackupInfoList>
	  </LinkBackupInfoList>
	  <RequestId>582FE511-FEFE-42BC-BBF4-4F8ECF92E3C6</RequestId>
</DescribeSmartAccessGatewayHaResponse>
```

`JSON` format

```
{
	"SmartAGId": "sag-i8mogwi9kisigcxxxx",
	"DeviceLevelBackupState": "OFF",
	"LinkBackupInfoList": {
		"LinkBackupInfoList": [
			{
				"LinkLevelBackupType": "StandbyMode",
				"MainLinkId": "lte",
				"BackupLinkState": "down",
				"LinkLevelBackupState": "ON",
				"BackupLinkId": "wan1",
				"MainLinkState": "up"
			}
		]
	},
	"RequestId": "582FE511-FEFE-42BC-BBF4-4F8ECF92E3C6"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

