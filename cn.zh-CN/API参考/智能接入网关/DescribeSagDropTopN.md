# DescribeSagDropTopN

调用DescribeSagDropTopN查询指定地域丢包率前10名的智能接入网关实例。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=DescribeSagDropTopN&type=RPC&version=2018-03-13)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|DescribeSagDropTopN|要执行的操作。

 取值：**DescribeSagDropTopN**。 |
|RegionId|String|是|cn-shanghai|智能接入网关实例地域ID。 |
|Size|Integer|否|10|查询智能接入网关实例的数量。默认值：**10**，且不支持修改。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|DropTopN|Array| |智能接入网关实例丢包信息列表。 |
|DropRate|String|0.0|智能接入网关实例丢包率。单位：pps。 |
|InstanceId|String|sag-whfn\*\*\*\*|智能接入网关实例ID。 |
|Name|String|test|智能接入网关实例名称。 |
|RegionId|String|cn-shanghai|智能接入网关实例地域ID。 |
|RequestId|String|AFF7E5A6-6897-4FDC-A5A8-1978B5B3E545|请求ID。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=DescribeSagDropTopN
&RegionId=cn-shanghai
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<DescribeSagDropTopNResponse>
  <RequestId>58853663-5DFE-47A1-A69F-F0290BBFBC0A</RequestId>
  <DropTopN>
        <InstanceId>sag-p6ctq4o5bey3e9****</InstanceId>
        <RegionId>cn-shanghai</RegionId>
        <DropRate>0.0</DropRate>
        <Name>ccntest</Name>
  </DropTopN>
  <DropTopN>
        <InstanceId>sag-on7qvl3pv52l33****</InstanceId>
        <RegionId>cn-shanghai</RegionId>
        <DropRate>0.0</DropRate>
        <Name>Tutest</Name>
  </DropTopN>
  <DropTopN>
        <InstanceId>sag-7zyvg7fpk16p15****</InstanceId>
        <RegionId>cn-shanghai</RegionId>
        <DropRate>0.0</DropRate>
        <Name>chtest</Name>
  </DropTopN>
</DescribeSagDropTopNResponse>
```

`JSON` 格式

```
{
	"RequestId": "58853663-5DFE-47A1-A69F-F0290BBFBC0A",
	"DropTopN": [
		{
			"InstanceId": "sag-p6ctq4o5bey3e9****",
			"RegionId": "cn-shanghai",
			"DropRate": "0.0",
			"Name": "ccntest"
		},
		{
			"InstanceId": "sag-on7qvl3pv52l33****",
			"RegionId": "cn-shanghai",
			"DropRate": "0.0",
			"Name": "Tutest"
		},
		{
			"InstanceId": "sag-7zyvg7fpk16p15****",
			"RegionId": "cn-shanghai",
			"DropRate": "0.0",
			"Name": "chtest"
		}
	]
}
```

## 错误码

访问[错误中心](https://error-center.aliyun.com/status/product/Smartag)查看更多错误码。

