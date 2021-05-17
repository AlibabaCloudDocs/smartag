# ModifySagManagementPort

You can call this operation to modify the management port configurations of a Smart Access Gateway \(SAG\) device.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=ModifySagManagementPort&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|ModifySagManagementPort|The operation that you want to perform.

Set the value to **ModifySagManagementPort**. |
|Gateway|String|Yes|192.XX.XX.254|The IP address of the management port gateway. |
|IP|String|Yes|192.XX.XX.1|The IP address of the management port. |
|Mask|String|Yes|255.255.255.0|The subnet mask of the IP address of the management port. |
|RegionId|String|Yes|cn-shanghai|The ID of the region where the SAG instance is deployed. |
|SmartAGId|String|Yes|sag-whfn\*\*\*\*|The ID of the SAG instance. |
|SmartAGSn|String|Yes|sag32a30\*\*\*\*|The serial number of the SAG device associated with the SAG instance. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|6877D55B-08F7-4DA3-916B-32A6FD402E06|The ID of the request. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=ModifySagManagementPort
&Gateway=192.XX.XX.254
&IP=192.XX.XX.1
&Mask=255.255.255.0
&RegionId=cn-shanghai
&SmartAGId=sag-whfn****
&SmartAGSn=sag32a30****
&<Common request parameters>
```

Sample success responses

`XML` format

```
<ModifySagManagementPortResponse>
      <RequestId>6877D55B-08F7-4DA3-916B-32A6FD402E06</RequestId>
</ModifySagManagementPortResponse>
```

`JSON` format

```
{
   "RequestId":"6877D55B-08F7-4DA3-916B-32A6FD402E06"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|Sag.PortMgtError|The role of a management port cannot be changed.|The role of the management port cannot be changed.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

