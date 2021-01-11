# CreateQosPolicy

调用CreateQosPolicy创建QoS策略五元组规则。

## 前提条件

在您创建QoS策略五元组规则前，请确保您已经创建了QoS策略限速规则。具体操作，请参见[CreateQosCar](~~131806~~)。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=CreateQosPolicy&type=RPC&version=2018-03-13)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|CreateQosPolicy|要执行的操作。

 取值：**CreateQosPolicy**。 |
|DestCidr|String|是|10.10.20.0/24|目的网段。

 目的网段格式为CIDR格式。例如：192.168.10.0/24。 |
|DestPortRange|String|是|80/80|目的端口范围。

 取值范围：**-1**或**1**~**65535**。

 目的端口范围格式例如：

 -   1/200，表示端口范围1至200。
-   80/80，表示端口80。
-   -1/-1，表示不限制端口。 |
|IpProtocol|String|是|TCP|QoS策略五元组规则应用的协议类型。

 QoS策略五元组规则支持的协议类型，请以控制台为准。 |
|Priority|Integer|是|3|QoS策略五元组规则所属的限速规则优先级。

 数值越小，优先级越高，同优先级时先下发至智能接入网关设备的规则优先生效。 |
|QosId|String|是|qos-dhf\*\*\*\*\*\*\*\*\*\*\*|QoS策略的实例ID。 |
|RegionId|String|是|cn-hangzhou|QoS策略实例所在的地域ID。 |
|SourceCidr|String|是|10.10.10.0/24|源网段。

 源网段格式为CIDR格式。例如：192.168.1.0/24。 |
|SourcePortRange|String|是|80/80|源端口范围。

 取值范围：**-1**或**1**~**65535**。

 目的端口范围格式例如：

 -   1/200，表示端口范围1至200。
-   80/80，表示端口80。
-   -1/-1，表示不限制端口。 |
|Description|String|否|test|QoS策略五元组规则的描述。

 长度为1~512个字符，以大小写字母或中文开头，可包含数字、下划线（\_）或短划线（-）。 |
|StartTime|String|否|2019-07-14T16:41:33+0800|QoS策略五元组规则生效开始时间。 |
|EndTime|String|否|2019-09-14T16:41:33+0800|QoS策略五元组规则生效结束时间。 |
|Name|String|否|nametest|QoS策略五元组规则名称。

 长度为2~100个字符，以大小写字母或中文开头，可包含数字、短划线（-）或下划线（\_）。 |
|DpiSignatureIds.N|RepeatList|否|1|应用组ID列表。

 您可以通过[ListDpiGroups](~~196754~~)查询应用组ID及其包含的应用信息。N的最大值为**10**。 |
|DpiGroupIds.N|RepeatList|否|20|应用ID列表。

 您可以通过[ListDpiSignatures](~~196630~~)查询应用ID及其对应的应用信息。N的最大值为**10**。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|Description|String|bvt-test|QoS策略五元组规则的描述。 |
|DestCidr|String|10.10.10.0/24|目的网段。 |
|DestPortRange|String|80/80|目的端口范围。 |
|DpiGroupIds|List|20|应用组ID列表。

 您可以通过[ListDpiGroups](~~196754~~)查询应用组ID及其包含的应用信息。 |
|DpiSignatureIds|List|1|应用ID列表。

 您可以通过[ListDpiSignatures](~~196630~~)查询应用ID及其对应的应用信息。 |
|EndTime|String|2019-09-14T16:41:33+0800|QoS策略五元组规则生效结束时间。 |
|IpProtocol|String|TCP|QoS策略五元组规则应用的协议类型。 |
|Name|String|nametest|QoS策略五元组规则名称。 |
|Priority|Integer|3|QoS策略五元组规则所属的限速规则优先级。 |
|QosId|String|qos-xhwhyuo43l\*\*\*\*\*\*\*\*|QoS策略的实例ID。 |
|QosPolicyId|String|qospy-xhwhyuo43l\*\*\*\*\*\*\*\*|QoS策略五元组规则的实例ID。 |
|RequestId|String|97862812-2C7E-4D25-B0D5-B26DAC7FA293|请求ID。 |
|SourceCidr|String|10.10.10.0/24|源网段。 |
|SourcePortRange|String|80/80|源端口范围。 |
|StartTime|String|2019-07-14T16:41:33+0800|QoS策略五元组规则生效开始时间。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=CreateQosPolicy
&DestCidr=10.10.20.0/24
&DestPortRange=80/80
&IpProtocol=TCP
&Priority=3
&QosId=qos-dhf***********
&RegionId=cn-hangzhou
&SourceCidr=10.10.10.0/24
&SourcePortRange=80/80
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<CreateQosPolicyResponse>
  <Description>bvt-test</Description>
  <DestCidr>10.10.0.0/24</DestCidr>
  <DestPortRange>-1/-1</DestPortRange>
  <EndTime>2019-09-14T16:41:33+0800</EndTime>
  <IpProtocol>ALL</IpProtocol>
  <Priority>1</Priority>
  <QosId>qos-awfxl1adxeqykl****</QosId>
  <QosPolicyId>qospy-427m9fo6wkhofs1****</QosPolicyId>
  <RequestId>97862812-2C7E-4D25-B0D5-B26DAC7FA293</RequestId>
  <SourceCidr>192.168.0.0/24</SourceCidr>
  <SourcePortRange>-1/-1</SourcePortRange>
  <StartTime>2019-07-14T16:41:33+0800</StartTime>
</CreateQosPolicyResponse>
```

`JSON` 格式

```
{
    "Description":"bvt-test",
    "DestCidr":"10.10.0.0/24",
    "DestPortRange":"-1/-1",
    "EndTime":"2019-09-14T16:41:33+0800",
    "IpProtocol":"ALL",
    "Priority":1,
    "QosId":"qos-awfxl1adxeqykl****",
    "QosPolicyId":"qospy-427m9fo6wkhofs1****",
    "RequestId":"97862812-2C7E-4D25-B0D5-B26DAC7FA293",
    "SourceCidr":"192.168.0.0/24",
    "SourcePortRange":"-1/-1",
    "StartTime":"2019-07-14T16:41:33+0800"
}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|InternalError|An internal server error occurred.|内部服务错误|
|400|NotSupportedProtocol|The specified protocol of the QoS policy is not supported.|Qos规则不支持该协议。|
|403|InvalidPortRange|The specified port range is invalid.|您输入的端口范围不合法。|
|400|InvalidId.Qos|The specified QosId is invalid.|您输入的参数"QosId"不合法。|
|400|QosPyPerQosPyPerQosAmountLimitQosAmountLimit|The maximum number of policies in a QoS is exceeded. You can submit a ticket to increase the quota.|单个Qos策略中的QosPolicy达到上限，您可以提交工单申请提高配额。|
|400|MissParameter.RegionId|You must specify RegionId.|您的输入中缺少必填参数"RegionId"。|
|400|MissParameter.QosId|You must specify QosId.|您的输入中缺少必填参数"QosId"。|
|400|MissParameter.QosPolicyId|You must specify QosPolicyId.|您的输入中缺少必填参数"QosPolicyId"。|
|400|InvalidParameter.Priority|The specified Priority is invalid.|您输入的参数"Priority"不合法。|
|400|MissParameter.SourceCidr|You must specify SourceCidr.|您的输入中缺少必填参数"SourceCidr"。|
|400|MissParameter.SourcePortRange|You must specify SourcePortRange.|您的输入中缺少必填参数"SourcePortRange"。|
|400|MissParameter.DestCidr|You must specify DestCidr.|您的输入中缺少必填参数"DestCidr"。|
|400|MissParameter.DestPortRange|You must specify DestPortRange.|您的输入中缺少必填参数"DestPortRange"。|
|400|MissParameter.IpProtocol|You must specify IpProtocol.|您的输入中缺少必填参数"IpProtocol"。|
|400|InvalidParameter.Description|The specified Description is invalid.|您输入的参数"Description"不合法。|
|400|InvalidParameter.DestCidr|The specified DestCidr is invalid.|您输入的参数"DestCidr"不合法。|
|400|InvalidParameter.DestPortRange|The specified DestPortRange is invalid.|您输入的参数"DestPortRange"不合法。|
|400|InvalidParameter.SourceCidr|The specified SourceCidr is invalid.|您输入的参数"SourceCidr"不合法。|
|400|InvalidParameter.SourcePortRange|The specified SourcePortRange is invalid.|您输入的参数"SourcePortRange"不合法。|
|400|InvalidParameter.StartTime|The specified StartTime is invalid.|您输入的参数"StartTime"不合法。|
|400|InvalidParameter.EndTime|The specified EndTime is invalid.|您输入的参数"EndTime"不合法。|
|400|InvalidTimeRangeCompare|The specified end time is earlier than the start time. Please check your input.|您输入的参数中结束时间小于开始时间，请检查您的输入。|
|400|InvalidParameter.Name|The specified Name is invalid.|您输入的参数"Name"不合法。|

访问[错误中心](https://error-center.aliyun.com/status/product/Smartag)查看更多错误码。

