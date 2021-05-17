# DescribeSagStaticRouteList

You can call this operation to obtain the information list of a static route.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=DescribeSagStaticRouteList&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|DescribeSagStaticRouteList|The operation that you want to perform.

Set the value to **DescribeSagStaticRouteList**. |
|RegionId|String|Yes|cn-shanghai|The ID of the region where the Smart Access Gateway \(SAG\) instance is deployed. |
|SmartAGId|String|Yes|sag-whfn\*\*\*\*|The ID of the SAG instance. |
|SmartAGSn|String|Yes|sag32a30\*\*\*\*|The serial number of the SAG device associated with the SAG instance. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|CE6642D4-21EB-4168-9BF9-F217953F9892|The ID of the request. |
|StaticRoutes|Array| |The information list of the static route. |
|DestinationCidr|String|192.XX.XX.0/24|The destination CIDR block. |
|NextHop|String|192.XX.XX.1|The IP address of the next hop. |
|PortName|String|0|The name of the port. |
|Vlan|String|1|The VLAN ID. |
|TaskStates|Array| |The state of the query task. |
|CreateTime|String|1586857309000|The time when the query task was created. |
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
http(s)://smartag.cn-shanghai.aliyuncs.com/? Action=DescribeSagStaticRouteList
&RegionId=cn-shanghai
&SmartAGId=sag-whfn****
&SmartAGSn=sag32a30****
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeSagStaticRouteListResponse>
  <RequestId>4C6825DA-AF71-48A5-A2A2-AE3E38ABC899</RequestId>
  <StaticRoutes>
        <NextHop>2.XX.XX.2</NextHop>
        <Vlan>0</Vlan>
        <PortName>5</PortName>
        <DestinationCidr>1.XX.XX.1/32</DestinationCidr>
  </StaticRoutes>
  <TaskStates>
        <State>Succeed</State>
        <CreateTime>1586857309000</CreateTime>
        <ErrorCode>200</ErrorCode>
        <ErrorMessage>Successful</ErrorMessage>
  </TaskStates>
</DescribeSagStaticRouteListResponse>
```

`JSON` format

```
{
    "RequestId": "4C6825DA-AF71-48A5-A2A2-AE3E38ABC899",
    "StaticRoutes": [
        {
            "NextHop": "2.XX.XX.2",
            "Vlan": "0",
            "PortName": "5",
            "DestinationCidr": "1.XX.XX.1/32"
        }
    ],
    "TaskStates": [
        {
            "State": "Succeed",
            "CreateTime": 1586857309000,
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

