# DescribeUserFlowStatistics {#doc_api_Smartag_DescribeUserFlowStatistics .reference}

调用DescribeUserOnlineClients查询指定智能接入网关软件版实例下用户的流量统计。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Smartag&api=DescribeUserFlowStatistics)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|RegionId|String|是|cn-hangzhou|智能接入网关软件版实例所在的地域。

 |
|SmartAGId|String|是|sag-mfkg\*\*\*\*\*|智能接入网关软件版实例ID。

 |
|UserNames.N|RepeatList|是|12|用户名列表，最大50。

 |
|Action|String|否|DescribeUserFlowStatistics|要执行的操作。

 取值：**DescribeUserOnlineClients**

 |
|StatisticsDate|String|否|201905|统计日期，格式yyyyMM。

 如果不设置，默认表示当月。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|9552AD68-18EA-4074-B27D-40040FBA9683|请求ID。

 |
|SagStatistics| | |流量统计。

 |
|└TotalBytes|String|12|流量值，单位byte。

 |
|└UserName|String|doctest|用户名。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeUserFlowStatistics
&RegionId=cn-hangzhou
&SmartAGId=sag-mfkg*****
&UserNames.1=12
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeUserFlowStatistics>
  <SagStatistics>
    <Statistics>
      <UserName>zhanlg</UserName>
      <TotalBytes>555352</TotalBytes>
    </Statistics>
  </SagStatistics>
  <RequestId>ADD09081-31A9-4E7D-B15C-135C6EBEEB63</RequestId>
</DescribeUserFlowStatistics>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"ADD09081-31A9-4E7D-B15C-135C6EBEEB63",
	"SagStatistics":{
		"Statistics":[
			{
				"UserName":"zhanlg",
				"TotalBytes":555352
			}
		]
	}
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|SAG.InstanceIdEmpty|You must specify the SAG instance ID.|智能网关实例ID为空。|
|400|SAG.InstanceNoFound|The specified SAG instance does not exist.|智能网关实例不存在。|

[查看本产品错误码](https://error-center.aliyun.com/status/product/Smartag)

