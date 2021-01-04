# ModifyQosPolicy

调用ModifyQosPolicy修改五元组规则。

****

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=ModifyQosPolicy&type=RPC&version=2018-03-13)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|ModifyQosPolicy|要执行的操作。

 取值：**ModifyQosPolicy**。 |
|QosId|String|是|qos-djhgg\*\*\*\*\*\*\*\*\*\*\*|Qos策略的实例ID。 |
|QosPolicyId|String|是|qospy-427m9fo6wkh\*\*\*\*\*\*\*\*\*|Qos规则的五元组实例ID。 |
|RegionId|String|是|cn-hangzhou|Qos策略实例所属的地域ID。 |
|Priority|Integer|否|3|设置限速策略的优先级，数值越小，优先级越高，同优先级时先下发的规则优先生效。

 优先级范围：1~7。 |
|SourceCidr|String|否|10.10.10.9/24|源网段。 |
|DestCidr|String|否|10.10.20.9/12|目的网段。 |
|IpProtocol|String|否|tcp|传输层协议。 |
|SourcePortRange|String|否|80/80|源端口范围。 |
|DestPortRange|String|否|80/80|目的端口范围。 |
|StartTime|String|否|2019-07-14T16:41:33+0800|五元组规则生效开始时间。 |
|EndTime|String|否|2019-09-14T16:41:33+0800|五元组规则生效结束时间。 |
|Description|String|否|docdesc|五元组规则描述。 |
|Name|String|否|doctest|五元组规则名称。长度为2-100，必须以大小字母或中文开头，可包含数字，"-","\_"。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|551CD836-9E46-4F2C-A167-B4363180A647|请求ID。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=ModifyQosPolicy
&QosId=qos-djhgg***********
&QosPolicyId=qospy-427m9fo6wkh*********
&RegionId=cn-hangzhou
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<ModifyQosPolicyResponse>
	  <RequestId>551CD836-9E46-4F2C-A167-B4363180A647</RequestId>
    </ModifyQosPolicyResponse>
```

`JSON` 格式

```
{
"RequestId":"551CD836-9E46-4F2C-A167-B4363180A647"
}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|MissParameter.RegionId|You must specify RegionId.|您的输入中缺少必填参数"RegionId"。|
|400|MissParameter.QosId|You must specify QosId.|您的输入中缺少必填参数"QosId"。|
|400|MissParameter.QosPolicyId|You must specify QosPolicyId.|您的输入中缺少必填参数"QosPolicyId"。|
|400|InvalidParameter.Description|The specified Description is invalid.|您输入的参数"Description"不合法。|
|400|InvalidParameter.Priority|The specified Priority is invalid.|您输入的参数"Priority"不合法。|
|400|InvalidParameter.SourcePortRange|The specified SourcePortRange is invalid.|您输入的参数"SourcePortRange"不合法。|
|400|InvalidParameter.DestCidr|The specified DestCidr is invalid.|您输入的参数"DestCidr"不合法。|
|400|InvalidParameter.DestPortRange|The specified DestPortRange is invalid.|您输入的参数"DestPortRange"不合法。|
|400|InvalidParameter.SourceCidr|The specified SourceCidr is invalid.|您输入的参数"SourceCidr"不合法。|
|400|InvalidParameter.StartTime|The specified StartTime is invalid.|您输入的参数"StartTime"不合法。|
|400|InvalidParameter.EndTime|The specified EndTime is invalid.|您输入的参数"EndTime"不合法。|
|400|InvalidTimeRangeCompare|The specified end time is earlier than the start time. Please check your input.|您输入的参数中结束时间小于开始时间，请检查您的输入。|
|400|InvalidId.QOSPY|The specified QosPolicyId is invalid.|指定的QosPolicy的实例ID不合法。|
|403|InternalError|An internal server error occurred.|内部服务错误|
|400|InvalidId.Qos|The specified QosId is invalid.|您输入的参数"QosId"不合法。|
|400|NotSupportedProtocol|The specified protocol of the QoS policy is not supported.|Qos规则不支持该协议。|
|403|InvalidPortRange|The specified port range is invalid.|您输入的端口范围不合法|
|400|InvalidParameter.Name|The specified Name is invalid.|您输入的参数"Name"不合法。|

访问[错误中心](https://error-center.aliyun.com/status/product/Smartag)查看更多错误码。

