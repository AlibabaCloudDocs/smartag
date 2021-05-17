# DescribeSagPortList

You can call this operation to query the information of a physical port.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=DescribeSagPortList&type=RPC&version=2018-03-13)

## Request parameters

|Name|Type|Required|Example|Description|
|----|----|--------|-------|-----------|
|Action|String|No|DescribeSagPortList|The operation that you want to perform.

Set the value to **DescribeSagPortList**. |
|RegionId|String|Yes|cn-shanghai|The ID of the region where the Smart Access Gateway \(SAG\) instance is deployed. |
|SmartAGId|String|Yes|sag-whfn\*\*\*\*|The ID of the SAG instance. |
|SmartAGSn|String|Yes|sag32a30\*\*\*\*|The serial number of the SAG device associated with the SAG instance. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Ports|Array| |The list of the port information. |
|Mac|String|c4:00:ad:a2:f5:\*\*\*\*|The Mac address of the port. |
|PortName|String|5|The name of the port. |
|Role|String|NONE|Port role:

-   **NONE**: No role is assigned to the port.
-   **WAN**: The port is used as a WAN port. The WAN port supports a Dynamic Host Configuration Protocol \(DHCP\) client, PPPoE, or a static IP address to access the Internet.
-   **LAN**: The port is used as a LAN port. The LAN port supports a DHCP server or a static IP address to connect to a local terminal or switch.
-   **ECC**: The port is used as a leased line port to connect to a leased line.
-   **MGT**: The port is used as the management port. |
|Status|String|Down|Port states:

-   **Up**: The port is enabled.
-   **Down**: The port is disabled.
-   **Unavailable**: The SAG device is disconnected from Alibaba Cloud. |
|RequestId|String|CE6642D4-21EB-4168-9BF9-F217953F9892|The ID of the request. |
|TaskStates|Array| |The state of the query task. |
|CreateTime|String|1586762479000|The time when the query task was created. |
|ErrorCode|String|200|The error code. 200 indicates that the query task is successful. |
|ErrorMessage|String|Successful|The error message. Successful indicates that the query task is successful. |
|State|String|Succeed|Asynchronous task states:

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
http(s)://smartag.cn-shanghai.aliyuncs.com/? Action=DescribeSagPortList
&RegionId=cn-shanghai
&SmartAGId=sag-whfn****
&SmartAGSn=sag32a30****
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeSagPortListResponse>
  <RequestId>4363065D-5F04-49D4-A994-C1DF39C7E241</RequestId>
  <Ports>
        <Role>LAN</Role>
        <Status>Down</Status>
        <PortName>0</PortName>
        <Mac>cc:d3:9d:9e:2d:****</Mac>
  </Ports>
  <Ports>
        <Role>NONE</Role>
        <Status>Down</Status>
        <PortName>1</PortName>
        <Mac>cc:d3:9d:9e:2d:****</Mac>
  </Ports>
  <Ports>
        <Role>MGT</Role>
        <Status>Up</Status>
        <PortName>2</PortName>
        <Mac>cc:d3:9d:9e:2d:****</Mac>
  </Ports>
  <Ports>
        <Role>ECC</Role>
        <Status>Down</Status>
        <PortName>3</PortName>
        <Mac>cc:d3:9d:9e:2d:****</Mac>
  </Ports>
  <Ports>
        <Role>LAN</Role>
        <Status>Up</Status>
        <PortName>4</PortName>
        <Mac>cc:d3:9d:9e:2d:****</Mac>
  </Ports>
  <Ports>
        <Role>WAN</Role>
        <Status>Up</Status>
        <PortName>5</PortName>
        <Mac>cc:d3:9d:9e:2d:****</Mac>
  </Ports>
  <TaskStates>
        <State>Succeed</State>
        <CreateTime>1586762479000</CreateTime>
        <ErrorCode>200</ErrorCode>
        <ErrorMessage>Successful</ErrorMessage>
  </TaskStates>
</DescribeSagPortListResponse>
```

`JSON` format

```
{
    "RequestId": "4363065D-5F04-49D4-A994-C1DF39C7E241",
    "Ports": [
        {
            "Role": "LAN",
            "Status": "Down",
            "PortName": "0",
            "Mac": "cc:d3:9d:9e:2d:****"
        },
        {
            "Role": "NONE",
            "Status": "Down",
            "PortName": "1",
            "Mac": "cc:d3:9d:9e:2d:****"
        },
        {
            "Role": "MGT",
            "Status": "Up",
            "PortName": "2",
            "Mac": "cc:d3:9d:9e:2d:****"
        },
        {
            "Role": "ECC",
            "Status": "Down",
            "PortName": "3",
            "Mac": "cc:d3:9d:9e:2d:****"
        },
        {
            "Role": "LAN",
            "Status": "Up",
            "PortName": "4",
            "Mac": "cc:d3:9d:9e:2d:****"
        },
        {
            "Role": "WAN",
            "Status": "Up",
            "PortName": "5",
            "Mac": "cc:d3:9d:9e:2d:****"
        }
    ],
    "TaskStates": [
        {
            "State": "Succeed",
            "CreateTime": 1586762479000,
            "ErrorCode": "200",
            "ErrorMessage": "Successful"
        }
    ]
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|SAG.InstanceNoFound|The specified SAG instance does not exist.|The specified SAG instance does not exist.|
|400|SAG.SoftwareNotSupport|The specified SAG software edition instance does not support ACL.|The SAG APP instance does not support access control lists \(ACLs\).|
|500|SmartAccessGatewayInArrears|The specified Smart Access Gateway has expired.|The specified SAG instance has expired and stopped running. Renew the SAG instance.|
|500|SmartAccessGatewayNotActivated|The specified Smart Access Gateway has not been activated.|The specified SAG instance is not activated. Activate the SAG instance.|
|403|SmartAccessGatewayNotOnline|The specified smart access gateway is not online.|The system failed to process the request because the specified SAG device is not connected to Alibaba Cloud.|
|500|SmartAccessGatewayOffline|The request cannot be completed. The Smart Access Gateway is offline.|The system failed to process the request because the specified SAG device is not connected to Alibaba Cloud.|
|400|InstanceNotExit|The specified instance does not exist.|The specified SAG instance does not exist.|
|400|ConfigUnsynchronized|The network configuration is not synchronized.|The network configurations are not synchronized.|
|403|FeatureNotSupport|The current edition of the smart access gateway does not support this feature.|The current version of the SAG device does not support this feature.|
|403|FeatureNotSupportForActiveSmartAG|The current edition of the active smart access gateway does not support this feature.|The current version of the active SAG device does not support this feature.|
|403|FeatureNotSupportForStandBySmartAG|The current edition of the standby smart access gateway does not support this feature.|The current version of the standby SAG device does not support this feature.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

