# DescribeSagWanList

Queries the WAN port settings of a Smart Access Gateway \(SAG\) device.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=DescribeSagWanList&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|DescribeSagWanList|The operation that you want to perform.

 Set the value to **DescribeSagWanList**. |
|RegionId|String|Yes|cn-shanghai|The ID of the region where the SAG instance is deployed. |
|SmartAGId|String|Yes|sag-whfn\*\*\*\*|The ID of the SAG instance. |
|SmartAGSn|String|Yes|sag32a30\*\*\*\*|The serial number \(SN\) of the SAG device. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|CE6642D4-21EB-4168-9BF9-F217953F9892|The ID of the request. |
|TaskStates|Array of TaskState| |The status of and information about the query task. |
|CreateTime|String|1586834861000|The time when the query task was created. |
|ErrorCode|String|200|The error code returned to the query task. A value of 200 indicates that the query task is successful. |
|ErrorMessage|String|Successful|The error message returned to the query task. A value of Successful indicates that the query task is successful. |
|State|String|Succeed|The status of the query task. Valid values:

 -   **Initialized**: The query task is initialized.
-   **Offline**: The SAG device is disconnected from Alibaba Cloud and Alibaba Cloud has not assigned the query task to the SAG device. After the SAG device is connected to Alibaba Cloud, Alibaba Cloud assigns the query task to the SAG device.
-   **Succeed**: Alibaba Cloud has assigned the query task to the SAG device.
-   **Processing**: Alibaba Cloud is assigning the query task to the SAG device.
-   **VersionNotSupport**: The query task is not supported by the current version of the SAG device.
-   **BuildRequestError**: The query task is not supported by the controller of the SAG device.
-   **HardwareError**: Alibaba Cloud failed to assign the query task to the SAG device because the SAG device is faulty.
-   **TaskNotExist**: The query task does not exist.
-   **OfflineNotConfiged**: The SAG device is disconnected from Alibaba Cloud and Alibaba Cloud has not assigned the query task to the SAG device. Alibaba Cloud does not assign the query task to the SAG device even after the SAG device is connected to Alibaba Cloud. |
|Wans|Array of Wan| |The settings of the WAN port. |
|BandWidth|Integer|50|The bandwidth cap of the WAN port. Unit: Mbit/s. |
|Gateway|String|192.XX.XX.1|The IP address of the gateway. |
|IP|String|172.XX.XX.1|The IP address of the WAN port. |
|IPType|String|STATIC|The connection type of the WAN port. Valid values:

 -   **DHCP**: The WAN port connects to the Internet through an IP address that is dynamically assigned by the Dynamic Host Configuration Protocol \(DHCP\) server.
-   **STATIC**: The WAN port connects to the Internet through a static IP address.
-   **PPPOE**: The WAN port connects to the Internet through dial-up connections. |
|ISP|String|CT|The Internet service provider \(ISP\) that is used by the WAN port. Valid values:

 -   **CT**: China Telecom
-   **CM**: China Mobile
-   **CU**: China Unicom
-   **Other**: Other ISPs |
|Mask|String|255.255.255.240|The subnet mask of the WAN port IP address. |
|PortName|String|1|The number of the WAN port. |
|Priority|Integer|1|The priority of the WAN port.

 Valid values: **-1** and **1 to 50**. A smaller number represents a higher priority.

 **Note:** A value of **-1** indicates that the WAN port is not used to forward network traffic. |
|TrafficState|String|active|The status of data transfer on the WAN port. Valid values:

 -   **active**: The WAN port is the active port for data transfer.
-   **standby**: The WAN port is a standby port. If the active port is down, data transfer is switched to the WAN port. |
|Username|String|Usernamexx|The username of the PPPoE account. |
|Weight|Integer|100|The weight of the WAN port. |

## Examples

Sample requests

```
http(s)://smartag.cn-shanghai.aliyuncs.com/? Action=DescribeSagWanList
&RegionId=cn-shanghai
&SmartAGId=sag-whfn****
&SmartAGSn=sag32a30****
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeSagWanListResponse>
  <RequestId>D6E2D7AF-6721-462F-B460-D1CE616BC557</RequestId>
  <Wans>
        <IPType>DHCP</IPType>
        <Username></Username>
        <Gateway>172.XX.XX.254</Gateway>
        <Priority>10</Priority>
        <IP>172.XX.XX.43</IP>
        <Mask>255.255.255.0</Mask>
        <PortName>3</PortName>
  </Wans>
  <Wans>
        <IPType>STATIC</IPType>
        <Username></Username>
        <Gateway>10.XX.XX.254</Gateway>
        <Priority>20</Priority>
        <IP>10.XX.XX.200</IP>
        <Mask>255.255.255.0</Mask>
        <PortName>4</PortName>
  </Wans>
</DescribeSagWanListResponse>
```

`JSON` format

```
{
	"RequestId": "D6E2D7AF-6721-462F-B460-D1CE616BC557",
	"Wans": [
		{
			"IPType": "DHCP",
			"Username": "",
			"Gateway": "172.XX.XX.254",
			"Priority": 10,
			"IP": "172.XX.XX.43",
			"Mask": "255.255.255.0",
			"PortName": "3"
		},
		{
			"IPType": "STATIC",
			"Username": "",
			"Gateway": "10.XX.XX.254",
			"Priority": 20,
			"IP": "10.XX.XX.200",
			"Mask": "255.255.255.0",
			"PortName": "4"
		}
	]
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|SAG.InstanceNoFound|The specified SAG instance does not exist.|The error message returned because the specified SAG instance does not exist.|
|400|SAG.SoftwareNotSupport|The specified SAG software edition instance does not support ACL.|The error message returned because the SAG APP instance does not support access control lists \(ACLs\).|
|500|SmartAccessGatewayInArrears|The specified Smart Access Gateway has expired.|The error message returned because the specified SAG instance has expired. Renew the SAG instance first.|
|500|SmartAccessGatewayNotActivated|The specified Smart Access Gateway has not been activated.|The error message returned because the specified SAG instance has not been activated. Activate the SAG instance first.|
|403|SmartAccessGatewayNotOnline|The specified smart access gateway is not online.|The error message returned because the specified SAG device is not connected to Alibaba Cloud and the system failed to process the request.|
|500|SmartAccessGatewayOffline|The request cannot be completed. The Smart Access Gateway is offline.|The error message returned because the specified SAG device is not connected to Alibaba Cloud and the system failed to process the request.|
|400|InstanceNotExit|The specified instance does not exist.|The error message returned because the specified instance does not exist.|
|400|ConfigUnsynchronized|The network configuration is not synchronized.|The error message returned because the network configurations are not synchronized between the SAG instance and the SAG device.|
|403|FeatureNotSupport|The current edition of the smart access gateway does not support this feature.|The error message returned because the current version of the specified SAG instance does not support this feature.|
|403|FeatureNotSupportForActiveSmartAG|The current edition of the active smart access gateway does not support this feature.|The error code returned because the current version of the active SAG device does not support this feature.|
|403|FeatureNotSupportForStandBySmartAG|The current edition of the standby smart access gateway does not support this feature.|The error code returned because the current version of the standby SAG device does not support this feature.|
|400|Sag.PortRoleInvalid|The port role is invalid.|The error message returned because the port role is invalid.|
|400|Sag.PortMgtError|The role of a management port cannot be changed.|The error message returned because the role of the management port cannot be changed.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

