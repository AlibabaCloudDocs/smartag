# GetQosAttribute

调用GetQosAttribute接口查询QoS策略实例信息。

****

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=GetQosAttribute&type=RPC&version=2018-03-13)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|GetQosAttribute|要执行的操作。取值：**GetQosAttribute**。 |
|RegionId|String|是|cn-shanghai|QoS策略实例所属地域ID。

 您可以通过调用[DescribeRegions](~~36063~~)接口获取地域ID。 |
|QosId|String|是|qos-1iqifund3gcno5\*\*\*\*|QoS策略实例ID。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|QosPolicies|Array of QosPolicy| |QoS策略实例的五元组规则信息列表。 |
|EndTime|Long|2021-07-29T00:00:00+0800|五元组规则失效时间。

 时间显示为北京时间，格式为：UTC时间+8小时。 |
|StartTime|Long|2021-06-21T00:00:00+0800|五元组规则开始生效时间。 |
|DestCidr|String|0.0.0.0/0|目的网段。 |
|DestPortRange|String|-1/-1|目的端口范围。

 取值范围：**-1**或**1**~**65535**。

 目的端口范围格式示例：

 -   **1/200**，表示端口范围1至200。
-   **80/80**，表示端口80。
-   **-1/-1**，表示不限制端口。 |
|IpProtocol|String|ALL|五元组规则应用的协议类型。 |
|Priority|Integer|1|五元组规则所属的限速规则的优先级。

 数值越小，优先级越高。 |
|QosPolicieDescription|String|test|五元组规则的描述信息。 |
|SourceCidr|String|0.0.0.0/0|源网段。 |
|QosPolicieName|String|test|五元组规则名称。 |
|SourcePortRange|String|-1/-1|源端口范围。

 取值范围：**-1**或**1**~**65535**。

 源端口范围格式例如：

 -   **1/200**，表示端口范围1至200。
-   **80/80**，表示端口80。
-   **-1/-1**，表示不限制端口。 |
|QosCars|Array of QosCar| |配置异常的QoS策略限速规则信息。 |
|MaxBandwidthAbs|Integer|2|最大带宽。单位：Mbps。 |
|QosCarName|String|test|限速规则的名称。 |
|PercentSourceType|String|InternetUpBandwidth|按百分比限速时的带宽类型：

 -   **CcnBandwidth**：云连接网带宽。
-   **InternetUpBandwidth**：公网上行带宽。 |
|MinBandwidthAbs|Integer|1|最小带宽。单位：Mbps。 |
|MaxBandwidthPercent|Integer|20|最大带宽百分比。 |
|QosCarDescription|String|test|限速规则的描述信息。 |
|LimitType|String|Absolute|限速类型：

 -   **Absolute**：按带宽值。
-   **Percent**：按百分比。 |
|Priority|Integer|1|限速规则的优先级。

 优先级支持设置**1**~**3**级，数值越小，优先级越高。 |
|MinBandwidthPercent|Integer|10|最小带宽百分比。 |
|QosCarId|String|qoscar-xir1apa8ayjp56ei\*\*\*\*|限速规则ID。 |
|RequestId|String|91058E01-1806-45D5-B305-19E4D0A5CE04|请求ID。 |
|ErrorConfigSmartAGCount|Integer|1|配置异常的智能接入网关实例个数。 |
|QosName|String|test|QoS策略实例的名称。 |
|QosDescription|String|test|QoS策略实例的描述信息。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=GetQosAttribute
&RegionId=cn-shanghai
&QosId=qos-1iqifund3gcno5****
&公共请求参数
```

正常返回示例

`XML`格式

```
HTTP/1.1 200 OK
Content-Type:application/xml

<GetQosAttributeResponse>
    <QosPolicies>
        <DestCidr>0.0.0.0/0</DestCidr>
        <SourcePortRange>-1/-1</SourcePortRange>
        <SourceCidr>0.0.0.0/0</SourceCidr>
        <Priority>1</Priority>
        <IpProtocol>ALL</IpProtocol>
        <DestPortRange>-1/-1</DestPortRange>
    </QosPolicies>
    <QosCars>
        <MinBandwidthAbs>1</MinBandwidthAbs>
        <QosCarId>qoscar-xir1apa8ayjp56ei****</QosCarId>
        <Priority>1</Priority>
        <MaxBandwidthAbs>2</MaxBandwidthAbs>
        <PercentSourceType>InternetUpBandwidth</PercentSourceType>
        <LimitType>Absolute</LimitType>
    </QosCars>
    <RequestId>91058E01-1806-45D5-B305-19E4D0A5CE04</RequestId>
    <ErrorConfigSmartAGCount>1</ErrorConfigSmartAGCount>
    <QosName>ccn-yaochi-bvt-qos</QosName>
</GetQosAttributeResponse>
```

`JSON`格式

```
HTTP/1.1 200 OK
Content-Type:application/json

{
  "QosPolicies" : [ {
    "DestCidr" : "0.0.0.0/0",
    "SourcePortRange" : "-1/-1",
    "SourceCidr" : "0.0.0.0/0",
    "Priority" : 1,
    "IpProtocol" : "ALL",
    "DestPortRange" : "-1/-1"
  } ],
  "QosCars" : [ {
    "MinBandwidthAbs" : 1,
    "QosCarId" : "qoscar-xir1apa8ayjp56ei****",
    "Priority" : 1,
    "MaxBandwidthAbs" : 2,
    "PercentSourceType" : "InternetUpBandwidth",
    "LimitType" : "Absolute"
  } ],
  "RequestId" : "91058E01-1806-45D5-B305-19E4D0A5CE04",
  "ErrorConfigSmartAGCount" : 1,
  "QosName" : "ccn-yaochi-bvt-qos"
}
```

## 错误码

访问[错误中心](https://error-center.aliyun.com/status/product/Smartag)查看更多错误码。

