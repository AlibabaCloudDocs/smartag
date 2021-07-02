# ModifyACLRule

调用ModifyACLRule接口修改访问控制规则。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=ModifyACLRule&type=RPC&version=2018-03-13)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|ModifyACLRule|要执行的操作。取值：**ModifyACLRule**。 |
|RegionId|String|是|cn-shanghai|访问控制实例所属地域ID。 |
|AclId|String|是|acl-xhwhyuo43l0n\*\*\*\*\*\*\*|访问控制实例ID。 |
|AcrId|String|是|acr-u98qztgtgvhb\*\*\*\*\*\*\*\*|访问控制规则ID。

 您可以通过调用接口[DescribeACLAttribute](~~114017~~)查询访问控制实例下访问控制规则的ID。 |
|Description|String|否|test|访问控制规则的描述信息。

 描述长度为**1**~**512**个字符。 |
|Direction|String|否|in|访问控制规则应用方向。取值：

 -   **in**：入方向，指从外部访问智能接入网关实例所在的本地网络的方向。
-   **out**：出方向，指从智能接入网关实例所在的本地网络访问外部的方向。 |
|SourceCidr|String|否|0.0.0.0/0|源网段。

 源网段格式为CIDR格式。例如：192.168.1.0/24。 |
|DestCidr|String|否|0.0.0.0/0|目的网段。

 目的网段格式为CIDR格式。例如：192.168.10.0/24。 |
|IpProtocol|String|否|tcp|访问控制规则应用的协议。

 访问控制功能支持的协议类型，请以控制台为准。协议格式不区分大小写。 |
|SourcePortRange|String|否|80/80|源端口范围。取值范围：**-1**或**1**~**65535**。

 目的端口范围格式示例：

 -   1/200，表示端口范围1至200。
-   80/80，表示端口80。
-   -1/-1，表示不限制端口。 |
|DestPortRange|String|否|80/80|目的端口范围。取值范围：**-1**或**1**~**65535**。

 目的端口范围格式示例：

 -   1/200，表示端口范围1至200。
-   80/80，表示端口80。
-   -1/-1，表示不限制端口。 |
|Policy|String|否|accept|访问控制规则授权策略。取值：

 -   **accept**：允许。
-   **drop**：拒绝。 |
|Priority|Integer|否|2|访问控制规则优先级。

 数值越小，优先级越高。同优先级时，先下发到智能接入网关设备的规则优先生效。

 取值范围：**1~100**。默认值：**1**。 |
|Type|String|否|LAN|访问控制规则类型。取值：

 -   **LAN**：（默认值）私网，表示针对私网地址的流量设置访问控制规则。
-   **WAN**：公网，表示针对公网地址的流量设置访问控制规则。 |
|Name|String|否|doctest|访问控制规则名称。

 名称长度为2~128个字符，以大小写字母或中文开头，可包含数字、下划线（\_）和短划线（-）。 |
|DpiSignatureIds.N|String|否|1|访问控制规则匹配的应用ID。

 您可以通过[ListDpiSignatures](~~196630~~)查询应用ID及其对应的应用信息。 |
|DpiGroupIds.N|String|否|20|访问控制规则匹配的应用组ID。

 您可以通过[ListDpiGroups](~~196754~~)查询应用组ID及其包含的应用信息。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|Policy|String|accept|访问控制规则授权策略。

 -   **accept**：允许。
-   **drop**：拒绝。 |
|Description|String|test|访问控制规则描述信息。 |
|RequestId|String|7F3DD2C1-0F6B-4575-9106-B2D50DF7A711|请求ID。 |
|SourcePortRange|String|-1/-1|源端口范围。 |
|SourceCidr|String|0.0.0.0/0|源网段。

 源网段格式为CIDR格式。例如：192.168.1.0/24。 |
|Priority|Integer|1|访问控制规则优先级。

 数值越小，优先级越高。同优先级时，先下发到智能接入网关设备的规则优先生效。 |
|AclId|String|acl-jdc7tir4fkplwr\*\*\*\*|访问控制实例ID。 |
|AcrId|String|acr-r8hezn2pi39s5a\*\*\*\*|访问控制规则ID。 |
|DestPortRange|String|-1/-1|目的端口范围。 |
|Direction|String|in|访问控制规则应用方向。取值：

 -   **in**：入方向，指从外部访问智能接入网关实例所在的本地网络的方向。
-   **out**：出方向，指从智能接入网关实例所在的本地网络访问外部的方向。 |
|DpiGroupIds|Array of String|20|访问控制规则匹配的应用组ID。 |
|Name|String|doctest|访问控制规则名称。 |
|GmtCreate|Long|1553777700000|创建访问控制规则时的时间戳。

 时间戳格式为Long型，优先级相同时，时间戳小的访问控制规则优先生效。 |
|DestCidr|String|0.0.0.0/0|目的网段。

 目的网段格式为CIDR格式。例如：192.168.10.0/24。 |
|DpiSignatureIds|Array of String|1|访问控制规则匹配的应用ID。 |
|IpProtocol|String|ALL|访问控制规则应用的协议。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=ModifyACLRule
&RegionId=cn-hangzhou
&AclId=acl-xhwhyuo43l0n*******
&AcrId=acr-u98qztgtgvhb********
&Description=test
&Direction=in
&SourceCidr=0.0.0.0/0
&DestCidr=0.0.0.0/0
&IpProtocol=tcp
&SourcePortRange=80/80
&DestPortRange=80/80
&Policy=accept
&Priority=2
&Type=LAN
&Name=doctest
&DpiSignatureIds=["1"]
&DpiGroupIds=["20"]
&公共请求参数
```

正常返回示例

`XML`格式

```
HTTP/1.1 200 OK
Content-Type:application/xml

<ModifyACLRuleResponse>
    <Policy>accept</Policy>
    <RequestId>7F3DD2C1-0F6B-4575-9106-B2D50DF7A711</RequestId>
    <SourcePortRange>-1/-1</SourcePortRange>
    <SourceCidr>0.0.0.0/0</SourceCidr>
    <Priority>1</Priority>
    <AclId>acl-jdc7tir4fkplwr****</AclId>
    <AcrId>acr-r8hezn2pi39s5a****</AcrId>
    <DestPortRange>-1/-1</DestPortRange>
    <Direction>in</Direction>
    <GmtCreate>1608887742000</GmtCreate>
    <DestCidr>0.0.0.0/0</DestCidr>
    <IpProtocol>ALL</IpProtocol>
</ModifyACLRuleResponse>
```

`JSON`格式

```
HTTP/1.1 200 OK
Content-Type:application/json

{
  "Policy" : "accept",
  "RequestId" : "7F3DD2C1-0F6B-4575-9106-B2D50DF7A711",
  "SourcePortRange" : "-1/-1",
  "SourceCidr" : "0.0.0.0/0",
  "Priority" : 1,
  "AclId" : "acl-jdc7tir4fkplwr****",
  "AcrId" : "acr-r8hezn2pi39s5a****",
  "DestPortRange" : "-1/-1",
  "Direction" : "in",
  "GmtCreate" : 1608887742000,
  "DestCidr" : "0.0.0.0/0",
  "IpProtocol" : "ALL"
}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|ACL.NoSupportWanType|An SAG 1000 device does not support a WAN ACL.|sag-1000类型盒子不支持公网ACL。|
|400|ACL.InvalidType|The specified ACL type is invalid.|非法的ACL类型。|
|403|Forbidden|User not authorized to operate on the specified resource.|用户没有操作此资源的权限。|
|403|MissingParameter|The input parameter is missing, please check your input.|输入参数缺失，请检查您的输入。|
|403|InvalidDescription|Description not valid.|详情描述超过长度限制。|
|403|InvalidParameter|The specified parameter is invalid.|非法参数。|
|403|FeatureNotSupport|The current edition of the smart access gateway does not support this feature.|智能接入网关当前版本不支持该功能特性。|
|403|FeatureNotSupportForActiveSmartAG|The current edition of the active smart access gateway does not support this feature.|主智能接入网关的当前版本不支持该功能特性。|
|403|FeatureNotSupportForStandBySmartAG|The current edition of the standby smart access gateway does not support this feature.|备智能接入网关的当前版本不支持该功能特性。|
|403|NotSupportedProtocol|The specified protocol of the ACL rule is not supported.|您输入的ACL规则的协议类型是不支持的。|
|403|InvalidId.ACL|The specified ACL ID is invalid.|无效的ACL组ID。|
|403|InvalidId.ACR|The specified ACL rule ID is invalid.|您输入的ACL规则ID无效。|
|403|InvalidPortRange|The specified port range is invalid.|您输入的端口范围不合法。|
|403|InternalError|An internal server error occurred.|内部服务错误。|

访问[错误中心](https://error-center.aliyun.com/status/product/Smartag)查看更多错误码。

