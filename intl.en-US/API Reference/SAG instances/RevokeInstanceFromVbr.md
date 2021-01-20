# RevokeInstanceFromVbr

Revokes permissions from a virtual border router \(VBR\) under another account.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=RevokeInstanceFromVbr&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|RevokeInstanceFromVbr|The operation that you want to perform.

 Set the value to **RevokeInstanceFromVbr**. |
|RegionId|String|Yes|cn-shanghai|The ID of the region where the SAG instance is deployed. |
|SmartAGId|String|Yes|sag-0nnteglltw6z4b\*\*\*\*|The ID of the SAG instance. |
|VbrInstanceId|String|Yes|vbr-bp13gtbhdp0pfqg6s\*\*\*\*|The ID of the VBR. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|D085AE49-51DC-4E8A-9F06-2D99C4E374F7|The ID of the request. |

## Examples

Sample request

```
http(s)://[Endpoint]/? Action=RevokeInstanceFromVbr
&RegionId=cn-shanghai
&SmartAGId=sag-0nnteglltw6z4b****
&VbrInstanceId=vbr-bp13gtbhdp0pfqg6s****
&<Common request parameters>
```

Sample success responses

`XML` format

```
<RevokeInstanceFromVbrResponse>
  <RequestId>D085AE49-51DC-4E8A-9F06-2D99C4E374F7</RequestId>
</RevokeInstanceFromVbrResponse>
```

`JSON` format

```
{
	"RequestId": "D085AE49-51DC-4E8A-9F06-2D99C4E374F7"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

