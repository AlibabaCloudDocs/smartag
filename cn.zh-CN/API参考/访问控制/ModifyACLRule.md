# ModifyACLRule {#doc_api_Smartag_ModifyACLRule .reference}

调用ModifyACLRule修改访问控制规则。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=ModifyACLRule&type=RPC&version=2018-03-13)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|AclId|String|是|acl-xhwhyuo43l0n\*\*\*\*\*\*\*|需要修改的访问控制ID。

 |
|AcrId|String|是|acr-u98qztgtgvhb\*\*\*\*\*\*\*\*|需要修改的访问控制规则ID。

 |
|RegionId|String|是|cn-hangzhou|地域ID。

 |
|Action|String|否|ModifyACLRule|要执行的操作。

 取值：**ModifyACLRule**

 |
|Description|String|否|test|规则描述信息，长度为1~512个字符。

 |
|DestCidr|String|否|0.0.0.0/0|目的地址，CIDR格式和IPv4格式的IP地址范围。

 默认值：**0.0.0.0/0**

 |
|DestPortRange|String|否|80/80|目的端口范围，80/80。

 |
|Direction|String|否|in|规则方向。

 取值：**in|out**

 |
|IpProtocol|String|否|tcp|协议，不区分大小写。

 |
|Policy|String|否|accept|访问权限：**accept|drop**

 |
|Priority|Integer|否|2|优先级，取值范围：1~100

 默认值：1

 |
|SourceCidr|String|否|0.0.0.0/0|源地址，CIDR格式和IPv4格式的IP地址范围。

 默认值：**0.0.0.0/0**

 |
|SourcePortRange|String|否|80/80|源端口范围，80/80。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|AclId|String|acl-xhwhyuo43l0n\*\*\*\*\*\*|修改访问控制规则的访问控制ID。

 |
|AcrId|String|acr-u98qztgtgvhb8\*\*\*\*\*\*|修改的访问控制规则ID。

 |
|Description|String|test|规则描述信息，长度为1~512个字符。

 |
|DestCidr|String|0.0.0.0/|目的地址，CIDR格式和IPv4格式的IP地址范围。

 默认值：**0.0.0.0/0**

 |
|DestPortRange|String|80/80|目的端口范围，80/80。

 |
|Direction|String|in|规则方向，取值：**in|out**

 |
|GmtCreate|Long|1553777700000|规则创建时间Long型时间戳，优先级相同时，小时间戳先生效。

 |
|IpProtocol|String|tcp|协议，不区分大小写。

 |
|Policy|String|drop|访问权限：**accept|drop**

 |
|Priority|Integer|2|优先级，取值范围：1~100

 默认值：1

 |
|RequestId|String|9B0F1C25-389E-4E78-9392-E89F8531F87C|请求ID。

 |
|SourceCidr|String|0.0.0.0/|源地址，CIDR格式和IPv4格式的IP地址范围。

 默认值：**0.0.0.0/0**

 |
|SourcePortRange|String|80/80|源端口范围，80/80。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?AclId=acl-xhwhyuo43l0n*******
&AcrId=acr-u98qztgtgvhb********
&RegionId=cn-hangzhou
&<公共请求参数>

```

正常返回示例

`XML` 格式

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

`JSON` 格式

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
|403|InvalidId.ACR|The specified ACL rule ID is invalid.|您输入的ACL规则ID无效|
|403|InvalidPortRange|The specified port range is invalid.|您输入的端口范围不合法|
|403|InternalError|An internal server error occurred.|内部服务错误|

访问[错误中心](https://error-center.aliyun.com/status/product/Smartag)查看更多错误码。

