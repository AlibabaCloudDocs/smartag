# DescribeDnatEntries {#doc_api_Smartag_DescribeDnatEntries .reference}

调用DescribeDnatEntries查询智能接入网关实例绑定的DNAT条目。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Smartag&api=DescribeDnatEntries)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|RegionId|String|是|cn-hangzhou|智能接入网关实例所在的地域ID。

 |
|SagId|String|是|sag-djgd\*\*\*\*\*\*\*\*\*\*\*\*\*|智能接入网关实例ID。

 **说明：** 目前仅支持硬件版实例。

 |
|Action|String|否|DescribeDnatEntries|要执行的操作。

 取值：**DescribeDnatEntries**。

 |
|PageNumber|Integer|否|1|分页查询时设置的每页行数，默认值为10，最大值为50。

 |
|PageSize|Integer|否|12|实例状态列表的页码，默认值为1。

 |
|Type|String|否|Intranet|DNAT类型，包含以下选项：

 -   Intranet：缺省值，表示私网DNAT。
-   Internet：表示公网DNAT。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|DnatEntries| | |DNAT条目规则列表。

 |
|DnatEntryId|String|dnat-jdhg\*\*\*\*\*\*\*\*\*\*|DNAT实例ID。

 |
|ExternalIp|String|10.10.\*\*.\*\*|外部的公网IP地址。

 |
|ExternalPort|String|12|公网端口。

 取值范围：**1-65535**。

 |
|InternalIp|String|192.168.0.1|目标私网IP地址。

 |
|InternalPort|String|80|目标私网端口号。

 取值范围：**1-65535**。

 |
|IpProtocol|String|TCP|协议类型，包含以下选项：

 -   TCP：转发TCP协议的报文。
-   UDP：转发UDP协议的报文。
-   Any：转发所有协议的报文。

 |
|SagId|String|sag-jfh\*\*\*\*\*\*\*\*|智能接入网关实例ID。

 |
|Type|String|Intranet|DNAT类型，包括以下选项：

 -   Intranet：缺省值，表示私网DNAT。
-   Internet：表示公网DNAT。

 |
|PageNumber|Integer|12|分页查询时设置的每页行数，默认值为10，最大值为50。

 |
|PageSize|Integer|1|实例状态列表的页码，默认值为1。

 |
|RequestId|String|635640CA-2335-4856-A9CB-1CB5C444DC5A|请求ID。

 |
|TotalCount|Integer|50|记录总数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeDnatEntries
&RegionId=cn-hangzhou
&SagId=sag-djgd*************
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDnatEntriesResponse>
  <DnatEntries/>
  <PageNumber>1</PageNumber>
  <PageSize>10</PageSize>
  <RequestId>635640CA-2335-4856-A9CB-1CB5C444DC5A</RequestId>
  <TotalCount>0</TotalCount>
</DescribeDnatEntriesResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"PageNumber":1,
	"TotalCount":0,
	"PageSize":10,
	"RequestId":"635640CA-2335-4856-A9CB-1CB5C444DC5A",
	"DnatEntries":{
		"DnatEntry":[]
	}
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|Forbidden|User not authorized to operate on the specified resource.|用户没有操作此资源的权限|
|403|MissingParameter|The input parameter is missing, please check your input.|输入参数缺失，请检查您的输入|
|403|InvalidParameter|The specified parameter is invalid.|非法参数|
|403|InternalError|An internal server error occurred.|内部服务错误|

访问[错误中心](https://error-center.alibabacloud.com/status/product/Smartag)查看更多错误码。

