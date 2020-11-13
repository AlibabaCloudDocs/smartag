# DiagnoseSmartAccessGateway

Enables diagnostics for Smart Access Gateway \(SAG\) devices.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=DiagnoseSmartAccessGateway&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DiagnoseSmartAccessGateway|The operation that you want to perform.

 Set the value to **DiagnoseSmartAccessGateway**. |
|RegionId|String|Yes|cn-shanghai|The ID of the region where the SAG instance is deployed. |
|SmartAGId|String|Yes|sag-1um5x5nwhilymw\*\*\*\*|The ID of the SAG instance. |
|SmartAGSn|String|Yes|sage62x022502\*\*\*\*|The serial number \(SN\) of the SAG device. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|193AE392-76C2-4D3E-9420-889A51B43CC0|The ID of the request. |

## Examples

Sample request

```
http(s)://[Endpoint]/? Action=DiagnoseSmartAccessGateway
&RegionId=cn-shanghai
&SmartAGId=sag-1um5x5nwhilymw****
&SmartAGSn=sage62x022502****
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DiagnoseSmartAccessGatewayResponse>
  <RequestId>193AE392-76C2-4D3E-9420-889A51B43CC0</RequestId>
</DiagnoseSmartAccessGatewayResponse>
```

`JSON` format

```
{
	"RequestId": "193AE392-76C2-4D3E-9420-889A51B43CC0"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|403|MissingParameter|The input parameter is missing, please check your input.|The error message returned because a required parameter is not set. Check whether you have set all required parameters.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

