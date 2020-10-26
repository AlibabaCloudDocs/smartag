# ModifySagWan

Modifies the WAN port configurations of a Smart Access Gateway \(SAG\) device.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates a sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=ModifySagWan&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|ModifySagWan|The operation that you want to perform.

 Set the value to **ModifySagWan**. |
|IPType|String|Yes|DHCP|The connection type of the WAN port: Valid values:

 -   **DHCP**: dynamically obtains an IP address through the Dynamic Host Configuration Protocol \(DHCP\) to access the Internet.
-   **STATIC**: uses a specified IP address to access the Internet. You must specify the IP address, subnet mask, and gateway.
-   **PPPOE**: uses dial-up connections to access the Internet. You must enter the PPPoE account and password provided by the Internet service provider \(ISP\). |
|PortName|String|Yes|0|The name of the WAN port. |
|RegionId|String|Yes|cn-shanghai|The ID of the region where the SAG instance is deployed. |
|SmartAGId|String|Yes|sag-whfn\*\*\*\*|The ID of the SAG instance. |
|SmartAGSn|String|Yes|sag32a30\*\*\*\*|The serial number of the SAG device associated with the SAG instance. |
|IP|String|No|192.XX.XX.1|The IP address of the WAN port.

 **Note:** If the WAN port uses a static IP address, you must set this parameter. |
|Mask|String|No|255.255.255.0|The subnet mask of the IP address of the WAN port.

 **Note:** If the WAN port uses a static IP address, you must set this parameter. |
|Gateway|String|No|192.XX.XX.254|The IP address of the gateway.

 **Note:**

-   If the WAN port uses a static IP address, you must set this parameter.
-   After the gateway is configured, the SAG device automatically adds a default route. |
|Username|String|No|P12ppp\*\*\*|The PPPoE account.

 The username of the account must be 6 to 30 characters in length, and can contain digits and letters.

 **Note:** If the connection type of the WAN port is PPPoE, you must set this parameter. |
|Password|String|No|P12ppq\*\*\*|The PPPoE password.

 The password must be 6 to 30 characters in length, and can contain digits and letters.

 **Note:** If the connection type of the WAN port is PPPoE, you must set this parameter. If you do not need to modify the password, you can skip this parameter. |
|Priority|Integer|No|1|The priority of the WAN port.

 Valid values: **-1** or **1 to 50**. A smaller number indicates a higher priority. **-1** indicates that data transfer is disabled on the WAN port. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|AFF7E5A6-6897-4FDC-A5A8-1978B5B3E545|The ID of the request. |

## Examples

Sample requests

```
http(s)://smartag.cn-shanghai.aliyuncs.com/? Action=ModifySagWan
&IPType=DHCP
&PortName=0
&RegionId=cn-shanghai
&SmartAGId=sag-whfn****
&SmartAGSn=sag32a30****
&<Common request parameters>
```

Sample success responses

`XML` format

```
<ModifySagWanResponse>
     <RequestId>AFF7E5A6-6897-4FDC-A5A8-1978B5B3E545</RequestId>
</ModifySagWanResponse>
```

`JSON` format

```
{
"RequestId": "AFF7E5A6-6897-4FDC-A5A8-1978B5B3E545"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|Sag.PortNotExist|The specified port does not exist.|The specified port does not exist.|
|400|Sag.PortRoleInvalid|The port role is invalid.|The port role is invalid.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

