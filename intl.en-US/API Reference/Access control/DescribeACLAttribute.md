# DescribeACLAttribute

Queries an access control list \(ACL\).

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=DescribeACLAttribute&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|DescribeACLAttribute|The operation that you want to perform.

 Set the value to **DescribeACLAttribute**. |
|AclId|String|Yes|acl-ohlexqptfhy\*\*\*\*\*\*|The ID of the ACL. |
|RegionId|String|Yes|cn-hangzhou|The ID of the region where the ACL is deployed. |
|PageSize|Integer|No|10|The number of entries to return on each page.

 Valid values: **1** to **50**.

 Default value: **10**. |
|PageNumber|Integer|No|1|The number of the page to return. Default value: **1**. |
|Direction|String|No|out|The direction in which the ACL rule is applied. Valid values:

 -   **in**: The ACL rule controls inbound network traffic of the on-premises network that is associated with the SAG instance.
-   **out**: The ACL rule controls outbound network traffic of the on-premises network that is associated with the SAG instance. |
|Order|String|No|1255444444|The ID of the order. |
|Name|String|No|doctest|The name of the ACL.

 The name must be 2 to 100 characters in length, and can contain digits, periods \(.\), underscores \(\_\), and hyphens \(-\). It must start with a letter. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Acrs|Array of Acr| |The information about the ACL rules that belong to the ACL. |
|Acr| | | |
|AclId|String|acl-7louazbja80bmgxxxx|The ID of the ACL. |
|AcrId|String|acr-gxzxj5w9qqdf1cxxxx|The ID of the ACL rule. |
|Description|String|Description|The description of the ACL rule.

 The description must be **1 to 512** characters in length. |
|DestCidr|String|0.0.0.0/0|The range of the destination IP addresses.

 Set this parameter in CIDR notation. Example: 192.168.10.0/24. |
|DestPortRange|String|10000/20000|The range of the destination ports.

 Valid values: **-1** and **1** to **65535**.

 Set the destination port range in one of the following formats: 1/200 or 80/80. A value of -1/-1 indicates that all ports are available. |
|Direction|String|out|The direction in which the ACL rule is applied. Valid values:

 -   **in**: The ACL rule controls inbound network traffic of the on-premises network that is associated with the SAG instance.
-   **out**: The ACL rule controls outbound network traffic of the on-premises network that is associated with the SAG instance. |
|DpiGroupIds|List|20|The IDs of application groups that match the current ACL rule.

 You can call the [ListDpiGroups](~~196754~~) operation to query application group IDs and information. |
|DpiSignatureIds|List|1|The IDs of applications that match the current ACL rule.

 You can call the [ListDpiSignatures](~~196630~~) operation to query application IDs and information. |
|GmtCreate|Long|1580821597000|The timestamp when the ACL rule was created.

 The timestamp is in Long format. If ACL rules have the same priority, the one with the smallest timestamp prevails. |
|IpProtocol|String|UDP|The protocol that is applied to the ACL rule.

 The supported protocols provided in this topic are for reference only. The actual protocols in the SAG console shall prevail. The value is not case-sensitive. |
|Name|String|doctest|The name of the ACL.

 The name must be 2 to 100 characters in length, and can contain digits, periods \(.\), underscores \(\_\), and hyphens \(-\). It must start with a letter. |
|Policy|String|drop|The action policy of the ACL rule. Valid values:

 -   **accept**: allows the network traffic.
-   **drop**: blocks the network traffic. |
|Priority|Integer|70|The priority of the ACL rule.

 Valid values:**1 to 100**. |
|SourceCidr|String|0.0.0.0/0|The range of the source IP addresses.

 Set this parameter in CIDR notation. Example: 192.168.1.0/24. |
|SourcePortRange|String|30000/40000|The range of the source ports.

 Valid values: **-1** and **1** to **65535**.

 Set the destination port range in one of the following formats: 1/200 or 80/80. A value of -1/-1 indicates that all ports are available. |
|Type|String|WAN|The type of the ACL rule:

 -   **LAN**: The ACL rule controls traffic of private IP addresses.
-   **WAN**: The ACL rule controls traffic of public IP addresses. |
|PageNumber|Integer|1|The page number of the returned page. |
|PageSize|Integer|10|The number of entries returned per page. |
|RequestId|String|8F62CE77-FBA2-4F8D-AED9-0A02814EDA69|The ID of the request. |
|TotalCount|Integer|3|The total number of entries returned. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=DescribeACLAttribute
&AclId=acl-ohlexqptfhy******
&RegionId=cn-hangzhou
&<Common request parameters>
```

Sample success responses

`XML` fomat

```
<DescribeACLAttribute>
  <PageNumber>1</PageNumber>
  <Acrs>
        <Acr>
              <IpProtocol>TCP</IpProtocol>
              <SourceCidr>10.XX.XX.0/24</SourceCidr>
              <SourcePortRange>1/65535</SourcePortRange>
              <AclId>acl-7louazbja80bmg****</AclId>
              <AcrId>acr-yjf99p2ffhw6cv****</AcrId>
              <Type>WAN</Type>
              <Policy>drop</Policy>
              <DestPortRange>15000/15000</DestPortRange>
              <DestCidr>39.XX.XX.0/24</DestCidr>
              <GmtCreate>1580821598000</GmtCreate>
              <Direction>out</Direction>
              <Priority>49</Priority>
        </Acr>
        <Acr>
              <IpProtocol>TCP</IpProtocol>
              <SourceCidr>11.XX.XX.0/8</SourceCidr>
              <SourcePortRange>1/65535</SourcePortRange>
              <AclId>acl-7louazbja80bmg****</AclId>
              <AcrId>acr-8jety1pnvarday****</AcrId>
              <Type>WAN</Type>
              <Policy>accept</Policy>
              <DestPortRange>1/65535</DestPortRange>
              <DestCidr>12.XX.XX.0/8</DestCidr>
              <GmtCreate>1580821597000</GmtCreate>
              <Direction>out</Direction>
              <Priority>50</Priority>
        </Acr>
        <Acr>
              <IpProtocol>UDP</IpProtocol>
              <SourceCidr>0.0.0.0/0</SourceCidr>
              <SourcePortRange>30000/40000</SourcePortRange>
              <AclId>acl-7louazbja80bmg****</AclId>
              <AcrId>acr-gxzxj5w9qqdf1c****</AcrId>
              <Type>WAN</Type>
              <Policy>drop</Policy>
              <DestPortRange>10000/20000</DestPortRange>
              <DestCidr>12.XX.XX.0/8</DestCidr>
              <GmtCreate>1580821597000</GmtCreate>
              <Direction>out</Direction>
              <Priority>70</Priority>
        </Acr>
  </Acrs>
  <TotalCount>3</TotalCount>
  <PageSize>10</PageSize>
  <RequestId>8F62CE77-FBA2-4F8D-AED9-0A02814EDA69</RequestId>
</DescribeACLAttribute>
```

`JSON` format

```
{
	"PageNumber": 1,
	"Acrs": {
		"Acr": [
			{
				"IpProtocol": "TCP",
				"SourceCidr": "10.XX.XX.0/24",
				"SourcePortRange": "1/65535",
				"AclId": "acl-7louazbja80bmg****",
				"AcrId": "acr-yjf99p2ffhw6cv****",
				"Type": "WAN",
				"Policy": "drop",
				"DestPortRange": "15000/15000",
				"DestCidr": "39.XX.XX.0/24",
				"GmtCreate": 1580821598000,
				"Direction": "out",
				"Priority": 49
			},
			{
				"IpProtocol": "TCP",
				"SourceCidr": "11.XX.XX.0/8",
				"SourcePortRange": "1/65535",
				"AclId": "acl-7louazbja80bmg****",
				"AcrId": "acr-8jety1pnvarday****",
				"Type": "WAN",
				"Policy": "accept",
				"DestPortRange": "1/65535",
				"DestCidr": "12.XX.XX.0/8",
				"GmtCreate": 1580821597000,
				"Direction": "out",
				"Priority": 50
			},
			{
				"IpProtocol": "UDP",
				"SourceCidr": "0.0.0.0/0",
				"SourcePortRange": "30000/40000",
				"AclId": "acl-7louazbja80bmg****",
				"AcrId": "acr-gxzxj5w9qqdf1c****",
				"Type": "WAN",
				"Policy": "drop",
				"DestPortRange": "10000/20000",
				"DestCidr": "12.XX.XX.0/8",
				"GmtCreate": 1580821597000,
				"Direction": "out",
				"Priority": 70
			}
		]
	},
	"TotalCount": 3,
	"PageSize": 10,
	"RequestId": "8F62CE77-FBA2-4F8D-AED9-0A02814EDA69"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|403|Forbidden|User not authorized to operate on the specified resource.|The error message returned because you do not have the permissions to manage the specified resource.|
|403|MissingParameter|The input parameter is missing, please check your input.|The error message returned because one or more required parameters are not set. Check whether you have set all required parameters.|
|403|InvalidParameter|The specified parameter is invalid.|The error message returned because a parameter is set to an invalid value.|
|403|InvalidId.ACL|The specified ACL ID is invalid.|The error message returned because the specified ACL ID is invalid.|
|403|InternalError|An internal server error occurred.|The error message returned because an internal server error occurred.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

