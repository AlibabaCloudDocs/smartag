# AddACLRule

You can call this operation to add an access control list \(ACL\) rule.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=AddACLRule&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|AddACLRule|The operation that you want to perform.

 Set the value to **AddACLRule**. |
|AclId|String|Yes|acl-xhwhyuo43l0n\*\*\*\*\*|The ID of the ACL. |
|DestCidr|String|Yes|0.0.0.0/0|The range of destination IP addresses specified in the ACL rule. CIDR blocks and IPv4 addresses are supported.

 Default value: **0.0.0.0/0**. |
|DestPortRange|String|Yes|1/200|The range of the destination port. Format: 80/80. |
|Direction|String|Yes|in|Specifies whether the ACL rule controls inbound or outbound access requests.

 Valid values: **in or out**. |
|IpProtocol|String|Yes|tcp|The Transmission Control Protocol \(TCP\). The value is not case-sensitive. |
|Policy|String|Yes|accept|Access permissions. Valid values:

 -   **accept**: access permissions granted.
-   **drop**: access permissions denied. |
|RegionId|String|Yes|cn-hangzhou|The ID of the region to which the ACL belongs. |
|SourceCidr|String|Yes|0.0.0.0/0|The source IP address range specified in the ACL rule. CIDR blocks and IPv4 addresses are supported.

 Default value: **0.0.0.0/0**. |
|SourcePortRange|String|Yes|1/200|The range of the source port. Format: 80/80. |
|Description|String|No|test|The description of the ACL rule. The description must be **1 to 512** characters in length. |
|Priority|Integer|No|12|The priority of the ACL rule. Valid values: **1 to 100**.

 Default value: **1**. |
|Type|String|No|LAN|The type of the ACL rule:

 -   **LAN**: private networks.
-   **WAN**: the Internet. |
|Name|String|No|doctest|The name of the ACL rule.

 The name must be 2 to 100 characters in length, and can contain digits, periods \(.\), underscores \(\_\), and hyphens \(-\). It must start with a letter or Chinese character. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|880F84CB-9B54-4413-A8A3-8832C82D1BC4|The ID of the request. |
|AcrId|String|acr-c1hkd054qywi\*\*\*\*\*\*|The ID of the ACL rule. |
|AclId|String|acl-xhwhyuo43l0\*\*\*\*\*\*\*|The ID of the ACL. |
|Description|String|3|The description of the ACL rule. The description must be **1 to 512** characters in length. |
|Direction|String|out|Specifies whether the ACL rule controls inbound or outbound access requests.

 Valid values: **in or out**. |
|SourceCidr|String|192.168.3.0/24|The range of source IP addresses specified in the ACL rule. CIDR blocks and IPv4 addresses are supported.

 Default value: **0.0.0.0/0**. |
|DestCidr|String|10.0.0.1/32|The range of destination IP addresses specified in the ACL rule. CIDR blocks and IPv4 addresses are supported.

 Default value: **0.0.0.0/0**. |
|IpProtocol|String|TCP|The Transmission Control Protocol \(TCP\). The value is not case-sensitive. |
|SourcePortRange|String|1/65535|The range of the source port. Format: 80/80. |
|DestPortRange|String|1/65535|The range of the destination port. Format: 80/80. |
|Policy|String|drop|Access permissions. Valid values:

 -   **accept**: access permissions granted.
-   **drop**: access permissions denied. |
|Priority|Integer|1|The priority of the ACL rule. Valid values: **1 to 100**.

 Default value: **1**. |
|GmtCreate|Long|1553766882689|The time when the ACL rule was created. It is a long type timestamp. When timestamps are assigned the same priority, the timestamp with the smallest value prevails. |
|Type|String|LAN|The type of the ACL rule:

 -   **LAN**: private networks.
-   **WAN**: public networks. |
|Name|String|doctest|The name of the ACL rule.

 The name must be 2 to 100 characters in length, and can contain digits, periods \(.\), underscores \(\_\), and hyphens \(-\). It must start with a letter or Chinese character. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=AddACLRule
&AclId=acl-xhwhyuo43l0n*****
&DestCidr=0.0.0.0/0
&DestPortRange=1/200
&Direction=in
&IpProtocol=tcp
&Policy=accept
&RegionId=cn-hangzhou
&SourceCidr=0.0.0.0/0
&SourcePortRange=1/200
&<Common request parameters>
```

Sample success responses

`XML` format

```
<AddACLRule>
  <AcrId>acr-c1hkd054qywiw2****</AcrId>
  <Type>LAN</Type>
  <GmtCreate>1553766882689</GmtCreate>
  <Direction>out</Direction>
  <Priority>1</Priority>
  <Name>doctest</Name>
  <IpProtocol>TCP</IpProtocol>
  <SourceCidr>192.168.3.0/24</SourceCidr>
  <SourcePortRange>1/65535</SourcePortRange>
  <AclId>acl-xhwhyuo43l0n2b****</AclId>
  <Policy>drop</Policy>
  <RequestId>880F84CB-9B54-4413-A8A3-8832C82D1BC4</RequestId>
  <DestPortRange>1/65535</DestPortRange>
  <DestCidr>10.0.0.1/32</DestCidr>
</AddACLRule>
```

`JSON` format

```
{
    "AcrId": "acr-c1hkd054qywiw2****", 
    "Type": "LAN",
    "GmtCreate": 1553766882689, 
    "Direction": "out", 
    "Priority": 1, 
    "Name": "doctest",
    "IpProtocol": "TCP", 
    "SourceCidr": "192.168.3.0/24", 
    "SourcePortRange": "1/65535", 
    "AclId": "acl-xhwhyuo43l0n2b****", 
    "Policy": "drop", 
    "RequestId": "880F84CB-9B54-4413-A8A3-8832C82D1BC4", 
    "DestPortRange": "1/65535", 
    "DestCidr": "10.0.0.1/32"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|403|Forbidden|User not authorized to operate on the specified resource.|The error message returned because you do not have the permission to manage the resource.|
|403|MissingParameter|The input parameter is missing, please check your input.|The error message returned because a request parameter is not set. Check the request parameters.|
|403|InvalidDescription|Description not valid.|The error message returned because the length of the description exceeds the upper limit.|
|403|InvalidParameter|The specified parameter is invalid.|The error message returned because a specified parameter is invalid.|
|403|FeatureNotSupport|The current edition of the smart access gateway does not support this feature.|The error message returned because the current version of the Smart Access Gateway \(SAG\) device does not support this feature.|
|403|FeatureNotSupportForActiveSmartAG|The current edition of the active smart access gateway does not support this feature.|The error message returned because the current version of the active SAG device does not support this feature.|
|403|FeatureNotSupportForStandBySmartAG|The current edition of the standby smart access gateway does not support this feature.|The error message returned because the current version of the standby SAG device does not support this feature.|
|403|NotSupportedProtocol|The specified protocol of the ACL rule is not supported.|The error message returned because the specified protocol type of the ACL rule is not supported.|
|403|InvalidId.ACL|The specified ACL ID is invalid.|The error message returned because the specified ACL ID is invalid.|
|403|InvalidPortRange|The specified port range is invalid.|The error message returned because the specified port range is invalid.|
|403|AcrPerAclAmountLimit|The maximum number of rules in an ACL is exceeded. You can open a ticket to increase the quota.|The error message returned because the number of created ACL rules in an ACL exceeds the upper limit. Submit a ticket to increase the quota.|
|403|InternalError|An internal server error occurred.|The error message returned because an internal server error has occurred.|
|400|ACL.NoSupportWanType|An SAG 1000 device does not support a WAN ACL.|The error message returned because an SAG-1000 device does not support a WAN ACL rule.|
|400|ACL.InvalidType|The specified ACL type is invalid.|The error message returned because the specified ACL rule type is invalid.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

