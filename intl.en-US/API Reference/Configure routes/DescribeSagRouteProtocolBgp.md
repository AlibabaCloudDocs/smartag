# DescribeSagRouteProtocolBgp

You can call this operation to query the configurations of Border Gateway Protocol \(BGP\) dynamic routing.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=DescribeSagRouteProtocolBgp&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|DescribeSagRouteProtocolBgp|The operation that you want to perform.

Set the value to **DescribeSagRouteProtocolBgp**. |
|RegionId|String|Yes|cn-shanghai|The ID of the region where the Smart Access Gateway \(SAG\) instance is deployed. |
|SmartAGId|String|Yes|sag-whfn\*\*\*\*|The ID of the SAG instance. |
|SmartAGSn|String|Yes|sag32a30\*\*\*\*|The serial number of the SAG device associated with the SAG instance. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|HoldTime|Integer|9|The hold time of BGP connections. |
|KeepAlive|Integer|3|The time interval at which keep-alive packets are transmitted. |
|LocalAs|Integer|12345|The autonomous system \(AS\) number to which the SAG device belongs. |
|RequestId|String|2F39E4FE-B45C-47FF-9921-95780486F52D|The ID of the request. |
|RouterId|String|192.XX.XX.1|The ID of the router that has BGP enabled. |
|TaskStates|Array| |The state of the query task. |
|CreateTime|String|1586765938000|The time when the query task was created. |
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
http(s)://smartag.cn-shanghai.aliyuncs.com/? Action=DescribeSagRouteProtocolBgp
&RegionId=cn-shanghai
&SmartAGId=sag-whfn****
&SmartAGSn=sag32a30****
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeSagRouteProtocolBgpResponse>
  <HoldTime>9</HoldTime>
  <RequestId>EF0FDC88-1C6F-4AB7-B5DF-7277D360726F</RequestId>
  <KeepAlive>3</KeepAlive>
  <RouterId>1.XX.XX.1</RouterId>
  <LocalAs>25</LocalAs>
  <TaskStates>
        <State>Succeed</State>
        <CreateTime>1586765938000</CreateTime>
        <ErrorCode>200</ErrorCode>
        <ErrorMessage>Successful</ErrorMessage>
  </TaskStates>
</DescribeSagRouteProtocolBgpResponse>
```

`JSON` format

```
{
    "HoldTime": 9,
    "RequestId": "EF0FDC88-1C6F-4AB7-B5DF-7277D360726F",
    "KeepAlive": 3,
    "RouterId": "1.XX.XX.1",
    "LocalAs": 25,
    "TaskStates": [
        {
            "State": "Succeed",
            "CreateTime": 1586765938000,
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

