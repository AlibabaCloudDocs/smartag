# ModifySagWan

Modifies the WAN port settings of a Smart Access Gateway \(SAG\) device.

## Background information

We recommend that you understand the functionality of a WAN port before you modify its settings. For more information, see [Configure a WAN port](~~163955~~).

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=ModifySagWan&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|ModifySagWan|The operation that you want to perform.

 Set the value to **ModifySagWan**. |
|IPType|String|Yes|DHCP|The connection type of the WAN port: Valid values:

 -   **DHCP**: The WAN port connects to the Internet through an IP address that is dynamically assigned by the Dynamic Host Configuration Protocol \(DHCP\) server.
-   **STATIC**: The WAN port connects to the Internet through a static IP address. If you set this value, you must configure a static IP address, a subnet mask, and a gateway IP address for the WAN port.
-   **PPPOE**: The WAN port connects to the Internet through dial-up connections. If you set this value, you must enter the username and password of the PPPoE account provided by the Internet service provider \(ISP\). |
|PortName|String|Yes|0|The number of the WAN port. |
|RegionId|String|Yes|cn-shanghai|The ID of the region where the SAG instance is deployed. |
|SmartAGId|String|Yes|sag-whfn\*\*\*\*|The ID of the SAG instance. |
|SmartAGSn|String|Yes|sag32a30\*\*\*\*|The serial number \(SN\) of the SAG device. |
|IP|String|No|192.XX.XX.1|The IP address of the WAN port.

 **Note:** If the WAN port uses a static IP address, you must set this parameter. |
|Mask|String|No|255.255.255.0|The subnet mask of the WAN port IP address.

 **Note:** If the WAN port uses a static IP address, you must set this parameter. |
|Gateway|String|No|192.XX.XX.254|The IP address of the gateway.

 **Note:**

-   If the WAN port uses a static IP address, you must set this parameter.
-   After this parameter is set, the SAG device generates a default route. |
|Username|String|No|P12ppp\*\*\*|The username of the PPPoE account.

 The username must be 6 to 30 characters in length, and can contain digits and letters.

 **Note:** If the connection type of the WAN port is PPPoE, you must set this parameter. |
|Password|String|No|P12ppq\*\*\*|The password of the PPPoE account.

 The password must be 6 to 30 characters in length, and can contain digits and letters.

 **Note:** If the connection type of the WAN port is PPPoE, you must set this parameter. If you do not need to modify the password, you can ignore this parameter. |
|Priority|Integer|No|1|The priority of the WAN port.

 Valid values: **-1** and **1 to 50**.

 A smaller number represents a higher priority. A value of **-1** indicates that the WAN port is not used to forward network traffic. |
|Weight|Integer|No|100|The weight of the WAN port.

 Valid values: **1 to 100**. Default value: **100**. |
|ISP|String|No|CT|The ISP used by the WAN port. Valid values:

 -   **CT**: China Telecom
-   **CM**: China Mobile
-   **CU**: China Unicom
-   **Other**: Other ISPs |
|Bandwidth|Integer|No|50|The bandwidth cap of the WAN port. Unit: Mbit/s. |

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
|400|Sag.PortNotExist|The specified port does not exist.|The error message returned because the specified port does not exist.|
|400|Sag.PortRoleInvalid|The port role is invalid.|The error message returned because the port role is invalid.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

