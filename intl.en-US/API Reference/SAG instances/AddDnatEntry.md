# AddDnatEntry

You can call this operation to add a destination network address translation \(DNAT\) entry to a Smart Access Gateway \(SAG\) instance.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=AddDnatEntry&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|AddDnatEntry|The operation that you want to perform.

 Set the value to **AddDnatEntry**. |
|ExternalPort|String|Yes|80|The Internet-facing port.

 Valid values: **1 to 65535**. |
|InternalIp|String|Yes|192.168.0.1|The IP address of the destination private network. |
|InternalPort|String|Yes|80|The destination private port.

 Valid values: **1 to 65535**. |
|IpProtocol|String|Yes|TCP|The protocol used in DNAT. Valid values:

 -   **TCP**: forwards TCP packets.
-   **UDP**: forwards UDP packets.
-   **Any**: forwards packets of all protocols. |
|RegionId|String|Yes|cn-hangzhou|The ID of the region where the SAG instance is deployed. |
|SagId|String|Yes|sag-kdhg\*\*\*\*\*\*\*|The ID of the SAG instance.

 **Note:** Only SAG instances used to manage SAG devices supported DNAT. |
|Type|String|Yes|Intranet|

 The type of the DNAT entry. Valid values:

 -   **Intranet**: the default value. Translates the destination IP address to a specific internal IP address.
-   **Internet**: translates the destination IP address to a specific public IP address. |
|ExternalIp|String|No|10.10.1.xx|The public IP address.

 **Note:** If the DNAT entry is used to forward packets transmitted over the Internet, the DNAT entry automatically recognizes the current public IP address. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|DnatEntryId|String|fwd-kxe4fq3xuzczze\*\*\*\*|The ID of the DNAT entry. |
|RequestId|String|56BF6C79-C77D-41A0-86DD-A4B156E784EA|The ID of the request. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=AddDnatEntry
&ExternalPort=80
&InternalIp=192.168.0.1
&InternalPort=80
&IpProtocol=TCP
&RegionId=cn-hangzhou
&SagId=sag-kdhg*******
&Type=Intranet
&<Common request parameters>
```

Sample success responses

`XML` format

```
<AddDnatEntryResponse>
	    <DnatEntryId>fwd-kxe4fq3xuzczze****</DnatEntryId>
	    <RequestId>56BF6C79-C77D-41A0-86DD-A4B156E784EA</RequestId>
</AddDnatEntryResponse>
```

`JSON` format

```
{
	"RequestId":"56BF6C79-C77D-41A0-86DD-A4B156E784EA",
	"DnatEntryId":"fwd-kxe4fq3xuzczze****"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|403|Forbidden|User not authorized to operate on the specified resource.|The error message returned because you do not have the permission to manage the specified resource.|
|403|MissingParameter|The input parameter is missing, please check your input.|The error message returned because a required parameter is not set. Check whether you have set all required parameters.|
|403|InvalidParameter|The specified parameter is invalid.|The error message returned because a specified parameter is invalid.|
|403|InternalError|An internal server error occurred.|The error message returned because an internal error occurred.|
|400|InvalidRegionID|The specified regionId does not exist.|The error message returned because the specified region ID \(RegionId\) does not exist.|
|500|SmartAccessGatewayNotActivated|The specified Smart Access Gateway has not been activated.|The error message returned because the specified SAG instance has not been activated. Activate the SAG instance first.|
|500|SmartAccessGatewayInArrears|The specified Smart Access Gateway has expired.|The error message returned because the specified SAG instance has expired. Renew the SAG instance first.|
|400|MissingParam|You must specify the parameter.|The error message returned because a required parameter is not specified.|
|400|IllegalParam|The parameter is invalid.|The error message returned because a specified parameter is invalid.|
|403|FeatureNotSupport|The current edition of the smart access gateway does not support this feature.|The error message returned because the current version of the SAG instance does not support this feature.|
|403|InvalidId.SMARTAG|The specified smart access gateway instance id is invalid.|The error message returned because the specified ID of the SAG instance is invalid.|
|400|DuplicatedDnatEntry|The specified ExternalIp, IpProtocol, ExternalPort, InternalIp, and InternalPort are duplicated.|The error message returned because the specified public IP address, protocol, external-facing port, internal IP address, or Internal-facing port is duplicate.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

