# DescribeACLAttribute

调用DescribeACLAttribute查询指定访问控制实例信息。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=DescribeACLAttribute&type=RPC&version=2018-03-13)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|DescribeACLAttribute|要执行的操作。

 取值：**DescribeACLAttribute**。 |
|AclId|String|是|acl-ohlexqptfhy\*\*\*\*\*\*|访问控制实例ID。 |
|RegionId|String|是|cn-hangzhou|访问控制实例所属地域ID。 |
|PageSize|Integer|否|10|分页查询时每页展示的访问控制规则条目数。

 取值范围：**1**~**50**。

 默认值：**10**。 |
|PageNumber|Integer|否|1|分页查询时的页码。默认值：**1**。 |
|Direction|String|否|out|访问控制规则应用方向。取值：

 -   **in**：入方向，指从外部访问智能接入网关实例所在的本地分支的流量。
-   **out**：出方向，指从智能接入网关实例所在的本地分支访问外部的流量。 |
|Order|String|否|1255444444|订单ID。 |
|Name|String|否|doctest|访问控制实例名称。

 长度为2~100个字符，以大小写字母或中文开头，可包含数字、半角句号（.）、下划线（\_）和短划线（-）。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|Acrs|Array of Acr| |当前访问控制实例包含的访问控制规则信息。 |
|Acr| | | |
|AclId|String|acl-7louazbja80bmgxxxx|访问控制实例ID。 |
|AcrId|String|acr-gxzxj5w9qqdf1cxxxx|访问控制规则ID。 |
|Description|String|访问规则|访问控制规则描述信息。

 描述长度为**1~512**个字符。 |
|DestCidr|String|0.0.0.0/0|目的网段。

 目的网段格式为CIDR格式。例如：192.168.10.0/24。 |
|DestPortRange|String|10000/20000|目的端口范围。

 取值范围：**-1**或**1**~**65535**。

 目的端口范围格式例如：1/200、80/80，其中-1/-1代表不限制端口。 |
|Direction|String|out|访问控制规则应用方向。

 -   **in**：入方向，指从外部访问智能接入网关实例所在的本地分支的流量。
-   **out**：出方向，指从智能接入网关实例所在的本地分支访问外部的流量。 |
|DpiGroupIds|List|20|当前访问控制规则匹配的应用组ID列表。

 您可以通过[ListDpiGroups](~~196754~~)查询应用组ID及其包含的应用信息。 |
|DpiSignatureIds|List|1|当前访问控制规则匹配的应用ID列表。

 您可以通过[ListDpiSignatures](~~196630~~)查询应用ID及其对应的应用信息。 |
|GmtCreate|Long|1580821597000|创建访问控制规则时的时间戳。

 时间戳格式为Long型，优先级相同时，时间戳小的访问控制规则优先生效。 |
|IpProtocol|String|UDP|访问控制规则应用的协议。

 访问控制功能支持的协议类型，请以控制台为准。协议格式不区分大小写。 |
|Name|String|doctest|访问控制实例名称。

 长度为2~100个字符，以大小写字母或中文开头，可包含数字、半角句号（.）、下划线（\_）和短划线（-）。 |
|Policy|String|drop|访问控制规则授权策略：

 -   **accept**：允许。
-   **drop**：拒绝。 |
|Priority|Integer|70|访问控制规则优先级。

 取值范围：**1~100**。 |
|SourceCidr|String|0.0.0.0/0|源网段。

 源网段格式为CIDR格式。例如：192.168.1.0/24。 |
|SourcePortRange|String|30000/40000|源端口范围。

 取值范围：**-1**或**1**~**65535**。

 源端口范围格式例如：1/200、80/80，其中-1/-1代表不限制端口。 |
|Type|String|WAN|访问控制规则类型：

 -   **LAN**：私网，表示针对私网地址的流量设置访问控制规则。
-   **WAN**：公网，表示针对公网地址的流量设置访问控制规则。 |
|PageNumber|Integer|1|分页查询时的页码。 |
|PageSize|Integer|10|分页查询时每页展示的访问控制规则条目数。 |
|RequestId|String|8F62CE77-FBA2-4F8D-AED9-0A02814EDA69|请求ID。 |
|TotalCount|Integer|3|当前访问控制实例包含的总的访问控制规则条目数。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=DescribeACLAttribute
&AclId=acl-ohlexqptfhy******
&RegionId=cn-hangzhou
&<公共请求参数>
```

正常返回示例

`XML` 格式

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

`JSON` 格式

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

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|Forbidden|User not authorized to operate on the specified resource.|用户没有操作此资源的权限。|
|403|MissingParameter|The input parameter is missing, please check your input.|输入参数缺失，请检查您的输入。|
|403|InvalidParameter|The specified parameter is invalid.|非法参数。|
|403|InvalidId.ACL|The specified ACL ID is invalid.|无效的ACL组ID。|
|403|InternalError|An internal server error occurred.|内部服务错误|

访问[错误中心](https://error-center.alibabacloud.com/status/product/Smartag)查看更多错误码。

