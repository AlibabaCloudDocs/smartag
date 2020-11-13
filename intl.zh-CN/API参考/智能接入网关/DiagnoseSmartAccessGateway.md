# DiagnoseSmartAccessGateway

调用DiagnoseSmartAccessGateway开启智能接入网关设备诊断。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=DiagnoseSmartAccessGateway&type=RPC&version=2018-03-13)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DiagnoseSmartAccessGateway|要执行的操作。

 取值：**DiagnoseSmartAccessGateway**。 |
|RegionId|String|是|cn-shanghai|智能接入网关实例所属地域ID。 |
|SmartAGId|String|是|sag-1um5x5nwhilymw\*\*\*\*|智能接入网关实例ID。 |
|SmartAGSn|String|是|sage62x022502\*\*\*\*|智能接入网关设备序列号。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|193AE392-76C2-4D3E-9420-889A51B43CC0|请求ID。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=DiagnoseSmartAccessGateway
&RegionId=cn-shanghai
&SmartAGId=sag-1um5x5nwhilymw****
&SmartAGSn=sage62x022502****
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<DiagnoseSmartAccessGatewayResponse>
  <RequestId>193AE392-76C2-4D3E-9420-889A51B43CC0</RequestId>
</DiagnoseSmartAccessGatewayResponse>
```

`JSON` 格式

```
{
	"RequestId": "193AE392-76C2-4D3E-9420-889A51B43CC0"
}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|MissingParameter|The input parameter is missing, please check your input.|输入参数缺失，请检查您的输入|

访问[错误中心](https://error-center.alibabacloud.com/status/product/Smartag)查看更多错误码。

