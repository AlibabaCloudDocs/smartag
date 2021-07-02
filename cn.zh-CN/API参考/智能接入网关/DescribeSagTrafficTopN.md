# DescribeSagTrafficTopN

调用DescribeSagTrafficTopN查询指定地域流量速率为前10名的智能接入网关实例。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=DescribeSagTrafficTopN&type=RPC&version=2018-03-13)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|DescribeSagTrafficTopN|要执行的操作。

 取值：**DescribeSagTrafficTopN**。 |
|RegionId|String|是|cn-shanghai|智能接入网关实例地域ID。 |
|Size|Integer|否|10|查询智能接入网关实例的数量。默认值：**10**，且不支持修改。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|AFF7E5A6-6897-4FDC-A5A8-1978B5B3E545|请求ID。 |
|TrafficTopN|Array| |智能接入网关实例流量速率信息列表。 |
|InstanceId|String|sag-whfn\*\*\*\*|智能接入网关实例ID。 |
|Name|String|test|智能接入网关实例名称。 |
|RegionId|String|cn-shanghai|智能接入网关实例地域ID。 |
|TrafficRate|String|3866.6666666666665|智能接入网关实例流量速率。单位：bps。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=DescribeSagTrafficTopN
&RegionId=cn-shanghai
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<DescribeSagTrafficTopNResponse>
  <RequestId>0390E09B-8824-4B79-A27E-35BE65DA8E48</RequestId>
  <TrafficTopN>
        <InstanceId>sag-moa1tjqpa7zbik****</InstanceId>
        <TrafficRate>3900.0</TrafficRate>
        <RegionId>cn-shanghai</RegionId>
        <Name>jitest</Name>
  </TrafficTopN>
  <TrafficTopN>
        <InstanceId>sag-7zyvg7fpk16p15****</InstanceId>
        <TrafficRate>1243.2</TrafficRate>
        <RegionId>cn-shanghai</RegionId>
        <Name>chutest</Name>
  </TrafficTopN>
</DescribeSagTrafficTopNResponse>
```

`JSON` 格式

```
{
	"RequestId": "0390E09B-8824-4B79-A27E-35BE65DA8E48",
	"TrafficTopN": [

		{
			"InstanceId": "sag-moa1tjqpa7zbik****",
			"TrafficRate": "3900.0",
			"RegionId": "cn-shanghai",
			"Name": "jitest"
		},
		{
			"InstanceId": "sag-7zyvg7fpk16p15****",
			"TrafficRate": "1243.2",
			"RegionId": "cn-shanghai",
			"Name": "chutest"
		}
	]
}
```

## 错误码

访问[错误中心](https://error-center.aliyun.com/status/product/Smartag)查看更多错误码。

