# DescribeFlowLogSags {#doc_api_Smartag_DescribeFlowLogSags .reference}

调用DescribeFlowLogSags查询流日志绑定的智能接入网关实例。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=DescribeFlowLogSags&type=RPC&version=2018-03-13)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|FlowLogId|String|是|fl-l934tsa5504yuc\*\*\*\*|流日志实例ID。

 |
|RegionId|String|是|cn-shanghahi|流日志的地域ID。

 |
|Action|String|否|DescribeFlowLogSags|要执行的操作。

 取值：**DescribeFlowLogSags**。

 |
|PageNumber|Integer|否|1|查询列表的页码，起始值为**1**，默认值为**1**。

 |
|PageSize|Integer|否|10|指定分页查询时每页的列表行数，最大值为**50**，默认值为**10**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|PageNumber|Integer|1|当前页码。

 |
|PageSize|Integer|4|当前分页包含的条目数。

 |
|RequestId|String|8D945945-85F2-4BD7-A144-7DC0E8B5A0DC|请求ID。

 |
|Sags| | |智能接入网关。

 |
|Sag| | |智能接入网关。

 |
|Description|String|sag-100wm|智能接入网关实例描述。

 |
|Name|String|ruijie-test-2|智能接入网关实例名称。

 |
|SmartAGId|String|sag-6rm1awijm3ktic\*\*\*\*|智能接入网关实例ID。

 |
|TotalCount|Integer|35|列表条条目数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeFlowLogSags
&FlowLogId=fl-l934tsa5504yuc****
&RegionId=cn-shanghahi
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeFlowLogSagsResponse>
	  <PageNumber>1</PageNumber>
	  <Sags>
		    <Sag>
			      <Name>ruijie-test-2</Name>
			      <SmartAGId>sag-6rm1awijm3ktic****</SmartAGId>
		    </Sag>
		    <Sag>
			      <Name>zhanxiaolong</Name>
			      <SmartAGId>sag-ecvqa7bw8fxbdn****</SmartAGId>
		    </Sag>
		    <Sag>
			      <Name>ccn-e2e-cn-sh-0-0820-005408</Name>
			      <SmartAGId>sag-gn7m5v5bpjykne****</SmartAGId>
		    </Sag>
		    <Sag>
			      <Name>sag-sec-1b</Name>
			      <SmartAGId>sag-hk69hizmi21fy9****</SmartAGId>
		    </Sag>
		    <Sag>
			      <Name></Name>
			      <SmartAGId>sag-i54wm4v15ruxji****</SmartAGId>
		    </Sag>
		    <Sag>
			      <Name>china-0-0424-222240</Name>
			      <SmartAGId>sag-iunln2dztruttt****</SmartAGId>
		    </Sag>
		    <Sag>
			      <Name>sag-sec-1</Name>
			      <SmartAGId>sag-q1sqc77sk2oe08****</SmartAGId>
		    </Sag>
		    <Sag>
			      <Name>sag1000_box5</Name>
			      <SmartAGId>sag-u42tn80ro3bxsd****</SmartAGId>
		    </Sag>
		    <Sag>
			      <Name>ccn-e2e-cn-sh-0-0820-005549</Name>
			      <SmartAGId>sag-wle98f4o41nm3f****</SmartAGId>
		    </Sag>
		    <Sag>
			      <Name>jia_双机_SAG1000</Name>
			      <SmartAGId>sag-yev5ajsek9x12o****</SmartAGId>
		    </Sag>
	  </Sags>
	  <TotalCount>35</TotalCount>
	  <PageSize>10</PageSize>
	  <RequestId>8D945945-85F2-4BD7-A144-7DC0E8B5A0DC</RequestId>
	</DescribeFlowLogSagsResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"PageNumber":1,
	"Sags":{
		"Sag":[
			{
				"SmartAGId":"sag-6rm1awijm3ktic****",
				"Name":"ruijie-test-2"
			},
			{
				"SmartAGId":"sag-ecvqa7bw8fxbdn****",
				"Name":"zhanxiaolong"
			},
			{
				"SmartAGId":"sag-gn7m5v5bpjykne****",
				"Name":"ccn-e2e-cn-sh-0-0820-005408"
			},
			{
				"SmartAGId":"sag-hk69hizmi21fy9****",
				"Name":"sag-sec-1b"
			},
			{
				"SmartAGId":"sag-i54wm4v15ruxji****",
				"Name":""
			},
			{
				"SmartAGId":"sag-iunln2dztruttt****",
				"Name":"china-0-0424-222240"
			},
			{
				"SmartAGId":"sag-q1sqc77sk2oe08****",
				"Name":"sag-sec-1"
			},
			{
				"SmartAGId":"sag-u42tn80ro3bxsd****",
				"Name":"sag1000_box5"
			},
			{
				"SmartAGId":"sag-wle98f4o41nm3f****",
				"Name":"ccn-e2e-cn-sh-0-0820-005549"
			},
			{
				"SmartAGId":"sag-yev5ajsek9x12o****",
				"Name":"jia_双机_SAG1000"
			}
		]
	},
	"TotalCount":35,
	"PageSize":10,
	"RequestId":"8D945945-85F2-4BD7-A144-7DC0E8B5A0DC"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|IllegalParam.ActiveAging|The specified ActiveAging is invalid.|参数ActiveAging不合法|
|400|IllegalParam.InactiveAging|The specified InactiveAging is invalid.|参数InactiveAging不合法|
|400|IllegalParam.NetflowServerIp|The specified NetflowServerIp is invalid.|参数NetflowServerIp不合法|
|400|IllegalParam.NetflowServerPort|The specified NetflowServerPort is invalid.|参数NetflowServerPort不合法|
|400|IllegalParam.NetflowVersion|The specified NetflowVersion is invalid.|参数NetflowVersion不合法|
|400|IllegalParam.OutputType|The specified OutputType is invalid.|参数OutputType不合法|
|400|IllegalParam.RegionId|The specified RegionId is invalid.|参数RegionId不合法|
|400|IllegalParam.SlsRegionId|The specified SlsRegionId is invalid.|参数SlsRegionId不合法|
|400|IllegalParam.Status|The specified Status parameter is invalid.|参数Status不合法|
|400|DependencyViolation.FlowLog|This FlowLog instance is bound to an SAG instance.|FlowLog存在资源依赖|
|400|IncorrectStatus.FlowLog|The current FlowLog instance status does not support this operation.|FlowLog状态非法|
|400|InvalidFlowLogId.NotFound|The specified FlowLogId does not exist.|根据FlowLogId未找到对应实例|
|400|MissingParam.FlowLogId|Specify the FlowLogId parameter.|缺少参数FlowLogId|
|400|OperationFailed.AssociateFlowLog|The operation failed. The specified SAG instance has already been associated with another FlowLog instance.|由于智能接入网关实例已经关联其他FlowLog实例，操作失败|
|400|OperationUnsupported.AssociateFlowLog|You cannot bind the SAG device of the current version or model to a FlowLog instance.|设备版本或者款型不支持关联FlowLog操作|
|400|QuotaExceeded.Flowlog|The maximum number of FlowLog instances is exceeded.|flowlog数量超过配额|

访问[错误中心](https://error-center.aliyun.com/status/product/Smartag)查看更多错误码。

