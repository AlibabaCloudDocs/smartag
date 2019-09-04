# DescribeFlowLogs {#doc_api_Smartag_DescribeFlowLogs .reference}

调用DescribeFlowLogs查询流日志。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=DescribeFlowLogs&type=RPC&version=2018-03-13)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|FlowLogId|String|是|fl-7a56mar1kfw9vj\*\*\*\*|流日志实例ID。

 |
|RegionId|String|是|cn-hangzhou|流日志地域ID。

 |
|Action|String|否|DescribeFlowLogs|要执行的操作。

 取值：**DescribeFlowLogs**。

 |
|Description|String|否|流日志1|流日志实例描述。

 |
|FlowLogName|String|否|DDE|流日志实例名称。

 |
|OutputType|String|否|sls|流日志输出类型：

 -   **sls**：流日志存储在阿里云日志服务。
-   **netflow**：流日志存储在您配置的netflow服务器。
-   **all**：流日志同时存储在阿里云日志服务和您配置的netflow服务器。

 |
|PageNumber|Integer|否|1|流日志实例列表的页码，起始值为**1**，默认值为**1**。

 |
|PageSize|Integer|否|10|指定分页查询时每页的行数，最大值为**50**，默认值为**10**。

 |
|Status|String|否|Active|流日志实例状态：

 -   **Active**：已启动。
-   **Inactive**：未启动。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|FlowLogs| | |流日志。

 |
|FlowLogSetType| | |流日志。

 |
|ActiveAging|Integer|300|活跃流输出间隔，默认为300s。

 |
|Description|String|流日志实例2|流日志实例描述。

 |
|FlowLogId|String|fl-7a56mar1kfw9vj\*\*\*\*|流日志实例ID。

 |
|InactiveAging|Integer|15|非活跃流输出间隔，默认值为15s。

 |
|LogstoreName|String|ssfghgh|日志服务的日志库，输出类型为sls时填入。

 |
|Name|String|DDE|流日志实例名称。

 |
|NetflowServerIp|String|192.168.0.2|流日志输出的服务器地址，输出类型为netflow时填入。

 |
|NetflowServerPort|String|9995|流日志输出的服务器端口，默认值为**9995**，输出类型为netflow时填入。

 |
|NetflowVersion|String|V9|流日志输出时使用的etflow协议版本号，可选**V5**、**V9**和**V10**，默认**V9**，输出类型为netflow时填入。

 |
|OutputType|String|sls|流日志输出类型：

 -   **sls**：流日志存储在阿里云日志服务。
-   **netflow**：流日志存储在您配置的netflow服务器。
-   **all**：流日志同时存储在阿里云日志服务和您配置的netflow服务器。

 |
|ProjectName|String|ddrrgt|日志服务的Project，输出类型为sls时填入。

 |
|SlsRegionId|String|cn-shanghai|日志服务的地域ID，输出类型为sls时填入。

 |
|Status|String|Active|流日志实例的状态：

 -   **Active**:已启动。
-   **Inactive**：未启动。

 |
|TotalSagNum|Integer|2|流日志实例关联的智能接入网关实例数目。

 |
|PageNumber|Integer|1|流日志实例列表的页码数，起始值为**1**，默认值为**1**。

 |
|PageSize|Integer|10|指定分页查询时每页的行数，最大值为**50**，默认值为**10**。

 |
|RequestId|String|44F4E2D0-77F7-4DEC-969B-061688946143|请求ID。

 |
|TotalCount|Integer|5|查询列表条目数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeFlowLogs
&FlowLogId=fl-7a56mar1kfw9vj****
&RegionId=cn-hangzhou
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeFlowLogsResponse>
	  <PageNumber>1</PageNumber>
	  <FlowLogs>
		    <FlowLogSetType>
			      <Name>test111</Name>
			      <InactiveAging>15</InactiveAging>
			      <Status>Active</Status>
			      <NetflowVersion>V9</NetflowVersion>
			      <ProjectName>sag-flowlog-shanghai</ProjectName>
			      <SlsRegionId>cn-shanghai</SlsRegionId>
			      <ActiveAging>300</ActiveAging>
			      <FlowLogId>fl-l934tsa5504yuc****</FlowLogId>
			      <OutputType>sls</OutputType>
			      <TotalSagNum>35</TotalSagNum>
			      <NetflowServerPort>9995</NetflowServerPort>
			      <LogstoreName>sag-shanghai</LogstoreName>
		    </FlowLogSetType>
	  </FlowLogs>
	  <TotalCount>1</TotalCount>
	  <PageSize>20</PageSize>
	  <RequestId>44F4E2D0-77F7-4DEC-969B-061688946143</RequestId>
	</DescribeFlowLogsResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"FlowLogs":{
		"FlowLogSetType":[
			{
				"InactiveAging":15,
				"Name":"test111",
				"Status":"Active",
				"ProjectName":"sag-flowlog-shanghai",
				"NetflowVersion":"V9",
				"ActiveAging":300,
				"SlsRegionId":"cn-shanghai",
				"FlowLogId":"fl-l934tsa5504yuc****",
				"OutputType":"sls",
				"TotalSagNum":35,
				"NetflowServerPort":9995,
				"LogstoreName":"sag-shanghai"
			}
		]
	},
	"PageNumber":1,
	"TotalCount":1,
	"PageSize":20,
	"RequestId":"44F4E2D0-77F7-4DEC-969B-061688946143"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Smartag)查看更多错误码。

