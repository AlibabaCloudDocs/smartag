# DescribeSmartAccessGatewayClientUsers {#doc_api_Smartag_DescribeSmartAccessGatewayClientUsers .reference}

调用DescribeSmartAccessGatewayClientUsers查询软件版实例用户列表。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Smartag&api=DescribeSmartAccessGatewayClientUsers)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|RegionId|String|是|cn-shanghai|智能接入网关软件版实例所在的地域。

 |
|SmartAGId|String|是|sag-jfkskjfjf\*\*\*\*\*\*\*\*|智能接入网关软件版实例ID。

 |
|Action|String|否|DescribeSmartAccessGatewayClientUsers|要执行的操作。

 取值：**DescribeSmartAccessGatewayClientUsers**

 |
|PageNo|Integer|否|1|标签列表的页码。 起始值：1

 默认值：**1**

 |
|PageSize|Integer|否|21|分页查询时设置的每页行数。 最大值：100

 默认值：**50**

 |
|UserName|String|否|doctest|用户名，同一个智能接入网关软件版实例下的用户名不可以重复。

 用户名和密码相互依赖，若指定用户名则必须指定密码，反之，若指定密码则必须指定用户名。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|PageNo|Integer|2|标签列表的页码。 起始值：1

 默认值：1

 |
|PageSize|Integer|12|分页查询时设置的每页行数。 最大值：100

 默认值：**50**

 |
|RequestId|String|62F4CF10-F909-487E-8E95-BC35457C5F50|请求ID。

 |
|TotalCount|Integer|2|用户数。

 |
|Users| | |软件客户端用户信息。

 |
|└Bandwidth|Integer|2|带宽。

 |
|└ClientIp|String|10.\*\*.\*\*.\*\*|软件版客户端的IP地址。

 |
|└UserMail|String|test@example.com|普通用户的邮箱地址。

 |
|└UserName|String|doctest|用户名。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeSmartAccessGatewayClientUsers
&RegionId=cn-shanghai
&SmartAGId=sag-jfkskjfjf********
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeSmartAccessGatewayClientUsers>
  <Users>
    <User>
      <SmartAccessGatewayId>sag-va03wf***idaj00g6x</SmartAccessGatewayId>
      <IsStaticIp>0</IsStaticIp>
      <UserMail>dd@example.com</UserMail>
      <UserName>dd@example.com</UserName>
      <Bandwidth>2</Bandwidth>
    </User>
  </Users>
  <TotalCount>1</TotalCount>
  <PageSize>10</PageSize>
  <RequestId>62F4CF10-F909-487E-8E95-BC35457C5F50</RequestId>
  <PageNo>1</PageNo>
</DescribeSmartAccessGatewayClientUsers>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Users":{
		"User":[
			{
				"SmartAccessGatewayId":"sag-va03****idaj00g6x",
				"IsStaticIp":0,
				"UserMail":"dd@example.com",
				"UserName":"dd@example.com",
				"Bandwidth":2
			}
		]
	},
	"TotalCount":1,
	"PageSize":10,
	"PageNo":1,
	"RequestId":"62F4CF10-F909-487E-8E95-BC35457C5F50"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|SAG.InstanceIdEmpty|You must specify the SAG instance ID.|智能网关实例ID为空。|
|400|SAG.InstanceNoFound|The specified SAG instance does not exist.|智能网关实例不存在。|

[查看本产品错误码](https://error-center.aliyun.com/status/product/Smartag)

