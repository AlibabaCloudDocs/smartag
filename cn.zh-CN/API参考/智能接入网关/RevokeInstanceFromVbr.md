# RevokeInstanceFromVbr

调用RevokeInstanceFromVbr取消跨账号边界路由器（VBR）实例授权。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=RevokeInstanceFromVbr&type=RPC&version=2018-03-13)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|RevokeInstanceFromVbr|要执行的操作。

 取值：**RevokeInstanceFromVbr**。 |
|RegionId|String|是|cn-shanghai|智能接入网关实例所属地域ID。 |
|SmartAGId|String|是|sag-0nnteglltw6z4b\*\*\*\*|智能接入网关实例ID。 |
|VbrInstanceId|String|是|vbr-bp13gtbhdp0pfqg6s\*\*\*\*|边界路由器实例ID。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|D085AE49-51DC-4E8A-9F06-2D99C4E374F7|请求ID。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=RevokeInstanceFromVbr
&RegionId=cn-shanghai
&SmartAGId=sag-0nnteglltw6z4b****
&VbrInstanceId=vbr-bp13gtbhdp0pfqg6s****
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<RevokeInstanceFromVbrResponse>
  <RequestId>D085AE49-51DC-4E8A-9F06-2D99C4E374F7</RequestId>
</RevokeInstanceFromVbrResponse>
```

`JSON` 格式

```
{
	"RequestId": "D085AE49-51DC-4E8A-9F06-2D99C4E374F7"
}
```

## 错误码

访问[错误中心](https://error-center.aliyun.com/status/product/Smartag)查看更多错误码。

