# DescribeSagVbrRelations

Queries whether a specified virtual border router \(VBR\) is associated with a Smart Access Gateway \(SAG\) instance.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=DescribeSagVbrRelations&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeSagVbrRelations|The operation that you want to perform. Set the value to DescribeSagVbrRelations. |
|VbrInstanceIds.N|RepeatList|Yes|vbr-bp15ihkk93ezxppkd\*\*\*\*|The ID of the VBR. You can specify one or more VBRs in each call. The maximum value of N is **20**. |
|VbrRegionId|String|Yes|cn-hangzhou|The ID of the region where the VBR is deployed. |
|RegionId|String|No|cn-shanghai|The ID of the region where the SAG instance is deployed. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|17D79124-104A-42DB-8FCA-CE2957CD1723|The ID of the request. |
|SagVbrRelations|Array of SagVbrRelation| |Indicates whether the specified VBR is associated with an SAG instance. |
|SagInstanceId|String|sag-0nnteglltw6z4b\*\*\*\*|The ID of the SAG instance. |
|SagUid|String|168840151212121212|The user ID \(UID\) of the Alibaba Cloud account to which the SAG instance belongs. |
|VbrInstanceId|String|vbr-bp15ihkk93ezxppk\*\*\*\*|The ID of the VBR. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=DescribeSagVbrRelations
&VbrInstanceIds.1=vbr-bp15ihkk93ezxppkd****
&VbrRegionId=cn-hangzhou
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeSagVbrRelationsResponse>
  <RequestId>17D79124-104A-42DB-8FCA-CE2957CD1723</RequestId>
  <SagVbrRelations>
        <VbrInstanceId>vbr-bp15ihkk93ezxppkd****</VbrInstanceId>
        <SagInstanceId>sag-0nnteglltw6z4b****</SagInstanceId>
        <SagUid>16884015</SagUid>
  </SagVbrRelations>
</DescribeSagVbrRelationsResponse>
```

`JSON` format

```
{
	"RequestId": "17D79124-104A-42DB-8FCA-CE2957CD1723",
	"SagVbrRelations": [
		{
			"VbrInstanceId": "vbr-bp15ihkk93ezxppkd****",
			"SagInstanceId": "sag-0nnteglltw6z4b****",
			"SagUid": "16884015"
		}
	]
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|403|Forbidden|User not authorized to operate on the specified resource.|The error message returned because you do not have the permissions to manage the specified resource.|
|400|Param.InvalidVersionComparator|The specified version comparison operator is invalid.|The error message returned because the specified operator used to filter SAG instance versions is invalid.|
|400|InvalidRegionID|The specified regionId does not exist.|The error message returned because the specified region ID does not exist.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

