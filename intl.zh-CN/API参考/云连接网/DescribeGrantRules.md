# DescribeGrantRules {#doc_api_Smartag_DescribeGrantRules .reference}

调用DescribeGrantRules查询绑定的云连接网的授权规则。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=DescribeGrantRules&type=RPC&version=2018-03-13)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|RegionId|String|是|cn-shanghai|云企业网实例所在的地域ID。

 |
|Action|String|否|DescribeGrantRules|要执行的操作，取值：**DescribeGrantRules**。

 |
|AssociatedCcnId|String|否|ccn-n2935s1mnwv8i\*\*\*\*\*|绑定的云连接网ID

 |
|PageNumber|String|否|1|请求页码，默认值是**1**。

 |
|PageSize|String|否|10|每页行数，默认值为**10**，最大值为**50**.

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|GrantRules| | |授权列表。

 |
|CcnInstanceId|String|ccn-n2935s1mnwv8i\*\*\*\*\*|CCN实例ID。

 |
|CcnUid|Long|213213|云连接网用户ID。

 |
|CenInstanceId|String|3213214|云企业网实例ID。

 |
|CenUid|Long|213213|云企业网用户ID。

 |
|GmtCreate|Long|1563439920000|规则创建时间Long型时间戳，优先级相同时，小时间戳先生效。

 |
|GmtModified|Long|1563439920000|规则最后修改的时间Long型时间戳，优先级相同时，小时间戳先生效。

 |
|GrantRuleId|String|18313265-d988-406c-965d-3e110ff\*\*\*\*\*|授权规则实例ID。

 |
|RegionId|String|cn-shanghai|地域ID。

 |
|PageNumber|Integer|1|分页索引。

 |
|PageSize|Integer|10|分页大小。

 |
|RequestId|String|FA579C2D-84A0-4BA1-B9C3-1E5A3B15F1B6|请求ID。

 |
|TotalCount|Integer|1|记录总数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeGrantRules
&RegionId=cn-shanghai
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeGrantRulesResponse>
	  <PageNumber>1</PageNumber>
	  <GrantRules>
		    <GrantRule>
			      <GrantRuleId>18313265-d988-406c-965d-3e110ff*****</GrantRuleId>
			      <CenUid>213213</CenUid>
			      <CcnInstanceId>ccn-n2935s1mnwv8i*****</CcnInstanceId>
			      <CenInstanceId>3213214</CenInstanceId>
			      <RegionId>cn-shanghai</RegionId>
			      <GmtCreate>1563439920000</GmtCreate>
			      <GmtModified>1563439920000</GmtModified>
		    </GrantRule>
	  </GrantRules>
	  <TotalCount>1</TotalCount>
	  <PageSize>10</PageSize>
	  <RequestId>FA579C2D-84A0-4BA1-B9C3-1E5A3B15F1B6</RequestId>
</DescribeGrantRulesResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"PageNumber":1,
	"GrantRules":{
		"GrantRule":[
			{
				"GrantRuleId":"18313265-d988-406c-965d-3e110ff*****",
				"CenUid":213213,
				"CcnInstanceId":"ccn-n2935s1mnwv8i*****",
				"CenInstanceId":"3213214",
				"RegionId":"cn-shanghai",
				"GmtCreate":1563439920000,
				"GmtModified":1563439920000
			}
		]
	},
	"TotalCount":1,
	"PageSize":10,
	"RequestId":"FA579C2D-84A0-4BA1-B9C3-1E5A3B15F1B6"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.alibabacloud.com/status/product/Smartag)查看更多错误码。

