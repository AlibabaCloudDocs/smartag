# DeleteSmartAccessGateway

Deletes a Smart Access Gateway \(SAG\) instance.

## Prerequisites

-   The SAG instance that you want to delete is an SAG CPE instance or an SAG vCPE instance.
-   The SAG instance that you want to delete is locked due to overdue payments.
-   The SAG instance that you want to delete is not associated with a Cloud Connect Network \(CCN\) instance or a virtual border router \(VBR\). If the SAG instance is associated with a CCN instance or a VBR, dissociate the SAG instance from the CCN instance or VBR first. For more information, see [Detach a network](~~164903~~).

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=DeleteSmartAccessGateway&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DeleteSmartAccessGateway|The operation that you want to perform. Set the value to **DeleteSmartAccessGateway**. |
|InstanceId|String|Yes|sag-far8v6owtdxlua\*\*\*\*|The ID of the SAG instance that you want to delete. |
|RegionId|String|No|cn-hangzhou|The ID of the region where the SAG instance is deployed. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|E26DBAAE-A796-4A48-98B4-B45AFCD1F299|The ID of the request. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=DeleteSmartAccessGateway
&InstanceId=sag-far8v6owtdxlua****
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DeleteSmartAccessGatewayResponse>
  <RequestId>D133AFFC-6E37-414D-8ECD-246DEBE4388D</RequestId>
</DeleteSmartAccessGatewayResponse>
```

`JSON` format

```
{
	"RequestId": "D133AFFC-6E37-414D-8ECD-246DEBE4388D"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|403|MissingParameter|The input parameter is missing, please check your input.|The error message returned because a required parameter is not set. Check whether you have set all required parameters.|

访问[错误中心](https://error-center.aliyun.com/status/product/Smartag)查看更多错误码。

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

