# ModifyACLRule

Modifies an access control list \(ACL\) rule.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=ModifyACLRule&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|ModifyACLRule|The operation that you want to perform.

Set the value to **ModifyACLRule**. |
|AclId|String|Yes|acl-xhwhyuo43l0n\*\*\*\*\*\*\*|The ID of the ACL to which the ACL rule belongs. |
|AcrId|String|Yes|acr-u98qztgtgvhb\*\*\*\*\*\*\*\*|The ID of the ACL rule.

You can call the [DescribeACLAttribute](~~114017~~) operation to query the IDs of ACL rules that belong to the current ACL. |
|RegionId|String|Yes|cn-hangzhou|The ID of the region where the ACL is deployed. |
|Description|String|No|test|The description of the ACL rule.

The description must be**1**to**512**characters in length. |
|Direction|String|No|in|The direction in which the ACL rule is applied. Valid values:

-   **in**: The ACL rule controls inbound network traffic of the on-premises network that is associated with the SAG instance.
-   **out**: The ACL rule controls outbound network traffic of the on-premises network that is associated with the SAG instance. |
|SourceCidr|String|No|192.168.1.0/24|The range of the source IP addresses.

Set this parameter in CIDR notation. Example: 192.168.1.0/24. |
|DestCidr|String|No|192.168.10.0/24.|The range of the destination IP addresses.

Set this parameter in CIDR notation. Example: 192.168.10.0/24. |
|IpProtocol|String|No|tcp|The protocol that is applied to the ACL rule.

The supported protocols provided in this topic are for reference only. The actual protocols in the SAG console shall prevail. The value is not case-sensitive. |
|SourcePortRange|String|No|80/80|The range of the source ports.

Valid values: **-1** and **1** to **65535**.

Set the source port range in one of the following formats: 1/200 or 80/80. A value of -1/-1 indicates that all ports are available. |
|DestPortRange|String|No|80/80|The range of the destination ports.

Valid values: **-1** and **1** to **65535**.

Set the destination port range in one of the following formats: 1/200 or 80/80. A value of -1/-1 indicates that all ports are available. |
|Policy|String|No|accept|The action policy of the ACL rule. Valid values:

-   **accept**: allows the network traffic.
-   **drop**: blocks the network traffic. |
|Priority|Integer|No|2|The priority of the ACL rule.

A smaller value indicates a higher priority. If rules have the same priority, whichever applied to the SAG devices earlier takes effect.

Valid values: **1 to 100**. |
|Type|String|No|LAN|The type of the ACL rule. Valid values:

-   **LAN**: The ACL rule controls traffic of private IP addresses.
-   **WAN**: The ACL rule controls traffic of public IP addresses. |
|Name|String|No|doctest|The name of the ACL rule.

The name must be 2 to 100 characters in length, and can contain digits, periods \(.\), underscores \(\_\), and hyphens \(-\). It must start with a letter. |
|DpiSignatureIds.N|RepeatList|No|1|The IDs of applications.

You can call the [ListDpiSignatures](~~196630~~) operation to query application IDs and information. Maximum value of N: **10**. |
|DpiGroupIds.N|RepeatList|No|20|The IDs of application groups.

You can call the [ListDpiGroups](~~196754~~) operation to query application group IDs and information. Maximum value of N: **10**. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|AclId|String|acl-xhwhyuo43l0n\*\*\*\*\*\*|The ID of the ACL to which the ACL rule belongs. |
|AcrId|String|acr-u98qztgtgvhb8\*\*\*\*\*\*|The ID of the ACL rule. |
|Description|String|test|The description of the ACL rule.

The description must be**1**to**512**characters in length. |
|DestCidr|String|192.168.10.0/24|The range of the destination IP addresses.

Set this parameter in CIDR notation. Example: 192.168.10.0/24. |
|DestPortRange|String|80/80|The range of the destination ports. |
|Direction|String|in|The direction in which the ACL rule is applied. Valid values:

-   **in**: The ACL rule controls inbound network traffic of the on-premises network that is associated with the SAG instance.
-   **out**: The ACL rule controls outbound network traffic of the on-premises network that is associated with the SAG instance. |
|DpiGroupIds|List|20|The IDs of application groups. |
|DpiSignatureIds|List|1|The IDs of applications. |
|GmtCreate|Long|1553777700000|The timestamp when the ACL rule was created.

The timestamp is in Long format. If ACL rules have the same priority, the one with the smallest timestamp prevails. |
|IpProtocol|String|tcp|The protocol that is applied to the ACL rule. |
|Name|String|doctest|The name of the ACL rule. |
|Policy|String|drop|The action policy of the ACL rule. Valid values:

-   **accept**: allows the network traffic.
-   **drop**: blocks the network traffic. |
|Priority|Integer|2|The priority of the ACL rule.

A smaller value indicates a higher priority. If rules have the same priority, whichever applied to the SAG devices earlier takes effect. |
|RequestId|String|9B0F1C25-389E-4E78-9392-E89F8531F87C|The ID of the request. |
|SourceCidr|String|192.168.1.0/24|The range of the source IP addresses.

Set this parameter in CIDR notation. Example: 192.168.1.0/24. |
|SourcePortRange|String|80/80|The range of the source ports. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=ModifyACLRule
&AclId=acl-xhwhyuo43l0n*******
&AcrId=acr-u98qztgtgvhb********
&RegionId=cn-hangzhou
&<Common request parameters>
```

Sample success responses

`XML` fomat

```
<ModifyACLRuleResponse>
  <AcrId>acr-u98qztgtgvhb87****</AcrId>
  <GmtCreate>1553777700000</GmtCreate>
  <Direction>out</Direction>
  <Priority>1</Priority>
  <IpProtocol>TCP</IpProtocol>
  <SourceCidr>192.168.1.0/24</SourceCidr>
  <SourcePortRange>1/65535</SourcePortRange>
  <AclId>acl-xhwhyuo43l0n2b****</AclId>
  <Policy>drop</Policy>
  <RequestId>9B0F1C25-389E-4E78-9392-E89F8531F87C</RequestId>
  <DestPortRange>1/65535</DestPortRange>
  <DestCidr>192.168.10.0/24</DestCidr>
</ModifyACLRuleResponse>
```

`JSON` format

```
{
    "AcrId": "acr-u98qztgtgvhb87****", 
    "GmtCreate": 1553777700000, 
    "Direction": "out", 
    "Priority": 1, 
    "IpProtocol": "TCP", 
    "SourceCidr": "192.168.1.0/24", 
    "SourcePortRange": "1/65535", 
    "AclId": "acl-xhwhyuo43l0n2b****", 
    "Policy": "drop", 
    "RequestId": "9B0F1C25-389E-4E78-9392-E89F8531F87C", 
    "DestPortRange": "1/65535", 
    "DestCidr": "192.168.10.0/24"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|403|Forbidden|User not authorized to operate on the specified resource.|The error message returned because you do not have the permissions to manage the specified resource.|
|403|MissingParameter|The input parameter is missing, please check your input.|The error message returned because one or more required parameter are not set. Check whether you have set all required parameters.|
|403|InvalidDescription|Description not valid.|The error message returned because the length of the description exceeds the upper limit.|
|403|InvalidParameter|The specified parameter is invalid.|The error message returned because a parameter is set to an invalid value.|
|403|FeatureNotSupport|The current edition of the smart access gateway does not support this feature.|The error message returned because the current version of the specified SAG instance does not support this feature.|
|403|FeatureNotSupportForActiveSmartAG|The current edition of the active smart access gateway does not support this feature.|The error message returned because the current version of the active SAG device does not support this feature.|
|403|FeatureNotSupportForStandBySmartAG|The current edition of the standby smart access gateway does not support this feature.|The error message returned because the current version of the standby SAG device does not support this feature.|
|403|NotSupportedProtocol|The specified protocol of the ACL rule is not supported.|The error message returned because the specified protocol type of the ACL rule is not supported.|
|403|InvalidId.ACL|The specified ACL ID is invalid.|The error message returned because the specified ACL ID is invalid.|
|403|InvalidId.ACR|The specified ACL rule ID is invalid.|The error message returned because the specified ACL rule ID is invalid.|
|403|InvalidPortRange|The specified port range is invalid.|The error message returned because the specified port range is invalid.|
|403|InternalError|An internal server error occurred.|The error message returned because an internal server error occurred.|
|400|ACL.NoSupportWanType|An SAG 1000 device does not support a WAN ACL.|The error message returned because an SAG-1000 device does not support WAN ACL rules.|
|400|ACL.InvalidType|The specified ACL type is invalid.|The error message returned because the specified ACL rule type is invalid.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

