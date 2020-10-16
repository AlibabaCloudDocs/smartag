# ClearSagCipher

调用ClearSagCipher重置智能接入网关（VCPE）设备密钥。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=ClearSagCipher&type=RPC&version=2018-03-13)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|ClearSagCipher|要执行的操作。

 取值：**ClearSagCipher**。 |
|RegionId|String|是|cn-shanghai|智能接入网关实例所属地域ID。 |
|SagId|String|是|sag-0nnteglltw6z4b\*\*\*\*|智能接入网关实例ID。 |
|SnNumber|String|是|sag42c3\*\*\*\*|智能接入网关（VCPE）设备序列号。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|3712F0B2-721E-4FBF-BBEF-888E3BFE0A20|请求ID。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=ClearSagCipher
&RegionId=cn-shanghai
&SagId=sag-0nnteglltw6z4b****
&SnNumber=sag42c3****
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<ClearSagCipherResponse>
  <RequestId>69E19A6D-8114-4D57-94A0-14CC7CA578C8</RequestId>
</ClearSagCipherResponse>
```

`JSON` 格式

```
{
	"RequestId": "69E19A6D-8114-4D57-94A0-14CC7CA578C8"
}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|MissingParameter|The input parameter is missing, please check your input.|输入参数缺失，请检查您的输入|

访问[错误中心](https://error-center.aliyun.com/status/product/Smartag)查看更多错误码。

