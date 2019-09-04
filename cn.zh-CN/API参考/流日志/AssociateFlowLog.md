# AssociateFlowLog {#doc_api_Smartag_AssociateFlowLog .reference}

调用AssociateFlowLog绑定智能接入网关实例。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=AssociateFlowLog&type=RPC&version=2018-03-13)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|FlowLogId|String|是|fl-l934tsa5504yuc\*\*\*\*|流日志实例ID。

 |
|RegionId|String|是|cn-shanghai|流日志的地域ID。

 |
|SmartAGId|String|是|sag-39u6j9a49i03wk\*\*\*\*|智能接入网关实例ID。

 |
|Action|String|否|AssociateFlowLog|要执行的操作。

 取值：**AssociateFlowLog**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|A6E1680B-B34F-4BB7-B504-F8ED675E721C|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=AssociateFlowLog
&FlowLogId=fl-l934tsa5504yuc****
&RegionId=cn-shanghai
&SmartAGId=sag-39u6j9a49i03wk****
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<AssociateFlowLogResponse>
	  <RequestId>A6E1680B-B34F-4BB7-B504-F8ED675E721C</RequestId>
    </AssociateFlowLogResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"A6E1680B-B34F-4BB7-B504-F8ED675E721C"
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
|400|IllegalParam.ActiveAging|The specified ActiveAging is invalid.|参数ActiveAging不合法|
|400|IllegalParam.InactiveAging|The specified InactiveAging is invalid.|参数InactiveAging不合法|
|400|IllegalParam.NetflowServerIp|The specified NetflowServerIp is invalid.|参数NetflowServerIp不合法|
|400|IllegalParam.NetflowServerPort|The specified NetflowServerPort is invalid.|参数NetflowServerPort不合法|
|400|IllegalParam.NetflowVersion|The specified NetflowVersion is invalid.|参数NetflowVersion不合法|
|400|IllegalParam.OutputType|The specified OutputType is invalid.|参数OutputType不合法|
|400|IllegalParam.RegionId|The specified RegionId is invalid.|参数RegionId不合法|
|400|IllegalParam.SlsRegionId|The specified SlsRegionId is invalid.|参数SlsRegionId不合法|
|400|IllegalParam.Status|The specified Status parameter is invalid.|参数Status不合法|
|400|InvalidSmartAGId.NotFound|The specified SmartAGId does not exist.|根据SmartAGId未找到对应实例|
|403|FeatureNotSupport|The current edition of the smart access gateway does not support this feature.|智能接入网关当前版本不支持该功能特性|
|403|FeatureNotSupportForActiveSmartAG|The current edition of the active smart access gateway does not support this feature.|主智能接入网关的当前版本不支持该功能特性|
|403|FeatureNotSupportForStandBySmartAG|The current edition of the standby smart access gateway does not support this feature.|备智能接入网关的当前版本不支持该功能特性|

访问[错误中心](https://error-center.aliyun.com/status/product/Smartag)查看更多错误码。

