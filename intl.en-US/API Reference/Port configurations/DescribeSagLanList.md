# DescribeSagLanList

You can call this operation to query the LAN port configurations of a Smart Access Gateway \(SAG\) device.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=DescribeSagLanList&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|DescribeSagLanList|The operation that you want to perform.

Set the value to **DescribeSagLanList**. |
|RegionId|String|Yes|cn-shanghai|The ID of the region where the SAG instance is deployed. |
|SmartAGId|String|Yes|sag-whfn\*\*\*\*|The ID of the SAG instance. |
|SmartAGSn|String|Yes|sag32a30\*\*\*\*|The serial number of the SAG device associated with the SAG instance. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Lans|Array| |The information list of the LAN port. |
|EndIp|String|192.XX.XX.254|The last IP address of the Dynamic Host Configuration Protocol \(DHCP\) pool. |
|IP|String|192.XX.XX.1|The IP address of the LAN port. |
|IPType|String|DHCP|The connection type of the LAN port.

**DHCP**: a dynamic IP address. Uses DHCP to dynamically assign an IP address to a connected device.

**STATIC**: a static IP address. Specifies a static IP address for the LAN port. |
|Lease|String|7|The time duration that the IP address is retained after it is assigned through DHCP. Unit: minute. |
|Mask|String|255.255.255.0|The subnet mask of the LAN port IP address. |
|PortName|String|0|The name of the LAN port. |
|StartIp|String|192.XX.XX.2|The first IP address of the DHCP pool. |
|RequestId|String|1120228A-E5E1-4E9C-B56D-96887E1A2B2F|The ID of the request. |
|TaskStates|Array| |The state of the query task. |
|CreateTime|String|1586852928000|The time when the query task was created. |
|ErrorCode|String|200|The error code. 200 indicates that the query task is successful. |
|ErrorMessage|String|Successful|The error message. Successful indicates that the query task is successful. |
|State|String|Succeed|The asynchronous task status. Valid values:

-   **Initialized**: The query task is initialized.
-   **Offline**: The SAG device is disconnected from Alibaba Cloud and Alibaba Cloud has not assigned the query task to the SAG device. When the SAG device is connected to Alibaba Cloud, Alibaba Cloud continues to assign the query task to the SAG device.
-   **Succeed**: Alibaba Cloud has assigned the query task to the SAG device.
-   **Processing**: Alibaba Cloud is assigning the query task to the SAG device.
-   **VersionNotSupport**: not supported by the current version of the SAG device.
-   **BuildRequestError**: not supported by the control and management center in the cloud.
-   **HardwareError**: Alibaba Cloud failed to assign the query task to the SAG device because the SAG device is faulty.
-   **TaskNotExist**: The query task does not exist.
-   **OfflineNotConfiged**: The SAG device is disconnected from Alibaba Cloud and Alibaba Cloud has not assigned the query task to the SAG device. When the SAG device is connected to Alibaba Cloud, Alibaba Cloud does not assign the query task to the SAG device. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=DescribeSagLanList
&RegionId=cn-shanghai
&SmartAGId=sag-whfn****
&SmartAGSn=sag32a30****
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeSagLanListResponse>
  <RequestId>ADDEF8CA-D96F-4002-812A-36FDF4114135</RequestId>
  <TaskStates>
        <State>Succeed</State>
        <CreateTime>1586869664000</CreateTime>
        <ErrorCode>200</ErrorCode>
        <ErrorMessage>Successful. </ErrorMessage>
  </TaskStates>
  <Lans>
        <IPType>STATIC</IPType>
        <IP>192.XX.XX.1</IP>
        <Mask>255.255.255.0</Mask>
        <PortName>0</PortName>
  </Lans>
  <Lans>
        <IPType>STATIC</IPType>
        <IP>172.XX.XX.10</IP>
        <Mask>255.255.255.0</Mask>
        <PortName>4</PortName>
  </Lans>
</DescribeSagLanListResponse>
```

`JSON` format

```
{
    "RequestId": "ADDEF8CA-D96F-4002-812A-36FDF4114135",
    "TaskStates": [
        {
            "State": "Succeed",
            "CreateTime": 1586869664000,
            "ErrorCode": "200",
            "ErrorMessage": "Successful"
        }
    ],
    "Lans": [
        {
            "IPType": "STATIC",
            "IP": "192.XX.XX.1",
            "Mask": "255.255.255.0",
            "PortName": "0"
        },
        {
            "IPType": "STATIC",
            "IP": "172.XX.XX.10",
            "Mask": "255.255.255.0",
            "PortName": "4"
        }
    ]
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|SAG.InstanceNoFound|The specified SAG instance does not exist.|The specified SAG instance does not exist.|
|400|SAG.SoftwareNotSupport|The specified SAG software edition instance does not support ACL.|The SAG APP instance does not support access control lists \(ACLs\).|
|500|SmartAccessGatewayInArrears|The specified Smart Access Gateway has expired.|The specified SAG instance has expired and stops running. Renew the SAG instance.|
|500|SmartAccessGatewayNotActivated|The specified Smart Access Gateway has not been activated.|The specified SAG instance is not activated. Activate the SAG instance.|
|403|SmartAccessGatewayNotOnline|The specified smart access gateway is not online.|The system failed to process the request because the specified SAG device is not connected to Alibaba Cloud.|
|500|SmartAccessGatewayOffline|The request cannot be completed. The Smart Access Gateway is offline.|The system failed to process the request because the specified SAG device is not connected to Alibaba Cloud.|
|400|InstanceNotExit|The specified instance does not exist.|The specified SAG instance does not exist.|
|400|ConfigUnsynchronized|The network configuration is not synchronized.|The network configurations are not synchronized.|
|403|FeatureNotSupport|The current edition of the smart access gateway does not support this feature.|The current version of the SAG device does not support this feature.|
|403|FeatureNotSupportForActiveSmartAG|The current edition of the active smart access gateway does not support this feature.|The current version of the active SAG device does not support this feature.|
|403|FeatureNotSupportForStandBySmartAG|The current edition of the standby smart access gateway does not support this feature.|The current version of the standby SAG device does not support this feature.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

