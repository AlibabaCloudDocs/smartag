# DescribeCloudConnectNetworks {#doc_api_Smartag_DescribeCloudConnectNetworks .reference}

调用DescribeCloudConnectNetworks查询已创建的云连接网。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Smartag&api=DescribeCloudConnectNetworks)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|RegionId|String|是|cn-hangzhou|云连接网的所属区域。

 |
|Action|String|否|DescribeCloudConnectNetworks|要执行的操作。

 取值： **DescribeCloudConnectNetworks**

 |
|CcnId|String|否|ccn-l9340rlu5enst\*\*\*\*\*|云连接网ID。

 |
|Name|String|否|ccn名称|云连接网名称。

 |
|PageNumber|String|否|4|实例状态列表的页码，默认值是1。

 |
|PageSize|String|否|4|分页查询时设置的每页行数，默认值为10，最大值为50。

 |
|Tag.N.Key|String|否|2|第N标签key。

 |
|Tag.N.Value|String|否|2|第N标签值。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|CloudConnectNetworks| | |云连接网的信息。

 |
|└AssociatedCenId|String|ccn-l9340rlu5enst\*\*\*\*\*\*|绑定的云企业网ID。

 |
|└AssociatedCenOwnerId|String|1954105122583124|云企业网的账号ID。

 |
|└AssociatedCloudBoxCount|String|3|云连接网绑定的智能接入网关数量。

 |
|└AvailableCloudBoxCount|String|2|已绑定的智能接入网关中可用的网关数量。

 |
|└CcnId|String|ccn-l9340rlu5enst\*\*\*\*\*\*|云连接网ID。

 |
|└CidrBlock|String|10.10.10.0/24|私网网段。

 |
|└CreateTime|Long|1523618639000|云连接网的创建时间。

 |
|└Description|String|ccn描述|云连接网描述。

 |
|└IsDefault|Boolean|false|是否默认创建。

 如果客户没有ccn在绑定时，会给用户默认创建一个ccn。

 |
|└Name|String|ccn名称|云连接网名称。

 |
|└SnatCidrBlock|String|10.10.10.5/24|SNAT网段。

 |
|└Tags| | |标签列表。

 |
|└Key|String|2|第N标签key。

 |
|└Value|String|2|第N标签值。

 |
|PageNumber|Integer|1|当前页码。

 |
|PageSize|Integer|2|当前分页包含多少条目。

 |
|RequestId|String|3F2A0B80-D6D1-4764-8D77-38067DBBA345|请求ID。

 |
|TotalCount|Integer|2|列表条目数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://smartag.cn-shanghai.aliyuncs.com/?Action=DescribeCloudConnectNetworks
&CommonParameters

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeCloudConnectNetworksResponse>
  <CloudConnectNetworks>
    <CloudConnectNetwork>
      <Name>DocTest</Name>
      <AvailableCloudBoxCount>2</AvailableCloudBoxCount>
      <AssociatedCenOwnerId>1954105122583124</AssociatedCenOwnerId>
      <IsDefault>false</IsDefault>
      <AssociatedCloudBoxCount>3</AssociatedCloudBoxCount>
      <CreateTime>1523618639000</CreateTime>
      <CcnId>ccn-l9340rlu5enstmzj5i</CcnId>
    </CloudConnectNetwork>
    <CloudConnectNetwork>
      <Name>CEN测试</Name>
      <Description/>
      <AvailableCloudBoxCount>0</AvailableCloudBoxCount>
      <AssociatedCenOwnerId>1954105122583124</AssociatedCenOwnerId>
      <IsDefault>false</IsDefault>
      <AssociatedCloudBoxCount>0</AssociatedCloudBoxCount>
      <CreateTime>1523190009000</CreateTime>
      <CcnId>ccn-oa5ftyg6t48gnhb61k</CcnId>
    </CloudConnectNetwork>
  </CloudConnectNetworks>
  <PageNumber>1</PageNumber>
  <TotalCount>3</TotalCount>
  <PageSize>10</PageSize>
  <RequestId>3F2A0B80-D6D1-4764-8D77-38067DBBA345</RequestId>
</DescribeCloudConnectNetworksResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"PageNumber":1,
	"CloudConnectNetworks":{
		"CloudConnectNetwork":[
			{
				"Name":"DocTest",
				"AvailableCloudBoxCount":2,
				"AssociatedCenOwnerId":"1954105122583124",
				"AssociatedCloudBoxCount":3,
				"IsDefault":false,
				"CreateTime":1523618639000,
				"CcnId":"ccn-l9340rlu5enstmzj5i"
			},
			{
				"Name":"CEN测试",
				"Description":"",
				"AvailableCloudBoxCount":0,
				"AssociatedCenOwnerId":"1954105122583124",
				"AssociatedCloudBoxCount":0,
				"IsDefault":false,
				"CreateTime":1523190009000,
				"CcnId":"ccn-oa5ftyg6t48gnhb61k"
			}
		]
	},
	"TotalCount":3,
	"PageSize":10,
	"RequestId":"3F2A0B80-D6D1-4764-8D77-38067DBBA345"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|Forbidden|User not authorized to operate on the specified resource.|用户没有操作此资源的权限|
|400|InvalidTagKey|The specified tag key is invalid.|Tag标签的key值不合法|
|400|InvalidTagValue|The specified tag value is invalid.|Tag标签的value值不合法|

[查看本产品错误码](https://error-center.aliyun.com/status/product/Smartag)

