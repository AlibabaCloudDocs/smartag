# GetCloudConnectNetworkUseLimit

You can call this operation to query the maximum number of Cloud Connect Network \(CCN\) instances that the current account can create in the specified region.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=GetCloudConnectNetworkUseLimit&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|RegionId|String|Yes|cn-hangzhou|The ID of the region where the CCN instances are deployed. |
|Action|String|No|GetCloudConnectNetworkUseLimit|The operation that you want to perform.

 Set the value to **GetCloudConnectNetworkUseLimit**. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|BCD04867-56C3-43DC-8FEF-923EFB8B56DA|The ID of the request. |
|TotalAmount|Integer|10|The maximum number of CCN instances that the current account can create in the specified region. |
|UsedAmount|Integer|6|The number of CCN instances that you have created. |

## Examples

Sample requests

```

https://smartag.cn-shanghai.aliyuncs.com/?Action=GetCloudConnectNetworkUseLimit
&RegionId=cn-shanghai
&CommonParameters

```

Sample success responses

`XML` format

```
<GetCloudConnectNetworkUseLimitResponse>
    <RequestId>BCD04867-56C3-43DC-8FEF-923EFB8B56DA</RequestId>
    <TotalAmount>10</TotalAmount>
    <UsedAmount>6</UsedAmount>
</GetCloudConnectNetworkUseLimitResponse>
```

`JSON` format

```
{
	"RequestId":"BCD04867-56C3-43DC-8FEF-923EFB8B56DA",
	"TotalAmount":10,
	"UsedAmount":6
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|403|Forbidden|User not authorized to operate on the specified resource.|The error message returned because you do not have the permission to manage the resource.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

