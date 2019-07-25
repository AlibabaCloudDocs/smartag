# DescribeNetworkOptimizationSags {#doc_api_Smartag_DescribeNetworkOptimizationSags .reference}

调用DescribeNetworkOptimizationSags查询网络优化实例绑定的智能接入网关列表。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Smartag&api=DescribeNetworkOptimizationSags)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|NetworkOptId|String|是|opt-h118pubncs3g\*\*\*\*\*\*|网络优化实例ID。

 |
|RegionId|String|是|cn-hangzhou|网络优化实例所在的地域ID。

 |
|Action|String|否|DescribeNetworkOptimizationSags|要执行的操作。

 取值：**DescribeNetworkOptimizationSags**。

 |
|PageNo|Integer|否|1|列表的页码，默认值为1。

 |
|PageSize|Integer|否|12|分页查询时每页的行数，最大值为50。

 默认值为10。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|PageNo|Integer|1|列表的页码，默认值为1。

 |
|PageSize|Integer|12|分页查询时每页的行数，最大值为50。

 默认值为10。

 |
|RequestId|String|893D6AFB-217C-4483-A061-F171021EAD65|请求ID。

 |
|SmartAccessGateways| | |智能接入网关实例列表。

 |
|└CreateTime|Long|1559802120000|智能接入网关实例创建时间。

 |
|└EndTime|Long|1562428971000|智能接入网关实例到期时间。

 |
|└InstanceId|String|sag-ojpz0tghdd9d9z\*\*\*\*|智能接入网关实例ID。

 |
|└MaxBandwidth|String|10M|智能接入网关实例带宽峰值。

 |
|└Name|String|dpctest|智能接入网关实例名称。

 |
|└State|String|Offline|智能接入网关实例状态。

 |
|TotalCount|Integer|2|绑定的智能接入网关实例数目。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeNetworkOptimizationSags
&NetworkOptId=opt-h118pubncs3g******
&RegionId=cn-hangzhou
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeNetworkOptimizationSagsResponse>
  <TotalCount>1</TotalCount>
  <SmartAccessGateways>
    <SmartAccessGateway>
      <Name>joe0606</Name>
      <State>Offline</State>
      <CreateTime>1559802120000</CreateTime>
      <InstanceId>sag-ojpz0tghdd9d*****</InstanceId>
      <EndTime>1562428971000</EndTime>
      <MaxBandwidth>10M</MaxBandwidth>
    </SmartAccessGateway>
  </SmartAccessGateways>
  <PageSize>10</PageSize>
  <RequestId>893D6AFB-217C-4483-A061-F171021EAD65</RequestId>
  <PageNo>1</PageNo>
</DescribeNetworkOptimizationSagsResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"SmartAccessGateways":{
		"SmartAccessGateway":[
			{
				"Name":"joe0606",
				"State":"Offline",
				"InstanceId":"sag-ojpz0tghdd9d9z****",
				"CreateTime":1559802120000,
				"EndTime":1562428971000,
				"MaxBandwidth":"10M"
			}
		]
	},
	"TotalCount":1,
	"PageSize":10,
	"PageNo":1,
	"RequestId":"893D6AFB-217C-4483-A061-F171021EAD65"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|NetworkOpt.InstanceIdEmpty|You must specify the NetworkOptId parameter.|公网优化实例ID不能为空。|
|400|NetworkOpt.InvalidInstanceId|The specified instance ID is invalid.|非法的公网优化实例。|
|400|NetworkOpt.InvalidState|The specified instance is not available.|公网实例状态不可用。|

[查看本产品错误码](https://error-center.aliyun.com/status/product/Smartag)

