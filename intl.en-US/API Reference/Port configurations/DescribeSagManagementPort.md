# DescribeSagManagementPort

You can call this operation to obtain the management port configurations of a Smart Access Gateway \(SAG\) device.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=DescribeSagManagementPort&type=RPC&version=2018-03-13)

## Request parameters

|Name|Type|Required|Example|Description|
|----|----|--------|-------|-----------|
|Action|String|No|DescribeSagManagementPort|The operation that you want to perform.

Set the value to **DescribeSagManagementPort**. |
|RegionId|String|Yes|cn-hangzhou|The ID of the region where the SAG instance is deployed. |
|SmartAGId|String|Yes|sag-jbauqzw5ildnud\*\*\*\*|The ID of the SAG instance. |
|SmartAGSn|String|Yes|sage62x021922\*\*\*\*|The serial number of the SAG device associated with the SAG instance. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Gateway|String|192.XX.XX.254|The IP address of the management port gateway. |
|IP|String|192.XX.XX.10|The IP address of the management port. |
|Mask|String|255.255.255.0|The subnet mask of the IP address of the management port. |
|TaskStates|Array| |The state of the query task. |
|CreateTime|String|1586759657000|The time when the query task was created. |
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
|RequestId|String|3616AAA9-3A6F-4604-98AF-86753AB7F040|The ID of the request. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=DescribeSagManagementPort
&RegionId=cn-hangzhou
&SmartAGId=sag-jbauqzw5ildnud****
&SmartAGSn=sage62x021922****
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeSagManagementPortResponse>
  <RequestId>3616AAA9-3A6F-4604-98AF-86753AB7F040</RequestId>
  <Gateway>192.XX.XX.254</Gateway>
  <IP>192.XX.XX.10</IP>
  <Mask>255.255.255.0</Mask>
  <TaskStates>
        <State>Succeed</State>
        <CreateTime>1586759657000</CreateTime>
        <ErrorCode>200</ErrorCode>
        <ErrorMessage>Successful</ErrorMessage>
  </TaskStates>
</DescribeSagManagementPortResponse>
```

`JSON` format

```
{
    "RequestId": "3616AAA9-3A6F-4604-98AF-86753AB7F040",
    "Gateway": "192.XX.XX.254",
    "IP": "192.XX.XX.10",
    "Mask": "255.255.255.0",
    "TaskStates": [
        {
            "State": "Succeed",
            "CreateTime": 1586759657000,
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

