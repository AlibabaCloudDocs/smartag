# UpdateSmartAGDpiAttribute

Enables or disables the deep packet inspection \(DPI\) feature for a Smart Access Gateway \(SAG\) instance.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=UpdateSmartAGDpiAttribute&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|UpdateSmartAGDpiAttribute|The operation that you want to perform.

Set the value to **UpdateSmartAGDpiAttribute**. |
|DpiEnabled|Boolean|Yes|true|Specifies whether to enable the DPI feature for the SAG instance. Valid values:

-   **true**: enables DPI
-   **false**: disables DPI |
|RegionId|String|Yes|cn-shanghai|The ID of the region where the SAG instance is deployed. |
|SmartAGId|String|Yes|sag-tq3sazs17smldn\*\*\*\*|The ID of the SAG instance. |
|ClientToken|String|No|02fb3da4-130e\*\*\*\*|The client token that is used to ensure the idempotence of the request.

You can use the client to generate the value, but you must ensure that it is unique among different requests. The token can contain only ASCII characters and cannot exceed 64 characters in length. |
|DryRun|Boolean|No|false|Specifies whether to check the validity of the request without actually making the request. Valid values:

-   **true**: checks the validity of the request but does not enable or disable the DPI feature. Check items include the request format, instance status, and whether the required parameters are set. If the request fails the check, an error message is returned. If the request passes the check, the ID of the request is returned.
-   **false**: makes the request and enables or disables the DPI feature after the request passes the check. This is the default value. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|0C2EE7A8-74D4-4081-8236-CEBDE3BBCF50|The ID of the request. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=UpdateSmartAGDpiAttribute
&DpiEnabled=true
&RegionId=cn-shanghai
&SmartAGId=sag-tq3sazs17smldn****
&<Common request parameters>
```

Sample success responses

`XML` format

```
<UpdateSmartAGDpiAttributeResponse>
  <RequestId>0C2EE7A8-74D4-4081-8236-CEBDE3BBCF50</RequestId>
</UpdateSmartAGDpiAttributeResponse>
```

`JSON` format

```
{"RequestId":"0C2EE7A8-74D4-4081-8236-CEBDE3BBCF50"}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|InvalidSmartAGId.NotFound|The specified SmartAGId does not exist.|The error message returned because the specified SAG instance ID does not exist.|
|403|FeatureNotSupport|The current edition of the smart access gateway does not support this feature.|The error message returned because the current version of the specified SAG instance does not support this feature.|
|403|FeatureNotSupportForActiveSmartAG|The current edition of the active smart access gateway does not support this feature.|The error message returned because the current version of the active SAG device does not support this feature.|
|403|FeatureNotSupportForStandBySmartAG|The current edition of the standby smart access gateway does not support this feature.|The error code returned because the current version of the standby SAG device does not support this feature.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

