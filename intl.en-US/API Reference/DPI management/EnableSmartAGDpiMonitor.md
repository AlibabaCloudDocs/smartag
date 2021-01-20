# EnableSmartAGDpiMonitor

Enables the deep packet inspection \(DPI\)-based monitoring feature for a Smart Access Gateway \(SAG\) instance.

## Prerequisites

-   The DPI feature is enabled for the SAG instance. For more information, see [UpdateSmartAGDpiAttribute](~~196146~~).
-   Log Service is activated. For more information, see [Quick Start](~~54604~~).

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=EnableSmartAGDpiMonitor&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|EnableSmartAGDpiMonitor|The operation that you want to perform.

 Set the value to **EnableSmartAGDpiMonitor**. |
|RegionId|String|Yes|cn-shanghai|The ID of the region where the SAG instance is deployed. |
|SlsLogStore|String|Yes|test2|The name of the Logstore. |
|SlsProjectName|String|Yes|test1|The name of the Log Service project. |
|SmartAGId|String|Yes|sag-vwmylqc9521p5l\*\*\*\*|The ID of the SAG instance. |
|ClientToken|String|No|02fb3da4-130e-11e9\*\*\*\*|The client token that is used to ensure the idempotence of the request.

 You can use the client to generate the value, but you must ensure that it is unique among different requests. The token can contain only ASCII characters and cannot exceed 64 characters in length. |
|DryRun|Boolean|No|true|Specifies whether to check the validity of the request without actually making the request. Valid values:

 -   **true**: checks the validity of the request but does not enable or disables the DPI feature for the SAG instance. Check items include the request format, instance status, and whether the required parameters are set. If the request fails the check, an error message is returned. If the request passes the request, the ID of the request is returned.
-   **false**: makes the request and enables the DPI feature for the SAG instance after the request passes the check. This is the default value. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|64966488-B3E3-41E2-9570-4596117EC12E|The ID of the request. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=EnableSmartAGDpiMonitor
&RegionId=cn-shanghai
&SlsLogStore=test2
&SlsProjectName=test1
&SmartAGId=sag-vwmylqc9521p5l****
&<Common request parameters>
```

Sample success responses

`XML` format

```
<EnableSmartAGDpiMonitorResponse>
  <RequestId>64966488-B3E3-41E2-9570-4596117EC12E</RequestId>
</EnableSmartAGDpiMonitorResponse>
```

`JSON` format

```
{"RequestId":"64966488-B3E3-41E2-9570-4596117EC12E"}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|InvalidSmartAGId.NotFound|The specified SmartAGId does not exist.|The error message returned because the specified SAG instance ID does not exist.|
|403|FeatureNotSupport|The current edition of the smart access gateway does not support this feature.|The error message returned because the current version of the specified SAG instance does not support this feature.|
|403|FeatureNotSupportForActiveSmartAG|The current edition of the active smart access gateway does not support this feature.|The error code returned because the current version of the active SAG device does not support this feature.|
|403|FeatureNotSupportForStandBySmartAG|The current edition of the standby smart access gateway does not support this feature.|The error code returned because the current version of the standby SAG device does not support this feature.|
|400|CreateProjectFailed|Failed to create the SLS project.|The error message returned because the Log Service project failed to be created.|
|400|IncorrectStatus|The instance status is invalid.|The error message returned because the SAG instance is in an invalid state.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

