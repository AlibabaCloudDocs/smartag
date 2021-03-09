# DescribeHealthCheckAttribute

调用DescribeHealthCheckAttribute查询健康检查实例详情。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=DescribeHealthCheckAttribute&type=RPC&version=2018-03-13)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|DescribeHealthCheckAttribute|要执行的操作。

 取值：**DescribeHealthCheckAttribute**。 |
|HcInstanceId|String|是|hc-1k4ucuq77b56x4\*\*\*\*|健康检查实例ID。 |
|RegionId|String|是|cn-shanghai|智能接入网关实例的地域ID。 |
|SmartAGId|String|是|sag-1um5x5nwhilymw\*\*\*\*|智能接入网关实例ID。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|CreateTime|Long|1586759657000|健康检查实例创建时间。 |
|Description|String|hc-123|健康检查实例描述。 |
|DstIpAddr|String|192.XX.XX.1|健康检查的目的地址。 |
|DstPort|Integer|1223|健康检查的目的端口。

 **说明：** 该功能目前不支持。 |
|FailCountThreshold|Integer|3|连续探测失败次数阈值。

 取值范围：**1**~**15**。

 默认值：**3**。 |
|HcInstanceId|String|hc-1k4ucuq77b56x4\*\*\*\*|健康检查实例ID。 |
|Name|String|bvt-test-03\*\*\*\*|健康检查实例名称。 |
|ProbeCount|Integer|3|每次健康检查探测次数。

 取值范围：**1**~**20**。

 默认值：**1**。 |
|ProbeInterval|Integer|2000|健康检查配置探测间隔，一次探测未完成情况下，不会发起下一次探测。

 取值范围：**1000**~**60000**。

 默认值：**2000**。

 单位：毫秒。 |
|ProbeTimeout|Integer|1000|健康检查一次探测的超时时间。

 取值范围：**10**~**30000**。

 默认值：**1000**。

 单位：毫秒。 |
|RequestId|String|DDA08B78-5634-4A83-94E4-5C58FD7EBA19|请求ID。 |
|RttFailThreshold|Integer|3|时延阈值触发次数。

 取值范围：**1**~**15**。

 默认值：**3**。 |
|RttThreshold|Integer|300|双向时延阈值。

 取值：**-1**或**1**~**5000**。

 默认值：**-1**，表示不配置双向时延阈值。 |
|SmartAGId|String|sag-1um5x5nwhilymw\*\*\*\*|智能接入网关实例ID。 |
|SrcIpAddr|String|10.XX.XX.1|健康检查的源地址。 |
|SrcPort|Integer|2334|健康检查的源端口。

 **说明：** 该功能目前不支持。 |
|Type|String|ICMP\_ECHO|健康检查报文类型。

 目前仅支持**ICMP\_ECHO**。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=DescribeHealthCheckAttribute
&HcInstanceId=hc-1k4ucuq77b56x4****
&RegionId=cn-shanghai
&SmartAGId=sag-1um5x5nwhilymw****
&<公共请求参数>
```

正常返回示例

`XML`格式

```
<DescribeHealthCheckAttributeResponse>
  <CreateTime>1586759657000</CreateTime>
  <Description>TEST</Description>
  <SrcPort>44</SrcPort>
  <RequestId>66ECCDF6-7290-44A6-A2D0-3B926CEE82C6</RequestId>
  <SrcIpAddr>2.XX.XX.1</SrcIpAddr>
  <FailCountThreshold>3</FailCountThreshold>
  <DstPort>33</DstPort>
  <Name>TEST</Name>
  <ProbeCount>5</ProbeCount>
  <Type>ICMP_ECHO</Type>
  <ProbeTimeout>30</ProbeTimeout>
  <HcInstanceId>hc-l3x9k16ag24d6j****</HcInstanceId>
  <RttThreshold>-1</RttThreshold>
  <ProbeInterval>2000</ProbeInterval>
  <SmartAGId>sag-4goc1sj3c978z2****</SmartAGId>
  <RttFailThreshold>5</RttFailThreshold>
  <DstIpAddr>12.XX.XX.1</DstIpAddr>
</DescribeHealthCheckAttributeResponse>
```

`JSON`格式

```
{
	"CreateTime": 1586759657000,
    "Description": "TEST",
	"SrcPort": 44,
	"RequestId": "66ECCDF6-7290-44A6-A2D0-3B926CEE82C6",
	"SrcIpAddr": "2.XX.XX.1",
	"FailCountThreshold": 3,
	"DstPort": 33,
	"Name": "TEST",
	"ProbeCount": 5,
	"Type": "ICMP_ECHO",
	"ProbeTimeout": 30,
	"HcInstanceId": "hc-l3x9k16ag24d6j****",
	"RttThreshold": -1,
	"ProbeInterval": 2000,
	"SmartAGId": "sag-4goc1sj3c978z2****",
	"RttFailThreshold": 5,
	"DstIpAddr": "12.XX.XX.1"
}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|HC.InstanceNoFound|The specified network health check instance does not exist.|健康检查实例不存在。|

访问[错误中心](https://error-center.aliyun.com/status/product/Smartag)查看更多错误码。

