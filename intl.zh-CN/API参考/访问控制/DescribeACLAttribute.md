# DescribeACLAttribute {#doc_api_Smartag_DescribeACLAttribute .reference}

调用DescribeACLAttribute批量查询访问控制，需要增加Name参数，支持按照Name过滤。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Smartag&api=DescribeACLAttribute)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|AclId|String|是|acl-ohlexqptfhy\*\*\*\*\*\*|访问控制ID。

 |
|RegionId|String|是|cn-hangzhou|地域ID。

 |
|Action|String|否|DescribeACLAttribute|要执行的操作。

 取值：**DescribeACLAttribute**

 |
|Direction|String|否|test|规则方向。

 取值：**in|out**

 |
|Order|String|否|1255444444|订单号。

 |
|PageNumber|Integer|否|2|列表的页码，默认值为1。

 |
|PageSize|Integer|否|10|分页查询时每页的行数，最大值为50，默认值为10。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Acrs| | |访问控制规则。

 |
|└AclId|String|acl-xhwhyuo43l\*\*\*\*\*\*\*|访问控制ID。

 |
|└AcrId|String|acr-oicr94jwtpij\*\*\*\*\*\*\*|访问控制规则ID。

 |
|└Description|String|访问规则|访问控制规则描述信息，长度为1~512个字符。

 |
|└DestCidr|String|0.0.0.0/0|目的地址，CIDR 格式和IPv4格式的IP地址范围。

 默认值：0.0.0.0/0

 |
|└DestPortRange|String|12|目的端口范围，80/80。

 |
|└Direction|String|in|规则方向。

 取值：**in|out**

 |
|└GmtCreate|Long|1553077933000|规则创建时间Long型时间戳，优先级相同时，小时间戳先生效。

 |
|└IpProtocol|String|TCP|协议，不区分大小写。

 |
|└Policy|String|drop|访问权限：**drop|accept**（默认值）

 |
|└Priority|Integer|2|优先级。

 取值范围：**1~100**，默认为1。

 |
|└SourceCidr|String|0.0.0.0/0|源地址，CIDR 格式和 IPv4 格式的IP地址范围。

 默认值：**0.0.0.0/0**

 |
|└SourcePortRange|String|30|源端口范围，80/80。

 |
|PageNumber|Integer|12|列表的页码，默认值为1。

 |
|PageSize|Integer|5|分页查询时每页的行数。

 |
|RequestId|String|5DC67C13-B0E4-45E0-A60C-D32D3B74AB19|请求ID。

 |
|TotalCount|Integer|12|返回总数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?AclId=acl-ohlexqptfhy******
&RegionId=cn-hangzhou
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeACLAttribute>
  <PageNumber>1</PageNumber>
  <Acrs>
    <Acr>
      <IpProtocol>TCP</IpProtocol>
      <SourceCidr>192.168.3.0/24</SourceCidr>
      <SourcePortRange>1/65535</SourcePortRange>
      <AclId>acl-xhwhyuo43l0******</AclId>
      <AcrId>acr-oicr94jwtpi*******</AcrId>
      <Policy>accept</Policy>
      <DestPortRange>1/65535</DestPortRange>
      <DestCidr>10.0.0.1/32</DestCidr>
      <GmtCreate>1553077933000</GmtCreate>
      <Direction>out</Direction>
      <Priority>1</Priority>
    </Acr>
  </Acrs>
  <TotalCount>1</TotalCount>
  <PageSize>10</PageSize>
  <RequestId>5DC67C13-B0E4-45E0-A60C-D32D3B74AB19</RequestId>
</DescribeACLAttribute>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"PageNumber":1,
	"Acrs":{
		"Acr":[
			{
				"IpProtocol":"TCP",
				"SourceCidr":"192.168.3.0/24",
				"SourcePortRange":"1/65535",
				"AcrId":"acr-oicr94jwtpi******",
				"AclId":"acl-xhwhyuo43l0n******",
				"Policy":"accept",
				"DestPortRange":"1/65535",
				"DestCidr":"10.0.0.1/32",
				"GmtCreate":1553077933000,
				"Direction":"out",
				"Priority":1
			}
		]
	},
	"TotalCount":1,
	"PageSize":10,
	"RequestId":"5DC67C13-B0E4-45E0-A60C-D32D3B74AB19"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|Forbidden|User not authorized to operate on the specified resource.|用户没有操作此资源的权限|
|403|MissingParameter|The input parameter is missing, please check your input.|输入参数缺失，请检查您的输入|
|403|InvalidParameter|The specified parameter is invalid.|非法参数|
|403|InvalidId.ACL|The specified ACL ID is invalid.|无效的ACL组ID|
|403|InternalError|An internal server error occurred.|内部服务错误|

[查看本产品错误码](https://error-center.aliyun.com/status/product/Smartag)

