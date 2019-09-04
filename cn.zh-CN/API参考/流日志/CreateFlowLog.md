# CreateFlowLog {#doc_api_Smartag_CreateFlowLog .reference}

调用CreateFlowlog创建一个流日志。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=CreateFlowLog&type=RPC&version=2018-03-13)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Description|String|是|创建流日志|流日志实例描述。

 |
|InactiveAging|Integer|是|15|非活跃流输出间隔，默认15s。

 |
|LogstoreName|String|是|config-operation-log|日志服务的日志库，当输出类型为sls时填入。

 |
|Name|String|是|sag-flowlog-1|流日志实例名称。

 |
|NetflowServerIp|String|是|192.168.0.2|流日志输出的服务器地址，输出类型是netflow时填入。

 |
|NetflowServerPort|Integer|是|9995|流日志输出的服务器端口，默认值为**9995**，输出类型是netflow时填入。

 |
|NetflowVersion|String|是|V9|流日志输出时使用的Netflow协议版本号，可选**V5**、**V9**和**V10**，默认**V9**，输出类型是netflow时填入。

 |
|OutputType|String|是|sls|流日志输出类型：

 -   **sls**：流日志存储在阿里云日志服务。
-   **netflow**：流日志存储在您配置的netflow服务器。
-   **all**：流日志同时存储在阿里云日志服务和您配置的netflow服务器。

 |
|ProjectName|String|是|sag-flowlog-shanghai|日志服务的 Project，输出类型为sls时填入。

 |
|RegionId|String|是|cn-shanghai|流日志的地域ID。

 |
|SlsRegionId|String|是|cn-hanghzou|日志服务的地域ID，输出类型为sls时填入。

 |
|Action|String|否|CreateFlowLog|要执行的操作。

 取值：**CreateFlowLog**。

 |
|ActiveAging|Integer|否|300|活跃流输出间隔，默认300s。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|FlowLogId|String|fl-7a56mar1kfw9vj\*\*\*\*|流日志的ID。

 |
|RequestId|String|650CB9E8-20F3-4538-A4FC-1DA1B36E42D9|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=CreateFlowLog
&Description=创建流日志
&InactiveAging=15
&LogstoreName=config-operation-log
&Name=sag-flowlog-1
&NetflowServerIp=192.168.0.2
&NetflowServerPort=9995
&NetflowVersion=V9
&OutputType=sls
&ProjectName=sag-flowlog-shanghai
&RegionId=cn-shanghai
&SlsRegionId=flowlog-shanghai1
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<CreateFlowLogResponse>
      <RequestId>650CB9E8-20F3-4538-A4FC-1DA1B36E42D9</RequestId>
	  <FlowLogId>fl-7a56mar1kfw9vj****</FlowLogId>
	</CreateFlowLogResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"650CB9E8-20F3-4538-A4FC-1DA1B36E42D9",
	"FlowLogId":"fl-7a56mar1kfw9vj****"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|DependencyViolation.FlowLog|This FlowLog instance is bound to an SAG instance.|FlowLog存在资源依赖|
|400|IncorrectStatus.FlowLog|The current FlowLog instance status does not support this operation.|FlowLog状态非法|
|400|InvalidFlowLogId.NotFound|The specified FlowLogId does not exist.|根据FlowLogId未找到对应实例|
|400|MissingParam.FlowLogId|Specify the FlowLogId parameter.|缺少参数FlowLogId|
|400|OperationFailed.AssociateFlowLog|The operation failed. The specified SAG instance has already been associated with another FlowLog instance.|由于智能接入网关实例已经关联其他FlowLog实例，操作失败|
|400|OperationUnsupported.AssociateFlowLog|You cannot bind the SAG device of the current version or model to a FlowLog instance.|设备版本或者款型不支持关联FlowLog操作|
|400|QuotaExceeded.Flowlog|The maximum number of FlowLog instances is exceeded.|flowlog数量超过配额|
|400|MissingParam.LogstoreName|Specify the LogstoreName parameter.|缺少参数LogstoreName|
|400|MissingParam.NetflowServerIp|Specify the NetflowServerIp parameter.|缺少参数NetflowServerIp|
|400|MissingParam.NetflowServerPort|Specify the NetflowServerPort parameter.|缺少参数NetflowServerPort|
|400|MissingParam.NetflowVersion|Specify the NetflowVersion parameter.|缺少参数NetflowVersion|
|400|MissingParam.ProjectName|Specify the ProjectName parameter.|缺少参数ProjectName|
|400|MissingParam.SlsRegionId|Specify the SlsRegionId parameter.|缺少参数SlsRegionId|
|400|IllegalParam.ActiveAging|The specified ActiveAging is invalid.|参数ActiveAging不合法|
|400|IllegalParam.InactiveAging|The specified InactiveAging is invalid.|参数InactiveAging不合法|
|400|IllegalParam.NetflowServerIp|The specified NetflowServerIp is invalid.|参数NetflowServerIp不合法|
|400|IllegalParam.NetflowServerPort|The specified NetflowServerPort is invalid.|参数NetflowServerPort不合法|
|400|IllegalParam.NetflowVersion|The specified NetflowVersion is invalid.|参数NetflowVersion不合法|
|400|IllegalParam.OutputType|The specified OutputType is invalid.|参数OutputType不合法|
|400|IllegalParam.RegionId|The specified RegionId is invalid.|参数RegionId不合法|
|400|IllegalParam.SlsRegionId|The specified SlsRegionId is invalid.|参数SlsRegionId不合法|
|400|IllegalParam.Status|The specified Status parameter is invalid.|参数Status不合法|
|403|FeatureNotSupport|The current edition of the smart access gateway does not support this feature.|智能接入网关当前版本不支持该功能特性|

访问[错误中心](https://error-center.aliyun.com/status/product/Smartag)查看更多错误码。

