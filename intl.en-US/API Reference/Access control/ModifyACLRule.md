# ModifyACLRule

You can call this operation to modify an access control list \(ACL\) rule.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=ModifyACLRule&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|ModifyACLRule|The operation that you want to perform.

 Set the value to **ModifyACLRule.** |
|AclId|String|Yes|acl-xhwhyuo43l0n\*\*\*\*\*\*\*|The ID of the ACL to which the ACL rule to be modified belongs. |
|AcrId|String|Yes|acr-u98qztgtgvhb\*\*\*\*\*\*\*\*|The ID of the ACL rule to be modified. |
|RegionId|String|Yes|cn-hangzhou|The ID of the region to which the ACL rule to be modified belongs. |
|Description|String|No|test|The description of the rule. The description must be 1 to 512 characters in length. |
|Direction|String|No|in|Specifies whether the ACL rule controls inbound or outbound access requests.

 Valid values: **in or out**. |
|SourceCidr|String|No|0.0.0.0/0|The source IP address range specified in the ACL rule. CIDR blocks and IPv4 addresses are supported.

 Default value: **0.0.0.0/0**. |
|DestCidr|String|No|0.0.0.0/0|The destination IP address range specified in the ACL rule. CIDR blocks and IPv4 addresses are supported.

 Default value: **0.0.0.0/0**. |
|IpProtocol|String|No|tcp|The Transmission Control Protocol. The value is not case-sensitive. |
|SourcePortRange|String|No|80/80|The range of the source port. |
|DestPortRange|String|No|80/80|The range of the destination port. |
|Policy|String|No|accept|Access permissions:

 -   **accept**: access permissions granted.
-   **drop**: access permissions denied. |
|Priority|Integer|No|2|The priority of the ACL rule. Valid values: 1 to 100.

 Default value: 1. |
|Type|String|No|LAN|The type of the ACL rule:

 -   **LAN**: private networks.
-   **WAN**: public networks. |
|Name|String|No|doctest|The name of the ACL rule. The name must be 2 to 100 characters in length, and can contain digits, periods \(.\), underscores \(\_\), and hyphens \(-\). It must start with a letter or Chinese character. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|9B0F1C25-389E-4E78-9392-E89F8531F87C|The ID of the request. |
|AcrId|String|acr-u98qztgtgvhb8\*\*\*\*\*\*|The ID of the ACL modified rule. |
|AclId|String|acl-xhwhyuo43l0n\*\*\*\*\*\*|The ID of the ACL to which the modified ACL rule belongs. |
|Description|String|test|The description of the rule. The description must be 1 to 512 characters in length. |
|Direction|String|in|Specifies whether the ACL rule controls inbound or outbound access requests. Valid values: **in or out**. |
|SourceCidr|String|0.0.0.0/0|The source IP address range specified in the ACL rule. CIDR blocks and IPv4 addresses are supported.

 Default value: **0.0.0.0/0**. |
|DestCidr|String|0.0.0.0/0|The destination IP address range specified in the ACL rule. CIDR blocks and IPv4 addresses are supported.

 Default value: **0.0.0.0/0**. |
|IpProtocol|String|tcp|The Transmission Control Protocol. The value is not case-sensitive. |
|SourcePortRange|String|80/80|The range of the source port. |
|DestPortRange|String|80/80|The range of the destination port. |
|Policy|String|drop|Access permissions:

 -   **accept**: access permissions granted.
-   **drop**: access permissions denied. |
|Priority|Integer|2|The priority. Valid values: 1 to 100.

 Default value: 1. |
|GmtCreate|Long|1553777700000|The time when the ACL rule was created. It is a long type timestamp. When timestamps are assigned the same priority, the timestamp with the smallest value prevails. |
|Name|String|doctest|The name of the ACL rule. The name must be 2 to 100 characters in length, and can contain digits, periods \(.\), underscores \(\_\), and hyphens \(-\). It must start with a letter or Chinese character. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? AclId=acl-xhwhyuo43l0n*******
&AcrId=acr-u98qztgtgvhb********
&RegionId=cn-hangzhou
&<Common request parameter>
```

Sample success responses

`XML` format

```
<ModifyACLRule>
      <AcrId>acr-u98qztgtgvhb87****</AcrId>
	  <GmtCreate>1553777700000</GmtCreate>
	  <Direction>out</Direction>
	  <Priority>1</Priority>
	  <IpProtocol>TCP</IpProtocol>
	  <SourceCidr>192.168.3.0/24</SourceCidr>
	  <SourcePortRange>1/65535</SourcePortRange>
	  <AclId>acl-xhwhyuo43l0n2b****</AclId>
	  <Policy>drop</Policy>
	  <RequestId>9B0F1C25-389E-4E78-9392-E89F8531F87C</RequestId>
	  <DestPortRange>1/65535</DestPortRange>
	  <DestCidr>10.0.0.1/32</DestCidr>
    </ModifyACLRule>
```

`JSON` format

```
{
    "AcrId": "acr-u98qztgtgvhb87****", 
    "GmtCreate": 1553777700000, 
    "Direction": "out", 
    "Priority": 1, 
    "IpProtocol": "TCP", 
    "SourceCidr": "192.168.3.0/24", 
    "SourcePortRange": "1/65535", 
    "AclId": "acl-xhwhyuo43l0n2b****", 
    "Policy": "drop", 
    "RequestId": "9B0F1C25-389E-4E78-9392-E89F8531F87C", 
    "DestPortRange": "1/65535", 
    "DestCidr": "10.0.0.1/32"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|403|Forbidden|User not authorized to operate on the specified resource.|The error code returned because you do not have the permission to manage the resource.|
|403|MissingParameter|The input parameter is missing, please check your input.|The error code returned because a request parameter is not set. Check the request parameters.|
|403|InvalidDescription|Description not valid.|The error code returned because the length of the description exceeds the upper limit.|
|403|InvalidParameter|The specified parameter is invalid.|The error code returned because a specified parameter is invalid.|
|403|FeatureNotSupport|The current edition of the smart access gateway does not support this feature.|The error code returned because the current version of the Smart Access Gateway \(SAG\) device does not support this feature.|
|403|FeatureNotSupportForActiveSmartAG|The current edition of the active smart access gateway does not support this feature.|The error code returned because the current version of the active SAG device does not support this feature.|
|403|FeatureNotSupportForStandBySmartAG|The current edition of the standby smart access gateway does not support this feature.|The error code returned because the current version of the standby SAG device does not support this feature.|
|403|NotSupportedProtocol|The specified protocol of the ACL rule is not supported.|The error code returned because the specified protocol type of the ACL rule is not supported.|
|403|InvalidId.ACL|The specified ACL ID is invalid.|The error code returned because the specified ACL ID is invalid.|
|403|InvalidId.ACR|The specified ACL rule ID is invalid.|The error code returned because the specified ACL rule ID is invalid.|
|403|InvalidPortRange|The specified port range is invalid.|The error code returned because the specified port range is invalid.|
|403|InternalError|An internal server error occurred.|The error code returned because an internal server error occurred.|
|400|ACL.NoSupportWanType|An SAG 1000 device does not support a WAN ACL.|The error code returned because an SAG-1000 device does not support a WAN ACL rule.|
|400|ACL.InvalidType|The specified ACL type is invalid.|The error code returned because the specified ACL rule type is invalid.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

