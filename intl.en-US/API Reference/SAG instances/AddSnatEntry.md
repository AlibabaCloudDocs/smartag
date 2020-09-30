# AddSnatEntry

You can call this operation to add a source network address translation \(SNAT\) entry to a Smart Access Gateway \(SAG\) instance.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=AddSnatEntry&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|AddSnatEntry|The operation that you want to perform.

 Set the value to **AddSnatEntry**. |
|CidrBlock|String|Yes|192.168.0.1/24|The destination CIDR block. |
|RegionId|String|Yes|cn-hangzhou|The ID of the region where the SAG instance is deployed. |
|SmartAGId|String|Yes|sag-hgke\*\*\*\*\*\*\*\*\*\*\*\*\*|The ID of the SAG instance. |
|SnatIp|String|Yes|10.0.\*\*. \*\*|The public IP address. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|56BF6C79-C77D-41A0-86DD-A4B156E784EA|The ID of the request. |
|InstanceId|String|snat-m2obgkt5ya1puz\*\*\*\*|The ID of the SNAT instance. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=AddSnatEntry
&CidrBlock=192.168.0.1/24
&RegionId=cn-hangzhou
&SmartAGId=sag-hgke*************
&SnatIp=10.0. **. **
&<Common request parameters>
```

Sample success responses

`XML` format

```
<AddSnatEntryResponse>
	  <InstanceId>snat-m2obgkt5ya1puz****</InstanceId>
	  <RequestId>56BF6C79-C77D-41A0-86DD-A4B156E784EA</RequestId>
    </AddSnatEntryResponse>
```

`JSON` format

```
{
"InstanceId":"snat-m2obgkt5ya1puz****",
"RequestId":"56BF6C79-C77D-41A0-86DD-A4B156E784EA"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|403|FeatureNotSupport|The current edition of the smart access gateway does not support this feature.|The error message returned because the current version of the specified SAG instance does not support this feature.|
|400|SAG.InstanceNoFound|The specified SAG instance does not exist.|The error message returned because the specified SAG instance does not exist.|
|500|SmartAccessGatewayInArrears|The specified Smart Access Gateway has expired.|The error message returned because the specified SAG instance has expired. Renew the SAG instance first.|
|500|SmartAccessGatewayNotActivated|The specified Smart Access Gateway has not been activated.|The error message returned because the specified SAG instance has not been activated. Activate the SAG instance first.|
|400|SNAT.CidrConfigExist|The specified SNAT CIDR block already exists.|The error message returned because the specified CIDR block in the SNAT entry already exists.|
|400|SNAT.AmountLimit|The maximum number of SNAT entries is exceeded.|The error message returned because the number of SNAT entries has reached the upper limit.|
|400|SNAT.SnatDnatIpConflict|The SNAT destination IP address is the same as the DNAT IP address.|The error message returned because the destination IP address in the SNAT entry overlaps with the IP address in the DNAT entry.|
|403|FeatureNotSupportForStandBySmartAG|The current edition of the standby smart access gateway does not support this feature.|The error message returned because the current version of the standby SAG device does not support this feature.|
|500|InternalError|An error occurred while processing your request.|The error message returned because an unknown error occurred.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

