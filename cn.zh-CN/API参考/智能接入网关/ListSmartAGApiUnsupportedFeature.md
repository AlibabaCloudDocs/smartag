# ListSmartAGApiUnsupportedFeature

调用ListSmartAGApiUnsupportedFeature查询指定智能接入网关设备不支持的功能特性。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=ListSmartAGApiUnsupportedFeature&type=RPC&version=2018-03-13)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|ListSmartAGApiUnsupportedFeature|要执行的操作。

 取值：**ListSmartAGApiUnsupportedFeature**。 |
|OpenApiName|String|是|ModifySagWan|功能特性相关的Open API名称。 |
|RegionId|String|是|cn-shanghai|智能接入网关实例所属的地域ID。 |
|SerialNumber|String|是|sage62x052614\*\*\*\*|智能接入网关设备序列号。 |
|SmartAGId|String|是|sag-4d6i45zess8nj4\*\*\*\*|智能接入网关设备所属的智能接入网关实例ID。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|Features|Array of Feature| |功能特性列表。 |
|Feature|String|ISP|功能特性。

 关于每个功能特性的描述信息，请您查看对应的Open API文档。 |
|RequestId|String|7459545D-2F0D-43E6-9957-CB7E0223332B|请求ID。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=ListSmartAGApiUnsupportedFeature
&OpenApiName=ModifySagWan
&RegionId=cn-shanghai
&SerialNumber=sage62x052614****
&SmartAGId=sag-4d6i45zess8nj4****
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<ListSmartAGApiUnsupportedFeatureResponse>
  <RequestId>7459545D-2F0D-43E6-9957-CB7E0223332B</RequestId>
  <Features>
        <Feature>Weight</Feature>
  </Features>
  <Features>
        <Feature>ISP</Feature>
  </Features>
  <Features>
        <Feature>BandWidth</Feature>
  </Features>
</ListSmartAGApiUnsupportedFeatureResponse>
```

`JSON` 格式

```
{
	"RequestId": "7459545D-2F0D-43E6-9957-CB7E0223332B",
	"Features": [
		{
			"Feature": "Weight"
		},
		{
			"Feature": "ISP"
		},
		{
			"Feature": "BandWidth"
		}
	]
}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidSmartAGId.NotFound|The specified SmartAGId does not exist.|根据SmartAGId未找到对应实例。|
|400|Sag.DeviceNotExist|The specified device does not exist.|当前设备不存在|

访问[错误中心](https://error-center.aliyun.com/status/product/Smartag)查看更多错误码。

