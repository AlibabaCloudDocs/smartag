# ModifyACLRule {#doc_api_Smartag_ModifyACLRule .reference}

Modifies an Access Control List \(ACL\) rule.

## Debug {#apiExplorer .section}

By using [API Explorer](https://api.aliyun.com/#product=Smartag&api=CreateACL) ,you can easily debug APIs, automatically generate SDK code examples, and quickly search for APIs.

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|Action|String|No|ModifyACLRule| The name of this action.

 Value: **ModifyACLRule**

 |
|AclId|String|Yes|acl-xhwhyuo43l0n\*\*\*\*\*\*\*| The ID of the ACL.

 |
|AcrId|String|Yes|acr-u98qztgtgvhb\*\*\*\*\*\*\*\*| The ID of the ACL rule.

 |
|RegionId|String|Yes|cn-hangzhou| The ID of the region to which the ACL rule belongs.

 |
|Description|String|No|test|The description of the ACL rule. It must be 1 to 512 characters in length.|
|DestCidr|String|No|0.0.0.0/0|The destination address. It is an IPv4 address range in CIDR format. Default value: 0.0.0.0/0 |
|DestPortRange|String|No|80/80|The range of the destination port. Valid value: 80/80.|
|Direction|String|No|in|The direction of the ACL rule. Valid values: in|out|
|IpProtocol|String|No|tcp| The protocol used by the ACL rule. The value is not case sensitive.

 |
|Policy|String|No|accept| The policy used by the ACL rule. Valid values: accept|drop

 |
|Priority|Integer|No|2| The priority of the ACL rule. Value range: 1 to 100.

 Default value: 1

 |
|SourceCidr|String|No|0.0.0.0/0|The source address. It is an IPv4 address range in CIDR format. Default value: 0.0.0.0/0 |
|SourcePortRange|String|No|80/80|The range of the source port. Valid value: 80/80|

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|AclId|String|acl-xhwhyuo43l0n\*\*\*\*\*\*| The ID of the ACL to which the ACL rule belongs.

 |
|AcrId|String|acr-u98qztgtgvhb8\*\*\*\*\*\*| The ID of the ACL rule to be modified.

 |
|Description|String|test|The description of the ACL rule. It must be 1 to 512 characters in length.|
|DestCidr|String|0.0.0.0/| The destination address. It is an IPv4 address range in the CIDR format.

 Default value: 0.0.0.0/0 

 |
|DestPortRange|String|80/80| The range of the destination port. Valid value: 80/80

 |
|Direction|String|in| The direction of the ACL rule.

 Valid values: in|out

 |
|GmtCreate|Long|1553777700000| The time at which the ACL rule was created. It is a long type timestamp. When the priority is the same, the smaller timestamp takes effect.

 |
|IpProtocol|String|tcp| The protocol used by the ACL rule. This value is not case sensitive.

 |
|Policy|String|drop| The policy used by the ACL rule. Valid values: accept|drop

 |
|Priority|Integer|2|The priority of the ACL rule. Value range: 1 to 100. Default value: 1.|
|RequestId|String|9B0F1C25-389E-4E78-9392-E89F8531F87C| The ID of the request.

 |
|SourceCidr|String|0.0.0.0/|The source address. It is an IPv4 address range in the CIDR format. Default value: 0.0.0.0/0 |
|SourcePortRange|String|80/80| The range of the source port. Valid value: 80/80

 |

## Examples {#demo .section}

**Request example**

``` {#request_demo}

http(s)://[Endpoint]/?AclId=acl-xhwhyuo43l0n*******
&AcrId=acr-u98qztgtgvhb********
&RegionId=cn-hangzhou
&<CommonParameters>

```

**Response example**

`XML` format

``` {#xml_return_success_demo}
<ModifyACLRule>
  <AcrId>acr-u98qztgtgvhb87nsls</AcrId>
  <GmtCreate>1553777700000</GmtCreate>
  <Direction>out</Direction>
  <Priority>1</Priority>
  <IpProtocol>TCP</IpProtocol>
  <SourceCidr>192.168.3.0/24</SourceCidr>
  <SourcePortRange>1/65535</SourcePortRange>
  <AclId>acl-xhwhyuo43l0n2b832u</AclId>
  <Policy>drop</Policy>
  <RequestId>9B0F1C25-389E-4E78-9392-E89F8531F87C</RequestId>
  <DestPortRange>1/65535</DestPortRange>
  <DestCidr>10.0.0.1/32</DestCidr>
</ModifyACLRule>

```

`JSON` format

``` {#json_return_success_demo}
{
	"IpProtocol":"TCP",
	"SourceCidr":"192.168.3.0/24",
	"SourcePortRange":"1/65535",
	"AclId":"acl-xhwhyuo43l0n2b832u",
	"AcrId":"acr-u98qztgtgvhb87nsls",
	"Policy":"drop",
	"RequestId":"9B0F1C25-389E-4E78-9392-E89F8531F87C",
	"DestPortRange":"1/65535",
	"DestCidr":"10.0.0.1/32",
	"GmtCreate":1553777700000,
	"Direction":"out",
	"Priority":1
}
```

## Error codes { .section}

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
|403|InvalidId.ACR|The specified ACL rule ID is invalid.|The specified ACL rule ID is invalid.|
|403|InvalidPortRange|The specified port range is invalid.|The specified port range is invalid.|
|403|InternalError|An internal server error occurred.|An internal server error has occured.|

[See common error codes](https://error-center.aliyun.com/status/product/Smartag)

