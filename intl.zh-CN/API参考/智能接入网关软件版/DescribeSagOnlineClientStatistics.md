# DescribeSagOnlineClientStatistics {#doc_api_Smartag_DescribeSagOnlineClientStatistics .reference}

调用DescribeSagOnlineClientStatistics查询当前用户智能接入网关APP实例在线连接数据。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Smartag&api=DescribeSagOnlineClientStatistics)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|RegionId|String|是|cn-shanghai|智能接入网关APP实例所在的地域。

 |
|Action|String|否|DescribeSagOnlineClientStatistics|要执行的操作。

 取值：**DescribeSagOnlineClientStatistics**。

 |
|SmartAGIds.N|RepeatList|否|12|智能接入网关实例ID列表，最大为50。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|9EC839B6-0EA5-4F19-A4B7-A9E465D057AE|请求ID。

 |
|SagStatistics| | |在线连接数据。

 |
|OnlineCount|String|2|当前智能接入网关APP实例在线连接的客户端数。

 |
|SmartAGId|String|sag-va03wf4l4idaj\*\*\*\*\*|智能接入网关APP实例ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeSagOnlineClientStatistics
&RegionId=cn-shanghai
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeSagOnlineClientStatisticsResponse>
  <RequestId>9EC839B6-0EA5-4F19-A4B7-A9E465D057AE</RequestId>
  <SagStatistics>
    <Statistics>
      <SmartAGId>sag-va03wf4l4idaj0***</SmartAGId>
      <OnlineCount>0</OnlineCount>
    </Statistics>
  </SagStatistics>
</DescribeSagOnlineClientStatisticsResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"SagStatistics":{
		"Statistics":[
			{
				"SmartAGId":"sag-va03wf4l4idaj00***",
				"OnlineCount":0
			}
		]
	},
	"RequestId":"9EC839B6-0EA5-4F19-A4B7-A9E465D057AE"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.alibabacloud.com/status/product/Smartag)查看更多错误码。

