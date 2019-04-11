# AddACLRule {#doc_api_Smartag_AddACLRule .reference}

调用AddACLRule添加访问控制规则。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Smartag&api=AddACLRule)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|AclId|String|是|acl-xhwhyuo43l0n\*\*\*\*\*|访问控制ID。

 |
|DestCidr|String|是|0.0.0.0/0|目的地址，CIDR 格式和 IPv4 格式的IP地址范围。

 默认值：0.0.0.0/0

 |
|DestPortRange|String|是|10|目的端口范围，80/80。

 |
|Direction|String|是|in|规则方向。

 取值：**in|out**

 |
|IpProtocol|String|是|tcp|协议，不区分大小写。

 |
|Policy|String|是|accept|访问权限：**accept|drop**

 |
|RegionId|String|是|cn-hangzhou|地域ID。

 |
|SourceCidr|String|是|0.0.0.0/0|源地址，CIDR 格式和IPv4格式的IP地址范围。

 默认值：**0.0.0.0/0**

 |
|SourcePortRange|String|是|20|源端口范围，80/80。

 |
|Action|String|否|AddACLRule|要执行的操作。

 取值：**AddACLRule**

 |
|Description|String|否|test|规则描述信息，长度为1~512个字符。

 |
|Priority|Integer|否|12|优先级，取值范围：**1~100**。

 默认值：1

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|AclId|String|acl-xhwhyuo43l0\*\*\*\*\*\*\*|访问控制ID。

 |
|AcrId|String|acr-c1hkd054qywi\*\*\*\*\*\*|访问控制规则ID。

 |
|Description|String|3|规则描述信息，长度为**1~512**个字符。

 |
|DestCidr|String|0.0.0.0/0|目的地址，CIDR格式和IPv4格式的IP地址范围。

 默认值：**0.0.0.0/0**

 |
|DestPortRange|String|80/80|目的端口范围，80/80。

 |
|Direction|String|in|规则方向。

 取值：**in|out**

 |
|GmtCreate|Long|1553766882689|规则创建时间Long型时间戳，优先级相同时，小时间戳先生效。

 |
|IpProtocol|String|tcp|协议，不区分大小写。

 |
|Policy|String|accept|访问权限：**accept|drop**

 |
|Priority|Integer|23|优先级，取值范围：1~100。

 默认值：1。

 |
|RequestId|String|880F84CB-9B54-4413-A8A3-8832C82D1BC4|请求ID。

 |
|SourceCidr|String|0.0.0.0/0|源地址，CIDR 格式和IPv4格式的IP地址范围。

 默认值：**0.0.0.0/0**

 |
|SourcePortRange|String|80/80|源端口范围，80/80。

 |

## 示例 {#demo .section}

请求示例

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
&<公共请求参数>

```

正常返回示例

`XML` 格式

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

`JSON` 格式

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

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|Forbidden|User not authorized to operate on the specified resource.|用户没有操作此资源的权限|
|403|MissingParameter|The input parameter is missing, please check your input.|输入参数缺失，请检查您的输入|
|403|InvalidDescription|Description not valid.|详情描述超过长度限制|
|403|InvalidParameter|The specified parameter is invalid.|非法参数|
|403|FeatureNotSupport|The current edition of the smart access gateway does not support this feature.|智能接入网关当前版本不支持该功能特性|
|403|FeatureNotSupportForActiveSmartAG|The current edition of the active smart access gateway does not support this feature.|主智能接入网关的当前版本不支持该功能特性|
|403|FeatureNotSupportForStandBySmartAG|The current edition of the standby smart access gateway does not support this feature.|备智能接入网关的当前版本不支持该功能特性|
|403|NotSupportedProtocol|The specified protocol of the ACL rule is not supported.|您输入的ACL规则的协议类型是不支持的|
|403|InvalidId.ACL|The specified ACL ID is invalid.|无效的ACL组ID|
|403|InvalidPortRange|The specified port range is invalid.|您输入的端口范围不合法|
|403|AcrPerAclAmountLimit|The maximum number of rules in an ACL is exceeded. You can open a ticket to increase the quota.|您创建的ACL规则超出了单个ACL组下规则数量限额，您可以通过工单申请提升限额|
|403|InternalError|An internal server error occurred.|内部服务错误|

[查看本产品错误码](https://error-center.aliyun.com/status/product/Smartag)

