# DescribeSmartAccessGatewayClientUsers {#doc_api_Smartag_DescribeSmartAccessGatewayClientUsers .reference}

调用DescribeSmartAccessGatewayClientUsers查询智能接入网关APP实例用户列表。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=DescribeSmartAccessGatewayClientUsers&type=RPC&version=2018-03-13)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|RegionId|String|是|cn-shanghai|智能接入网关APP实例所在的地域。

 |
|SmartAGId|String|是|sag-jfkskjfjf\*\*\*\*\*\*\*\*|智能接入网关APP实例ID。

 |
|Action|String|否|DescribeSmartAccessGatewayClientUsers|要执行的操作。

 取值：**DescribeSmartAccessGatewayClientUsers**。

 |
|PageNumber|Integer|否|2|分页查询的页码。

 |
|PageSize|Integer|否|21|分页查询时设置的每页行数。 最大值：100

 默认值：**50**

 |
|UserName|String|否|doctest|用户名，同一个智能接入网关APP实例下的用户名不可以重复。

 用户名和密码相互依赖，若指定用户名则必须指定密码，反之，若指定密码则必须指定用户名。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|PageNumber|Integer|1|分页查询的页码。

 |
|PageSize|Integer|12|分页查询时设置的每页行数。 最大值：100

 默认值：**50**

 |
|RequestId|String|62F4CF10-F909-487E-8E95-BC35457C5F50|请求ID。

 |
|TotalCount|Integer|2|用户数。

 |
|Users| | |APP客户端用户信息。

 |
|User| | |APP客户端用户信息。

 |
|Bandwidth|Integer|2|带宽。

 |
|ClientIp|String|10.\*\*.\*\*.\*\*|软件版客户端的IP地址。

 |
|State|Integer|0|账号启用状态，包含以下选项：

 -   0：表示正常
-   1：表示关闭

 |
|UserMail|String|test@example.com|普通用户的邮箱地址。

 |
|UserName|String|doctest|用户名。

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
<DescribeSmartAccessGatewayClientUsersResponse>
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
    </DescribeSmartAccessGatewayClientUsersResponse>
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

访问[错误中心](https://error-center.alibabacloud.com/status/product/Smartag)查看更多错误码。

