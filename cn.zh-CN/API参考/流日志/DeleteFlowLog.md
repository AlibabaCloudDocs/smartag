# DeleteFlowLog {#doc_api_Smartag_DeleteFlowLog .reference}

调用DeleteFlowLog删除一个流日志实例。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=DeleteFlowLog&type=RPC&version=2018-03-13)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|FlowLogId|String|是|fl-7a56mar1kfw9vj\*\*\*\*|流日志实例ID。

 |
|RegionId|String|是|cn-shanghai|流日志的地域ID。

 |
|Action|String|否|DeleteFlowLog|要执行的操作。

 取值：**DeleteFlowLog**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|B05AF87C-0FE5-42D7-BEA3-665D90FAA71D|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DeleteFlowLog
&FlowLogId=fl-7a56mar1kfw9vj****
&RegionId=cn-shanghai
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DeleteFlowLogResponse>
      <RequestId>B05AF87C-0FE5-42D7-BEA3-665D90FAA71D</RequestId>
	</DeleteFlowLogResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"B05AF87C-0FE5-42D7-BEA3-665D90FAA71D"
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

访问[错误中心](https://error-center.aliyun.com/status/product/Smartag)查看更多错误码。

