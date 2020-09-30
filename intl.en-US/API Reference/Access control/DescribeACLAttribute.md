# DescribeACLAttribute

You can call this operation to query multiple access control list \(ACL\) rules in an ACL.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=DescribeACLAttribute&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|DescribeACLAttribute|The operation that you want to perform.

 Set the value to **DescribeACLAttribute**. |
|AclId|String|Yes|acl-ohlexqptfhy\*\*\*\*\*\*|The ID of the ACL. |
|RegionId|String|Yes|cn-hangzhou|The ID of the region to which the ACL belongs. |
|PageSize|Integer|No|10|The number of entries returned on each page. Maximum value: **50**. Default value: **10**. |
|PageNumber|Integer|No|2|The number of the page to return. Pages start from page 1. Default value: **1**. |
|Direction|String|No|out|Specifies whether the ACL rule controls inbound or outbound access requests.

 Valid values: **in or out**. |
|Order|String|No|1255444444|The ID of the order. |
|Name|String|No|doctest|The name of the ACL to be queried.

 The name must be 2 to 100 characters in length, and can contain digits, periods \(.\), underscores \(\_\), and hyphens \(-\). It must start with a letter or Chinese character. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|8F62CE77-FBA2-4F8D-AED9-0A02814EDA69|The ID of the request. |
|TotalCount|Integer|3|The total number of entries returned. |
|PageNumber|Integer|1|The number of the page to return. Pages start from page 1. Default value: **1**. |
|PageSize|Integer|10|The number of entries returned per page. |
|Acrs|Array| |The ACL rule information returned. |
|AcrId|String|acr-gxzxj5w9qqdf1cxxxx|The ID of the ACL rule. |
|Description|String|The ACL rule|The description of the ACL rule. The description must be **1 to 512** characters in length. |
|Direction|String|out|Specifies whether the ACL rule controls inbound or outbound access requests.

 Valid values: **in or out**. |
|SourceCidr|String|0.0.0.0/0|The source IP address range specified in the ACL rule. CIDR blocks and IPv4 addresses are supported.

 Default value: **0.0.0.0/0**. |
|DestCidr|String|0.0.0.0/0|The destination IP address range specified in the ACL rule. CIDR blocks and IPv4 addresses are supported.

 Default value: **0.0.0.0/0**. |
|IpProtocol|String|UDP|The User Datagram Protocol \(UDP\). The value is not case-sensitive. |
|SourcePortRange|String|30000/40000|The range of the source port. |
|DestPortRange|String|10000/20000|The range of the destination port. |
|Policy|String|drop|Access permissions:

 -   **accept**: access permissions granted.
-   **drop**: access permissions denied. |
|Priority|Integer|70|The priority of the ACL rule.

 Valid values: **1 to 100**. Default value: **1**. |
|GmtCreate|Long|1580821597000|The time when the ACL rule was created. It is a long type timestamp. When timestamps are assigned the same priority, the timestamp with the smallest value prevails. |
|AclId|String|acl-7louazbja80bmgxxxx|The ID of the ACL. |
|Type|String|WAN|The type of the ACL rule:

 -   **LAN**: private networks.
-   **WAN**: public networks. |
|Name|String|doctest|The name of the ACL rule.

 The name must be 2 to 100 characters in length, and can contain digits, periods \(.\), underscores \(\_\), and hyphens \(-\). It must start with a letter or Chinese character. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=DescribeACLAttribute
&AclId=acl-ohlexqptfhy******
&RegionId=cn-hangzhou
&<Common request parameter>
```

Sample success responses

`XML` format

```
<DescribeACLAttribute>
  <PageNumber>1</PageNumber>
  <Acrs>
        <Acr>
              <IpProtocol>TCP</IpProtocol>
              <SourceCidr>10.10.3.0/24</SourceCidr>
              <SourcePortRange>1/65535</SourcePortRange>
              <AclId>acl-7louazbja80bmgxxxx</AclId>
              <AcrId>acr-yjf99p2ffhw6cvxxxx</AcrId>
              <Type>WAN</Type>
              <Policy>drop</Policy>
              <DestPortRange>15000/15000</DestPortRange>
              <DestCidr>39.104.89.0/24</DestCidr>
              <GmtCreate>1580821598000</GmtCreate>
              <Direction>out</Direction>
              <Priority>49</Priority>
        </Acr>
        <Acr>
              <IpProtocol>TCP</IpProtocol>
              <SourceCidr>0.0.0.0/0</SourceCidr>
              <SourcePortRange>1/65535</SourcePortRange>
              <AclId>acl-7louazbja80bmgxxxx</AclId>
              <AcrId>acr-8jety1pnvardayxxxx</AcrId>
              <Type>WAN</Type>
              <Policy>accept</Policy>
              <DestPortRange>1/65535</DestPortRange>
              <DestCidr>0.0.0.0/0</DestCidr>
              <GmtCreate>1580821597000</GmtCreate>
              <Direction>out</Direction>
              <Priority>50</Priority>
        </Acr>
        <Acr>
              <IpProtocol>UDP</IpProtocol>
              <SourceCidr>0.0.0.0/0</SourceCidr>
              <SourcePortRange>30000/40000</SourcePortRange>
              <AclId>acl-7louazbja80bmgxxxx</AclId>
              <AcrId>acr-gxzxj5w9qqdf1cxxxx</AcrId>
              <Type>WAN</Type>
              <Policy>drop</Policy>
              <DestPortRange>10000/20000</DestPortRange>
              <DestCidr>0.0.0.0/0</DestCidr>
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
				"SourceCidr": "10.10.3.0/24",
				"SourcePortRange": "1/65535",
				"AclId": "acl-7louazbja80bmgxxxx",
				"AcrId": "acr-yjf99p2ffhw6cvxxxx",
				"Type": "WAN",
				"Policy": "drop",
				"DestPortRange": "15000/15000",
				"DestCidr": "39.104.89.0/24",
				"GmtCreate": 1580821598000,
				"Direction": "out",
				"Priority": 49
			},
			{
				"IpProtocol": "TCP",
				"SourceCidr": "0.0.0.0/0",
				"SourcePortRange": "1/65535",
				"AclId": "acl-7louazbja80bmgxxxx",
				"AcrId": "acr-8jety1pnvardayxxxx",
				"Type": "WAN",
				"Policy": "accept",
				"DestPortRange": "1/65535",
				"DestCidr": "0.0.0.0/0",
				"GmtCreate": 1580821597000,
				"Direction": "out",
				"Priority": 50
			},
			{
				"IpProtocol": "UDP",
				"SourceCidr": "0.0.0.0/0",
				"SourcePortRange": "30000/40000",
				"AclId": "acl-7louazbja80bmgxxxx",
				"AcrId": "acr-gxzxj5w9qqdf1cxxxx",
				"Type": "WAN",
				"Policy": "drop",
				"DestPortRange": "10000/20000",
				"DestCidr": "0.0.0.0/0",
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
|403|Forbidden|User not authorized to operate on the specified resource.|The error code returned because you do not have the permission to manage the resource.|
|403|MissingParameter|The input parameter is missing, please check your input.|The error code returned because a request parameter is not set. Check the request parameters.|
|403|InvalidParameter|The specified parameter is invalid.|The error code returned because a specified parameter is invalid.|
|403|InvalidId.ACL|The specified ACL ID is invalid.|The error code returned because the specified ACL ID is invalid.|
|403|InternalError|An internal server error occurred.|The error code returned because an internal server error occurred.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

