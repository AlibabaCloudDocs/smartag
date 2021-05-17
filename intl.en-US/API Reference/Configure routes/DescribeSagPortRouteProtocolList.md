# DescribeSagPortRouteProtocolList

You can call this operation to query a list of the ports that have routing protocols enabled.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=DescribeSagPortRouteProtocolList&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|DescribeSagPortRouteProtocolList|The operation that you want to perform.

Set the value to**DescribeSagPortRouteProtocolList**. |
|RegionId|String|Yes|cn-shanghai|The ID of the region where the Smart Access Gateway \(SAG\) instance is deployed. |
|SmartAGId|String|Yes|sag-whfn\*\*\*\*|The ID of the SAG instance. |
|SmartAGSn|String|Yes|sag32a30\*\*\*\*|The serial number of the SAG device associated with the SAG instance. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Ports|Array| |The information list of the port. |
|NeighborIp|String|192.XX.XX.1|The IP address of the neighbor device. |
|PortName|String|3|The name of the port. |
|RemoteAs|String|12345|The autonomous system \(AS\) number to which the SAG device belongs. |
|RemoteIp|String|192.XX.XX.1|The IP address of the peer device. |
|RouteProtocol|String|BGP|The routing protocal. Valid values:

-   **STATIC**: uses a static routing protocol.
-   **OSPF**: uses the Open Shortest Path First protocol \(OSPF\).
-   **BGP**: uses the Border Gateway Protocol \(BGP\). |
|Status|String|UP|The port state. Valid values:

-   **UP**: The port is enabled.
-   **DOWN**: The port is disabled. |
|Vlan|String|2|The VLAN ID. |
|RequestId|String|CE6642D4-21EB-4168-9BF9-F217953F9892|The ID of the request. |
|TaskStates|Array| |The state of the query task. |
|CreateTime|String|1586843621000|The time when the query task was created. |
|ErrorCode|String|200|The error code. 200 indicates that the query task is successful. |
|ErrorMessage|String|Successful|The error message. Successful indicates that the query task is successful. |
|State|String|Succeed|The state of the query task. Valid values:

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
http(s)://smartag.cn-shanghai.aliyuncs.com/? Action=DescribeSagPortRouteProtocolList
&RegionId=cn-shanghai
&SmartAGId=sag-whfn****
&SmartAGSn=sag32a30****
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeSagPortRouteProtocolListResponse>
  <RequestId>CAA9089E-9C8E-422A-BB87-72A784A8A906</RequestId>
  <Ports>
        <Status>DOWN</Status>
        <RouteProtocol>STATIC</RouteProtocol>
        <PortName>0</PortName>
  </Ports>
  <Ports>
        <Status>UP</Status>
        <RouteProtocol>OSPF</RouteProtocol>
        <PortName>4</PortName>
  </Ports>
  <Ports>
        <Status>DOWN</Status>
        <RouteProtocol>STATIC</RouteProtocol>
        <PortName>5</PortName>
  </Ports>
  <Ports>
        <RemoteAs></RemoteAs>
        <Status>DOWN</Status>
        <RouteProtocol>STATIC</RouteProtocol>
        <RemoteIp></RemoteIp>
        <Vlan>0</Vlan>
        <PortName>3</PortName>
  </Ports>
  <TaskStates>
        <State>Succeed</State>
        <CreateTime>1586843621000</CreateTime>
        <ErrorCode>200</ErrorCode>
        <ErrorMessage>Successful</ErrorMessage>
  </TaskStates>
</DescribeSagPortRouteProtocolListResponse>
```

`JSON` format

```
{
    "RequestId": "CAA9089E-9C8E-422A-BB87-72A784A8A906",
    "Ports": [
        {
            "Status": "DOWN",
            "RouteProtocol": "STATIC",
            "PortName": "0"
        },
        {
            "Status": "UP",
            "RouteProtocol": "OSPF",
            "PortName": "4"
        },
        {
            "Status": "DOWN",
            "RouteProtocol": "STATIC",
            "PortName": "5"
        },
        {
            "RemoteAs": "",
            "Status": "DOWN",
            "RouteProtocol": "STATIC",
            "RemoteIp": "",
            "Vlan": "0",
            "PortName": "3"
        }
    ],
    "TaskStates": [
        {
            "State": "Succeed",
            "CreateTime": 1586843621000,
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

