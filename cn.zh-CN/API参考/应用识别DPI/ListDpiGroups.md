# ListDpiGroups

调用ListDpiGroups查询指定地域下智能接入网关支持的应用组信息。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=ListDpiGroups&type=RPC&version=2018-03-13)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|ListDpiGroups|要执行的操作。

 取值：**ListDpiGroups**。 |
|RegionId|String|是|cn-shanghai|地域ID。

 您可以通过[DescribeRegions](~~69813~~)查询智能接入网关支持的地域以及对应的地域ID。 |
|NextToken|String|否|FFPSpX59Eb\*\*\*\*|下一页查询开始的Token。 |
|MaxResults|Integer|否|3|列表分页查询时每页展示的应用组个数。

 取值范围：**1**~**100**。

 默认值：**20**。 |
|DpiGroupIds.N|RepeatList|否|1|应用组ID。

 系统允许您通过应用组ID指定查询一个或多个应用组信息，您一次最多可以查询10个指定的应用组信息。 |
|DpiGroupNames.N|RepeatList|否|P2P|应用组名称。

 系统允许您通过应用组名称指定查询一个或多个应用组信息，您一次最多可以查询10个指定的应用组信息。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|DpiGroup|Array of DpiGroup| |应用组信息列表。 |
|DpiGroupId|String|1|应用组ID。 |
|DpiGroupName|String|P2P|应用组名称。 |
|MinEngineVersion|String|0-0.0.1|支持该应用组的最低引擎版本。 |
|MinSignatureDbVersion|String|20201117\_1\_0-0.0.1|支持该应用组的最低特征库版本。 |
|NextToken|String|FFPSpX59Ebw\*\*\*\*|下一页查询开始的Token。 |
|RequestId|String|EC184A86-3C93-49D6-BB34-6C193E14D37F|请求ID。 |
|TotalCount|Integer|22|当前接口查询出来的应用组总个数。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=ListDpiGroups
&RegionId=cn-shanghai
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<ListDpiGroupsResponse>
  <TotalCount>22</TotalCount>
  <RequestId>9E753114-BAF3-4676-9572-377FED18446D</RequestId>
  <NextToken>FFPSpX59Ebw****</NextToken>
  <DpiGroup>
        <MinEngineVersion>0-0.0.1</MinEngineVersion>
        <DpiGroupName>P2P</DpiGroupName>
        <MinSignatureDbVersion>20201117_1_0-0.0.1</MinSignatureDbVersion>
        <DpiGroupId>1</DpiGroupId>
  </DpiGroup>
  <DpiGroup>
        <MinEngineVersion>0-0.0.1</MinEngineVersion>
        <DpiGroupName>VoIP</DpiGroupName>
        <MinSignatureDbVersion>20201117_1_0-0.0.1</MinSignatureDbVersion>
        <DpiGroupId>2</DpiGroupId>
  </DpiGroup>
</ListDpiGroupsResponse>
```

`JSON` 格式

```
{
	"TotalCount": 22,
	"RequestId": "9E753114-BAF3-4676-9572-377FED18446D",
	"NextToken": "FFPSpX59Ebw****",
	"DpiGroup": [
		{
			"MinEngineVersion": "0-0.0.1",
			"DpiGroupName": "P2P",
			"MinSignatureDbVersion": "20201117_1_0-0.0.1",
			"DpiGroupId": "1"
		},
		{
			"MinEngineVersion": "0-0.0.1",
			"DpiGroupName": "VoIP",
			"MinSignatureDbVersion": "20201117_1_0-0.0.1",
			"DpiGroupId": "2"
		}
	]
}
```

## 错误码

访问[错误中心](https://error-center.aliyun.com/status/product/Smartag)查看更多错误码。

