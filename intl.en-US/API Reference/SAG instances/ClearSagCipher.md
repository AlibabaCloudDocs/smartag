# ClearSagCipher

Resets the key of a Smart Access Gateway \(SAG\) vCPE device.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=ClearSagCipher&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|ClearSagCipher|The operation that you want to perform.

 Set the value to **ClearSagCipher**. |
|RegionId|String|Yes|cn-shanghai|The ID of the region where the SAG instance is deployed. |
|SagId|String|Yes|sag-0nnteglltw6z4b\*\*\*\*|The ID of the SAG instance. |
|SnNumber|String|Yes|sag42c3\*\*\*\*|The serial number of the SAG vCPE device. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|3712F0B2-721E-4FBF-BBEF-888E3BFE0A20|The ID of the request. |

## Examples

Sample request

```
http(s)://[Endpoint]/? Action=ClearSagCipher
&RegionId=cn-shanghai
&SagId=sag-0nnteglltw6z4b****
&SnNumber=sag42c3****
&<Common request parameters>
```

Sample success responses

`XML` format

```
<ClearSagCipherResponse>
  <RequestId>69E19A6D-8114-4D57-94A0-14CC7CA578C8</RequestId>
</ClearSagCipherResponse>
```

`JSON` format

```
{
	"RequestId": "69E19A6D-8114-4D57-94A0-14CC7CA578C8"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|403|MissingParameter|The input parameter is missing, please check your input.|The error message returned because a required parameter is not set. Check whether you have set all required parameters.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

