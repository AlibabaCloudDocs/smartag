# GetSmartAGDpiAttribute

Queries the settings of the deep packet inspection \(DPI\) feature for a Smart Access Gateway \(SAG\) instance.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=GetSmartAGDpiAttribute&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|GetSmartAGDpiAttribute|The operation that you want to perform.

 Set the value to **GetSmartAGDpiAttribute**. |
|RegionId|String|Yes|cn-shanghai|The ID of the region where the SAG instance is deployed. |
|SmartAGId|String|Yes|sag-tq3sazs17smldn\*\*\*\*|The ID of the SAG instance. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|DpiMonitorStatus|String|Inactive|The status of the DPI-based monitoring feature. Valid values:

 -   **Active**: enabled
-   **Inactive**: disabled |
|DpiStatus|String|On|The status of the DPI feature. Valid values:

 -   **On**: enabled
-   **Off**: disabled |
|LogstoreName|String|test1|The name of the Log Service Logstore that is associated with the DPI feature. |
|ProjectName|String|test2|The name of the Log Service project that is associated with the DPI feature. |
|RequestId|String|B2997DC4-F1A2-418B-81FC-C8892CD31CFF|The ID of the request. |
|SlsRegion|String|cn-shanghai|The region where Log Service is deployed. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=GetSmartAGDpiAttribute
&RegionId=cn-shanghai
&SmartAGId=sag-tq3sazs17smldn****
&<Common request parameters>
```

Sample success responses

`XML` format

```
<GetSmartAGDpiAttributeResponse>
  <RequestId>B2997DC4-F1A2-418B-81FC-C8892CD31CFF</RequestId>
  <SlsRegion>cn-shanghai</SlsRegion>
  <DpiMonitorStatus>Inactive</DpiMonitorStatus>
  <DpiStatus>On</DpiStatus>
</GetSmartAGDpiAttributeResponse>
```

`JSON` format

```
{
	"RequestId": "B2997DC4-F1A2-418B-81FC-C8892CD31CFF",
	"SlsRegion": "cn-shanghai",
	"DpiMonitorStatus": "Inactive",
	"DpiStatus": "On"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

