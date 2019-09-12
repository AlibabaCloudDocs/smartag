# DescribeGrantSagRules {#doc_api_Smartag_DescribeGrantSagRules .reference}

调用DescribeGrantSagRules查询授权智能接入网关规则。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=DescribeGrantSagRules&type=RPC&version=2018-03-13)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|PageNumber|Integer|是|1|实例状态列表的页码，默认值是1。

 |
|PageSize|Integer|是|10|分页查询时设置的每页行数，默认值为10，最大值为50。

 |
|RegionId|String|是|cn-hangzhou|智能接入网关实例所属的地域ID。

 |
|SmartAGId|String|是|sag-hdg\*\*\*\*\*\*\*\*\*\*\*\*\*|智能接入网关实例ID。

 |
|Action|String|否|DescribeGrantSagRules|要执行的操作。

 取值：**DescribeGrantSagRules**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|GrantRules| | |授权规则。

 |
|GrantRule| | |授权规则。

 |
|CcnInstanceId|String|ccn-hd\*\*\*\*\*\*\*\*\*\*|云连接网实例ID。

 |
|CcnUid|Long|13323444243434|云连接网实例所属的用户ID。

 |
|CreateTime|Long|156576751700|授权规则的创建时间。

 |
|InstanceId|String|1688401595963306|智能接入网关实例所属的用户ID。

 |
|SmartAGId|String|sag-hdhgn\*\*\*\*\*|智能接入网关实例ID。

 |
|PageNumber|Integer|2|实例状态列表的页码。

 |
|PageSize|Integer|10|分页查询时设置的每页行数。

 |
|RequestId|String|6E1674AC-083C-4031-B047-7A66E418E0C6|请求ID。

 |
|TotalCount|Integer|2|授权规则总数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeGrantSagRules
&PageNumber=1
&PageSize=10
&RegionId=cn-hangzhou
&SmartAGId=sag-hdg*************
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeGrantSagRulesResponse>
	  <GrantRules>
		    <GrantRule>
			      <CcnInstanceId>ccn-4dwoqcqu******</CcnInstanceId>
			      <CcnUid>1688401595963306</CcnUid>
			      <CreateTime>1565767517000</CreateTime>
			      <InstanceId>1688401595963306</InstanceId>
			      <SmartAGId>sag-7sc8ib3noaov*****</SmartAGId>
		    </GrantRule>
	  </GrantRules>
	  <PageNumber>1</PageNumber>
	  <PageSize>10</PageSize>
	  <RequestId>25B3FD03-DC56-4B88-8730-273485FAE0DC</RequestId>
	  <TotalCount>1</TotalCount>
    </DescribeGrantSagRulesResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"PageNumber":1,
	"GrantRules":{
		"GrantRule":[
			{
				"SmartAGId":"sag-7sc8ib3noaov*****",
				"CcnUid":1688401595963306,
				"CcnInstanceId":"ccn-4dwoqcqu******",
				"InstanceId":1688401595963306,
				"CreateTime":1565767517000
			}
		]
	},
	"TotalCount":1,
	"PageSize":10,
	"RequestId":"25B3FD03-DC56-4B88-8730-273485FAE0DC"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Smartag)查看更多错误码。

