# DescribeSagDropTopN

You can call this operation to query the top 10 Smart Access Gateway \(SAG\) instances that have the highest packet loss rates in a specific region.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=DescribeSagDropTopN&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|DescribeSagDropTopN|The operation that you want to perform.

 Set the value to **DescribeSagDropTopN**. |
|RegionId|String|Yes|cn-shanghai|The ID of the region where the SAG instance is deployed. |
|Size|Integer|No|10|The number of SAG instances to be queried. Default value:**10**. This value cannot be modified. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|DropTopN|Array| |The information about packets dropped by the SAG instance. |
|DropRate|String|0.0|The packet loss rate of the SAG instance. Unit: packets per second \(PPS\). |
|InstanceId|String|sag-whfn\*\*\*\*|The ID of the SAG instance. |
|Name|String|test|The name of the SAG instance. |
|RegionId|String|cn-shanghai|The ID of the region where the SAG instance is deployed. |
|RequestId|String|AFF7E5A6-6897-4FDC-A5A8-1978B5B3E545|The ID of the request. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=DescribeSagDropTopN
&RegionId=cn-shanghai
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeSagDropTopNResponse>
  <RequestId>58853663-5DFE-47A1-A69F-F0290BBFBC0A</RequestId>
  <DropTopN>
        <InstanceId>sag-p6ctq4o5bey3e9****</InstanceId>
        <RegionId>cn-shanghai</RegionId>
        <DropRate>0.0</DropRate>
        <Name>ccntest</Name>
  </DropTopN>
  <DropTopN>
        <InstanceId>sag-on7qvl3pv52l33****</InstanceId>
        <RegionId>cn-shanghai</RegionId>
        <DropRate>0.0</DropRate>
        <Name>Tutest</Name>
  </DropTopN>
  <DropTopN>
        <InstanceId>sag-7zyvg7fpk16p15****</InstanceId>
        <RegionId>cn-shanghai</RegionId>
        <DropRate>0.0</DropRate>
        <Name>chtest</Name>
  </DropTopN>
</DescribeSagDropTopNResponse>
```

`JSON` format

```
{
	"RequestId": "58853663-5DFE-47A1-A69F-F0290BBFBC0A",
	"DropTopN": [
		{
			"InstanceId": "sag-p6ctq4o5bey3e9****",
			"RegionId": "cn-shanghai",
			"DropRate": "0.0",
			"Name": "ccntest"
		},
		{
			"InstanceId": "sag-on7qvl3pv52l33****",
			"RegionId": "cn-shanghai",
			"DropRate": "0.0",
			"Name": "Tutest"
		},
		{
			"InstanceId": "sag-7zyvg7fpk16p15****",
			"RegionId": "cn-shanghai",
			"DropRate": "0.0",
			"Name": "chtest"
		}
	]
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

