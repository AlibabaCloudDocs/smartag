# DescribeSagTrafficTopN

You can call this operation to query the top 10 Smart Access Gateway \(SAG\) instances that have the highest data transfer rates in a specific region.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=DescribeSagTrafficTopN&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|DescribeSagTrafficTopN|The operation that you want to perform.

 Set the value to **DescribeSagTrafficTopN**. |
|RegionId|String|Yes|cn-shanghai|The ID of the region where the SAG instance is deployed. |
|Size|Integer|No|10|The number of SAG instances to be queried. Default value:**10**. This value cannot be modified. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|AFF7E5A6-6897-4FDC-A5A8-1978B5B3E545|The ID of the request. |
|TrafficTopN|Array| |The information about the data transfer rate of the SAG instance. |
|InstanceId|String|sag-whfn\*\*\*\*|The ID of the SAG instance. |
|Name|String|test|The name of the SAG instance. |
|RegionId|String|cn-shanghai|The ID of the region where the SAG instance is deployed. |
|TrafficRate|String|3866.6666666666665|The data transfer rate of the SAG instance. Unit: bit/s |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=DescribeSagTrafficTopN
&RegionId=cn-shanghai
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeSagTrafficTopNResponse>
  <RequestId>0390E09B-8824-4B79-A27E-35BE65DA8E48</RequestId>
  <TrafficTopN>
        <InstanceId>sag-moa1tjqpa7zbik****</InstanceId>
        <TrafficRate>3900.0</TrafficRate>
        <RegionId>cn-shanghai</RegionId>
        <Name>jitest</Name>
  </TrafficTopN>
  <TrafficTopN>
        <InstanceId>sag-7zyvg7fpk16p15****</InstanceId>
        <TrafficRate>1243.2</TrafficRate>
        <RegionId>cn-shanghai</RegionId>
        <Name>chutest</Name>
  </TrafficTopN>
</DescribeSagTrafficTopNResponse>
```

`JSON` format

```
{
	"RequestId": "0390E09B-8824-4B79-A27E-35BE65DA8E48",
	"TrafficTopN": [

		{
			"InstanceId": "sag-moa1tjqpa7zbik****",
			"TrafficRate": "3900.0",
			"RegionId": "cn-shanghai",
			"Name": "jitest"
		},
		{
			"InstanceId": "sag-7zyvg7fpk16p15****",
			"TrafficRate": "1243.2",
			"RegionId": "cn-shanghai",
			"Name": "chutest"
		}
	]
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

