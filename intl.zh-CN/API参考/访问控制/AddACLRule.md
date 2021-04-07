# AddACLRule

调用AddACLRule添加访问控制规则。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=AddACLRule&type=RPC&version=2018-03-13)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|AddACLRule|要执行的操作。

 取值：**AddACLRule**。 |
|AclId|String|是|acl-xhwhyuo43l0n\*\*\*\*\*|访问控制实例ID。 |
|DestCidr|String|是|192.168.10.0/24|目的网段。

 目的网段格式为CIDR格式。例如：192.168.10.0/24。 |
|DestPortRange|String|是|1/200|目的端口范围。

 取值范围：**-1**或**1**~**65535**。

 目的端口范围格式例如：1/200、80/80，其中-1/-1代表不限制端口。 |
|Direction|String|是|in|访问控制规则应用方向。取值：

 -   **in**：入方向，指从外部访问智能接入网关实例所在的本地分支的流量。
-   **out**：出方向，指从智能接入网关实例所在的本地分支访问外部的流量。 |
|IpProtocol|String|是|tcp|访问控制规则应用的协议。

 访问控制功能支持的协议类型，请以控制台为准。协议格式不区分大小写。 |
|Policy|String|是|accept|访问控制规则授权策略。取值：

 -   **accept**：允许。
-   **drop**：拒绝。 |
|RegionId|String|是|cn-hangzhou|访问控制实例所属地域ID。 |
|SourceCidr|String|是|192.168.20.0/24|源网段。

 源网段格式为CIDR格式。例如：192.168.1.0/24。 |
|SourcePortRange|String|是|1/200|源端口范围。

 取值范围：**-1**或**1**~**65535**。

 源端口范围格式例如：1/200、80/80，其中-1/-1代表不限制端口。 |
|Description|String|否|test|访问控制规则描述信息。

 描述长度为**1~512**个字符。 |
|Priority|Integer|否|12|访问控制规则优先级。

 数值越小，优先级越高。同优先级时，首先下发到智能接入网关设备的规则优先生效。

 取值范围：**1~100**。默认值：**1**。 |
|Type|String|否|LAN|访问控制规则类型。取值：

 -   **LAN**：（默认值）私网，表示针对私网地址的流量设置访问控制规则。
-   **WAN**：公网，表示针对公网地址的流量设置访问控制规则。 |
|Name|String|否|doctest|访问控制规则名称。

 长度为2~100个字符，以大小写字母或中文开头，可包含数字、半角句号（.）、下划线（\_）和短划线（-）。 |
|DpiSignatureIds.N|RepeatList|否|1|当前访问控制规则匹配的应用ID列表。

 您可以通过[ListDpiSignatures](~~196630~~)查询应用ID及其对应的应用信息。N的最大值为**10**。 |
|DpiGroupIds.N|RepeatList|否|20|当前访问控制规则匹配的应用组ID列表。

 您可以通过[ListDpiGroups](~~196754~~)查询应用组ID及其包含的应用信息。N的最大值为**10**。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|AclId|String|acl-xhwhyuo43l0\*\*\*\*\*\*\*|访问控制实例ID。 |
|AcrId|String|acr-c1hkd054qywi\*\*\*\*\*\*|访问控制规则ID。 |
|Description|String|test|访问控制规则描述信息。 |
|DestCidr|String|192.168.10.0/24|目的网段。

 目的网段格式为CIDR格式。例如：192.168.10.0/24。 |
|DestPortRange|String|1/65535|目的端口范围。 |
|Direction|String|out|访问控制规则应用方向。取值：

 -   **in**：入方向，指从外部访问智能接入网关实例所在的本地分支的流量。
-   **out**：出方向，指从智能接入网关实例所在的本地分支访问外部的流量。 |
|DpiGroupIds|List|20|当前访问控制规则匹配的应用组ID列表。 |
|DpiSignatureIds|List|1|当前访问控制规则匹配的应用ID列表。 |
|GmtCreate|Long|1553766882689|创建访问控制规则时的时间戳。

 时间戳格式为Long型，优先级相同时，时间戳小的访问控制规则优先生效。 |
|IpProtocol|String|TCP|访问控制规则应用的协议。 |
|Name|String|doctest|访问控制规则名称。 |
|Policy|String|drop|访问控制规则授权策略。

 -   **accept**：允许。
-   **drop**：拒绝。 |
|Priority|Integer|1|访问控制规则优先级。

 数值越小，优先级越高。同优先级时，首先下发到智能接入网关设备的规则优先生效。 |
|RequestId|String|880F84CB-9B54-4413-A8A3-8832C82D1BC4|请求ID。 |
|SourceCidr|String|192.168.20.0/24|源网段。

 源网段格式为CIDR格式。例如：192.168.1.0/24。 |
|SourcePortRange|String|1/65535|源端口范围。 |
|Type|String|LAN|访问控制规则类型。

 -   **LAN**：私网，表示针对私网地址的流量设置访问控制规则。
-   **WAN**：公网，表示针对公网地址的流量设置访问控制规则。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=AddACLRule
&AclId=acl-xhwhyuo43l0n*****
&DestCidr=192.168.10.0/24
&DestPortRange=1/200
&Direction=in
&IpProtocol=tcp
&Policy=accept
&RegionId=cn-hangzhou
&SourceCidr=192.168.20.0/24
&SourcePortRange=1/200
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<AddACLRuleResponse>
  <AcrId>acr-c1hkd054qywiw2****</AcrId>
  <Type>LAN</Type>
  <GmtCreate>1553766882689</GmtCreate>
  <Direction>out</Direction>
  <Priority>1</Priority>
  <Name>doctest</Name>
  <IpProtocol>TCP</IpProtocol>
  <SourceCidr>192.168.20.0/24</SourceCidr>
  <SourcePortRange>1/65535</SourcePortRange>
  <AclId>acl-xhwhyuo43l0n2b****</AclId>
  <Policy>drop</Policy>
  <RequestId>880F84CB-9B54-4413-A8A3-8832C82D1BC4</RequestId>
  <DestPortRange>1/65535</DestPortRange>
  <DestCidr>192.168.10.0/24</DestCidr>
</AddACLRuleResponse>
```

`JSON` 格式

```
{
    "AcrId": "acr-c1hkd054qywiw2****", 
    "Type": "LAN",
    "GmtCreate": 1553766882689, 
    "Direction": "out", 
    "Priority": 1, 
    "Name": "doctest",
    "IpProtocol": "TCP", 
    "SourceCidr": "192.168.20.0/24", 
    "SourcePortRange": "1/65535", 
    "AclId": "acl-xhwhyuo43l0n2b****", 
    "Policy": "drop", 
    "RequestId": "880F84CB-9B54-4413-A8A3-8832C82D1BC4", 
    "DestPortRange": "1/65535", 
    "DestCidr": "192.168.10.0/24"
}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|Forbidden|User not authorized to operate on the specified resource.|用户没有操作此资源的权限。|
|403|MissingParameter|The input parameter is missing, please check your input.|输入参数缺失，请检查您的输入。|
|403|InvalidDescription|Description not valid.|详情描述超过长度限制|
|403|InvalidParameter|The specified parameter is invalid.|非法参数。|
|403|FeatureNotSupport|The current edition of the smart access gateway does not support this feature.|智能接入网关当前版本不支持该功能特性。|
|403|FeatureNotSupportForActiveSmartAG|The current edition of the active smart access gateway does not support this feature.|主智能接入网关的当前版本不支持该功能特性。|
|403|FeatureNotSupportForStandBySmartAG|The current edition of the standby smart access gateway does not support this feature.|备智能接入网关的当前版本不支持该功能特性。|
|403|NotSupportedProtocol|The specified protocol of the ACL rule is not supported.|您输入的ACL规则的协议类型是不支持的|
|403|InvalidId.ACL|The specified ACL ID is invalid.|无效的ACL组ID。|
|403|InvalidPortRange|The specified port range is invalid.|您输入的端口范围不合法。|
|403|AcrPerAclAmountLimit|The maximum number of rules in an ACL is exceeded. You can open a ticket to increase the quota.|您创建的ACL规则超出了单个ACL组下规则数量限额，您可以通过工单申请提升限额|
|403|InternalError|An internal server error occurred.|内部服务错误|
|400|ACL.NoSupportWanType|An SAG 1000 device does not support a WAN ACL.|sag-1000类型盒子不支持公网ACL。|
|400|ACL.InvalidType|The specified ACL type is invalid.|非法的ACL类型。|

访问[错误中心](https://error-center.alibabacloud.com/status/product/Smartag)查看更多错误码。

