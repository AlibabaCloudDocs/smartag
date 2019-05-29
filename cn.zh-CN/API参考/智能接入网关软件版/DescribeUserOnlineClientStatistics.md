# DescribeUserOnlineClientStatistics {#doc_api_Smartag_DescribeUserOnlineClientStatistics .reference}

调用DescribeUserOnlineClientStatistics查询指定智能接入网关软件版实例用户数统计。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Smartag&api=DescribeUserOnlineClientStatistics)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|RegionId|String|是|cn-shanghai|智能接入网关软件版实例所在的地域。

 |
|UserNames.N|RepeatList|是|12|用户名列表，最大50。

 |
|Action|String|否|DescribeUserOnlineClientStatistics|要执行的操作。

 取值：**DescribeUserOnlineClientStatistics**

 |
|SmartAGId|String|否|sag-sfjg\*\*\*\*\*|智能接入网关软件版实例ID。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|14846A6A-2192-4F6A-B272-B8BD68EBC89B|请求ID。

 |
|UserStatistics| | |在线用户。

 |
|└OnlineCount|String|2|在线连接数。

 |
|└UserName|String|doctest|用户名。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeUserOnlineClientStatistics
&RegionId=cn-shanghai
&UserNames.1=12
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeUserOnlineClientStatistics>
  <RequestId>14846A6A-2192-4F6A-B272-B8BD68EBC89B</RequestId>
  <UserStatistics>
    <Statistics>
      <UserName>doctest</UserName>
      <OnlineCount>0</OnlineCount>
    </Statistics>
  </UserStatistics>
</DescribeUserOnlineClientStatistics>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"14846A6A-2192-4F6A-B272-B8BD68EBC89B",
	"UserStatistics":{
		"Statistics":[
			{
				"UserName":"doctest",
				"OnlineCount":0
			}
		]
	}
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|ClientUser.NameEmpty|You must specify UserName.|用户名不能为空。|
|400|ClientUser.NameInvalid|The specified UserName is invalid.|用户名格式非法。|
|400|SAG.InstanceIdEmpty|You must specify the SAG instance ID.|智能网关实例ID为空。|
|400|SAG.InstanceNoFound|The specified SAG instance does not exist.|智能网关实例不存在。|

[查看本产品错误码](https://error-center.aliyun.com/status/product/Smartag)

