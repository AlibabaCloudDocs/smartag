# RevokeInstanceFromCbn

You can call this operation to revoke the authorization of a Cloud Enterprise Network \(CEN\) instance to a Cloud Connect Network \(CCN\) instance.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=RevokeInstanceFromCbn&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|CcnInstanceId|String|Yes|ccn-n2935s1mnwv8i\*\*\*\*\*|The ID of the CCN instance. |
|CenInstanceId|String|Yes|cen-7qthudw0ll6jm\*\*\*\*\*|The ID of the CEN instance. |
|RegionId|String|Yes|cn-shanghai|The ID of the region where the CCN instance is deployed. |
|Action|String|No|RevokeInstanceFromCbn|The operation that you want to perform. Set the value to **RevokeInstanceFromCbn**. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|07D73949-2508-4169-8C64-7CCDB33871C4|The ID of the request. |

## Examples

Sample requests

```

http(s)://[Endpoint]/? Action=RevokeInstanceFromCbn
&CcnInstanceId=ccn-n2935s1mnwv8i*****
&CenInstanceId=cen-7qthudw0ll6jm*****
&RegionId=cn-shanghai
&<Common request parameters>

```

Sample success responses

`XML` format

```
<RevokeInstanceFromCbnResponse>
	  <RequestId>07D73949-2508-4169-8C64-7CCDB33871C4</RequestId>
</RevokeInstanceFromCbnResponse>
```

`JSON` format

```
{
	"RequestId":"07D73949-2508-4169-8C64-7CCDB33871C4"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

