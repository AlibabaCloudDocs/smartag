# ListAccessPoints

调用ListAccessPoints查询智能接入网关接入点信息。

## 背景信息

接入点是指智能接入网关接入云连接网时的连接点。云连接网在一些区域内包含多个接入点。智能接入网关实例绑定云连接网后，系统采取就近原则，自动帮您连接最近的接入点进入阿里云。您可以通过本API查询指定区域内的接入点信息。云连接网区域详情请参见[云连接网介绍](~~93667~~)。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=ListAccessPoints&type=RPC&version=2018-03-13)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|ListAccessPoints|要执行的操作。

 取值：**ListAccessPoints**。 |
|RegionId|String|是|cn-hangzhou|要查询的接入点所属地域ID。您可以通过[DescribeRegions](~~36063~~)查询地域ID。 |
|PageSize|Integer|否|20|分页查询时每页的条目数。 |
|SmartAGId|String|否|sag-far8v6owtdxlua\*\*\*\*|智能接入网关实例ID。 |
|PageNumber|Integer|否|1|分页查询时的页码，默认值为**1**。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|AccessPoints|Array of AccessPoint| |接入点信息。 |
|AccessPointId|Integer|401|接入点ID。 |
|ActiveSmartAGCount|Integer|0|当前接入点下可用的智能接入网关实例数量。 |
|InactiveSmartAGCount|Integer|7|当前接入点下离线的智能接入网关实例数量。 |
|Latitude|String|103.81\*\*\*\*|接入点纬度。 |
|Longitude|String|1.35\*\*\*\*|接入点经度。 |
|RequestId|String|E26DBAAE-A796-4A48-98B4-B45AFCD1F299|请求ID。 |
|TotalCount|Integer|2|接入点总个数。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=ListAccessPoints
&RegionId=cn-hangzhou
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<ListAccessPointsResponse>
  <AccessPoints>
        <AccessPointId>401</AccessPointId>
        <ActiveSmartAGCount>0</ActiveSmartAGCount>
        <Latitude>103.81****</Latitude>
        <InactiveSmartAGCount>7</InactiveSmartAGCount>
        <Longitude>1.35****</Longitude>
  </AccessPoints>
  <AccessPoints>
        <AccessPointId>402</AccessPointId>
        <ActiveSmartAGCount>0</ActiveSmartAGCount>
        <Latitude>24.6****</Latitude>
        <InactiveSmartAGCount>13</InactiveSmartAGCount>
        <Longitude>-28.4****</Longitude>
  </AccessPoints>
  <TotalCount>2</TotalCount>
  <RequestId>E26DBAAE-A796-4A48-98B4-B45AFCD1F299</RequestId>
</ListAccessPointsResponse>
```

`JSON` 格式

```
{
	"AccessPoints": [
		{
			"AccessPointId": 401,
			"ActiveSmartAGCount": 0,
			"Latitude": "103.81****",
			"InactiveSmartAGCount": 7,
			"Longitude": "1.35****"
		},
		{
			"AccessPointId": 402,
			"ActiveSmartAGCount": 0,
			"Latitude": "24.6****",
			"InactiveSmartAGCount": 13,
			"Longitude": "-28.4****"
		}
	],
	"TotalCount": 2,
	"RequestId": "E26DBAAE-A796-4A48-98B4-B45AFCD1F299"
}
```

## 错误码

访问[错误中心](https://error-center.aliyun.com/status/product/Smartag)查看更多错误码。

