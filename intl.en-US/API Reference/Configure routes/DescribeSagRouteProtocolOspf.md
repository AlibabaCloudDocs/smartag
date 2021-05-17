# DescribeSagRouteProtocolOspf

You can call this operation to query the Open Shortest Path First \(OSPF\) configurations.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=DescribeSagRouteProtocolOspf&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|DescribeSagRouteProtocolOspf|The operation that you want to perform.

Set the value to **DescribeSagRouteProtocolOspf**. |
|RegionId|String|Yes|cn-shanghai|The ID of the region where the Smart Access Gateway \(SAG\) instance is deployed. |
|SmartAGId|String|Yes|sag-whfn\*\*\*\*|The ID of the SAG instance. |
|SmartAGSn|String|Yes|sag32a30\*\*\*\*|The serial number of the SAG device associated with the SAG instance. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|AreaId|String|10|The ID of the OSPF area. |
|AreaType|String|NSSA|The type of the OSPF area.

**Note:** Only the NSSA area type is supported. |
|AuthenticationType|String|MD5|The authentication type. Valid values:

-   **NONE**: disables authentication.
-   **CLEARTEXT**: enables plaintext authentication.
-   **MD5**: uses MD5 authentication. |
|DeadTime|Integer|40|The timeout period of connections between OSPF peers. |
|HelloTime|Integer|10|The time interval at which Hello packets are sent. |
|Md5Key|String|123\*\*\*\*|The MD5 key value. |
|Md5KeyId|Integer|1|The ID of the MD5 key. |
|RequestId|String|60F9B653-25B7-4511-A3C7-BCBAF462393E|The ID of the request. |
|RouterId|String|1.XX.XX.1|The ID of the router that has OSPF enabled. |
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
http(s)://smartag.cn-shanghai.aliyuncs.com/? Action=DescribeSagRouteProtocolOspf
&RegionId=cn-shanghai
&SmartAGId=sag-whfn****
&SmartAGSn=sag32a30****
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeSagRouteProtocolOspfResponse>
  <RequestId>60F9B653-25B7-4511-A3C7-BCBAF462393E</RequestId>
  <DeadTime>40</DeadTime>
  <Md5KeyId>1</Md5KeyId>
  <AreaId>10</AreaId>
  <RouterId>1.XX.XX.1</RouterId>
  <HelloTime>10</HelloTime>
  <AreaType></AreaType>
  <TaskStates>
        <State>Succeed</State>
        <CreateTime>1586768763000</CreateTime>
        <ErrorCode>200</ErrorCode>
        <ErrorMessage>Successful</ErrorMessage>
  </TaskStates>
  <Md5Key>123****</Md5Key>
  <AuthenticationType>MD5</AuthenticationType>
</DescribeSagRouteProtocolOspfResponse>
```

`JSON` format

```
{
    "RequestId": "60F9B653-25B7-4511-A3C7-BCBAF462393E",
    "DeadTime": 40,
    "Md5KeyId": 1,
    "AreaId": 10,
    "RouterId": "1.XX.XX.1",
    "HelloTime": 10,
    "AreaType": "",
    "TaskStates": [
        {
            "State": "Succeed",
            "CreateTime": 1586768763000,
            "ErrorCode": 200,
            "ErrorMessage": "Successful"
        }
    ],
    "Md5Key": "123****",
    "AuthenticationType": "MD5"
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

