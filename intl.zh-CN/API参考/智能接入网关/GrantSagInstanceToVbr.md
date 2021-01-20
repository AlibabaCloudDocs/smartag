# GrantSagInstanceToVbr

调用GrantSagInstanceToVbr向跨账号边界路由器（VBR）实例授权。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=GrantSagInstanceToVbr&type=RPC&version=2018-03-13)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|GrantSagInstanceToVbr|要执行的操作。

 取值：**GrantSagInstanceToVbr**。 |
|RegionId|String|是|cn-shanghai|智能接入网关实例所属地域ID。 |
|SmartAGId|String|是|sag-0nnteglltw6z4b\*\*\*\*|智能接入网关实例ID。 |
|VbrInstanceId|String|是|vbr-bp13gtbhdp0pfqg6s\*\*\*\*|边界路由器实例ID。 |
|VbrRegionId|String|是|cn-hangzhou|边界路由器实例所在地域ID。 |
|VbrUid|Long|是|1231212121121212112|边界路由器实例所属账号UID。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|InstanceId|String|sgv-3x8djyem7vqh70\*\*\*\*|授权实例ID。 |
|RequestId|String|49CEBB2B-9E5C-4789-8A29-3255A56A67B1|请求ID。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=GrantSagInstanceToVbr
&RegionId=cn-shanghai
&SmartAGId=sag-0nnteglltw6z4b****
&VbrInstanceId=vbr-bp13gtbhdp0pfqg6s****
&VbrRegionId=cn-hangzhou
&VbrUid=1231212121121212112
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<GrantSagInstanceToVbrResponse>
  <RequestId>49CEBB2B-9E5C-4789-8A29-3255A56A67B1</RequestId>
  <InstanceId>sgv-3x8djyem7vqh70****</InstanceId>
</GrantSagInstanceToVbrResponse>
```

`JSON` 格式

```
{
	"RequestId": "49CEBB2B-9E5C-4789-8A29-3255A56A67B1",
	"InstanceId": "sgv-3x8djyem7vqh70****"
}
```

## 错误码

访问[错误中心](https://error-center.alibabacloud.com/status/product/Smartag)查看更多错误码。

