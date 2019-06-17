# AddACLRule {#doc_api_Smartag_AddACLRule .reference}

Adds an Access Control List \(ACL\) rule.

## Debug {#apiExplorer .section}

By using [OpenAPI Explorer](https://api.aliyun.com/#product=Smartag&api=CreateACL), you can easily debug APIs, automatically generate SDK code examples, and quickly search for APIs.

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|Action|String|No|AddACLRule| The name of this action.

 Value: **AddACLRule**

 |
|AclId|String|Yes|acl-xhwhyuo43l0n\*\*\*\*\*| The ID of the ACL.

 |
|DestCidr|String|Yes|0.0.0.0/0|The destination address. It is an IPv4 address range in CIDR format. Default value: 0.0.0.0/0|
|DestPortRange|String|Yes|10|The range of the destination port. Valid value: 80/80.|
|Direction|String|Yes|in|The direction of the ACL rule. Valid values: in|out|
|IpProtocol|String|Yes|tcp| The protocol used by the ACL rule. The value is not case sensitive.

 |
|Policy|String|Yes|accept| The policy used by the ACL rule. Valid values: accept|drop

 |
|RegionId|String|Yes|cn-hangzhou| The ID of the region to which the ACL rule belongs.

 |
|SourceCidr|String|Yes|0.0.0.0/0|The source address. It is an IPv4 address range in the CIDR format. Default value: 0.0.0.0/0|
|SourcePortRange|String|Yes|20|The range of the source port. Valid value: 80/80|
|Description|String|No|test|The description of the ACL rule. It must be 1 to 512 characters in length.|
|Priority|Integer|No|12| The priority of the ACL rule. Value range: 1 to 100.

 Default value: 1

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|AclId|String|acl-xhwhyuo43l0\*\*\*\*\*\*\*| The ID of the ACL.

 |
|AcrId|String|acr-c1hkd054qywi\*\*\*\*\*\*| The ID of the ACL rule.

 |
|Description|String|3|The description of the ACL rule. It must be 1 to 512 characters in length.|
|DestCidr|String|0.0.0.0/0| The destination address. It is an IPv4 address range in the CIDR format.

 Default value: 0.0.0.0/0

 |
|DestPortRange|String|80/80| The range of the destination port. Valid value: 80/80

 |
|Direction|String|in| The direction of the ACL rule.

 Valid values: in|out

 |
|GmtCreate|Long|1553766882689| The time at which the ACL rule was created. It is a long type timestamp. When the priority is the same, the smaller timestamp takes effect.

 |
|IpProtocol|String|tcp| The protocol used by the ACL rule. It is not case sensitive.

 |
|Policy|String|accept| The policy used by the ACL rule. Valid values: accept|drop

 |
|Priority|Integer|23|The priority of the ACL rule. Value range: 1 to 100. Default value: 1.|
|RequestId|String|880F84CB-9B54-4413-A8A3-8832C82D1BC4| The ID of the request.

 |
|SourceCidr|String|0.0.0.0/0|The source address. It is an IPv4 address range in the CIDR format. Default value: 0.0.0.0/0|
|SourcePortRange|String|80/80| The range of the source port. Valid value: 80/80

 |

## Examples {#demo .section}

 **Request example** 

``` {#request_demo}

http(s)://[Endpoint]/?AclId=acl-xhwhyuo43l0n*****
&DestCidr=0.0.0.0/0
&DestPortRange=10
&Direction=in
&IpProtocol=tcp
&Policy=accept
&RegionId=cn-hangzhou
&SourceCidr=0.0.0.0/0
&SourcePortRange=20
&<CommonParameters>

```

 **Response example** 

`XML` format

``` {#xml_return_success_demo}
<AddACLRule>
  <AcrId>acr-c1hkd054qywiw21ef3</AcrId>
  <GmtCreate>1553766882689</GmtCreate>
  <Direction>out</Direction>
  <Priority>1</Priority>
  <IpProtocol>TCP</IpProtocol>
  <SourceCidr>192.168.3.0/24</SourceCidr>
  <SourcePortRange>1/65535</SourcePortRange>
  <AclId>acl-xhwhyuo43l0n2b832u</AclId>
  <Policy>drop</Policy>
  <RequestId>880F84CB-9B54-4413-A8A3-8832C82D1BC4</RequestId>
  <DestPortRange>1/65535</DestPortRange>
  <DestCidr>10.0.0.1/32</DestCidr>
</AddACLRule>

```

`JSON` format

``` {#json_return_success_demo}
{
	"IpProtocol":"TCP",
	"SourceCidr":"192.168.3.0/24",
	"SourcePortRange":"1/65535",
	"AclId":"acl-xhwhyuo43l0n2b832u",
	"AcrId":"acr-c1hkd054qywiw21ef3",
	"Policy":"drop",
	"RequestId":"880F84CB-9B54-4413-A8A3-8832C82D1BC4",
	"DestPortRange":"1/65535",
	"DestCidr":"10.0.0.1/32",
	"GmtCreate":1553766882689,
	"Direction":"out",
	"Priority":1
}
```

## Error codes {#section_239_91d_flb .section}

|HTTP status code|Error code|Error message|Description|
|----------------|----------|-------------|-----------|
|403|Forbidden|User not authorized to operate on the specified resource.|You are not authorized to operate on this resource.|
|403|MissingParameter|The input parameter is missing, please check your input.|The input parameter is missing. Please check your input.|
|403|InvalidDescription|Description not valid.|The length of the description has exceeded the limit.|
|403|InvalidParameter|The specified parameter is invalid.|The specified parameter is invalid.|
|403|FeatureNotSupport|The current edition of the smart access gateway does not support this feature.|The current version of the Smart Access Gateway device does not support this feature.|
|403|FeatureNotSupportForActiveSmartAG|The current edition of the active smart access gateway does not support this feature.|The current version of the active Smart Access Gateway device does not support this feature.|
|403|FeatureNotSupportForStandBySmartAG|The current edition of the standby smart access gateway does not support this feature.|The current version of the standby Smart Access Gateway device does not support this feature.|
|403|NotSupportedProtocol|The specified protocol of the ACL rule is not supported.|The specified protocol of the ACL rule is not supported.|
|403|InvalidId.ACL|The specified ACL ID is invalid.|The specified ACL ID is invalid.|
|403|InvalidPortRange|The specified port range is invalid.|The specified port range is invalid.|
|403|AcrPerAclAmountLimit|The maximum number of rules in an ACL is exceeded. You can open a ticket to increase the quota.|The quota for ACL rules that can be added to an ACL has been reached. To increase the quota, open a ticket.|
|403|InternalError|An internal server error occurred.|An internal server error has occured.|

[See common error codes](https://error-center.aliyun.com/status/product/Smartag)

