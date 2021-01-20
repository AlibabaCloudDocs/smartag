# GrantSagInstanceToCcn

调用GrantSagInstanceToCcn将智能接入网关实例授权给跨账号的云连接网实例。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=GrantSagInstanceToCcn&type=RPC&version=2018-03-13)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|GrantSagInstanceToCcn|要执行的操作。

 取值：**GrantSagInstanceToCcn**。 |
|CcnInstanceId|String|是|ccn-jdh\*\*\*\*\*\*\*\*\*\*|云连接网实例ID。 |
|CcnUid|Long|是|123456|云连接网实例所属的账号ID。 |
|RegionId|String|是|cn-hangzhou|智能接入网关实例所属的地域ID。 |
|SmartAGId|String|是|sag-hdh\*\*\*\*\*\*\*\*\*\*\*\*|智能接入网关实例ID。 |
|GrantTrafficService|Boolean|否|true|是否给跨账号的云连接网实例授权智能接入网关实例的流量服务能力。

 授权成功后，跨账号云连接网实例可以引导智能接入网关实例去往公网的流量做安全审计。

 -   **true**：授权。
-   **false**：不授权。

 **说明：** 在您授权成功后，如果智能接入网关实例开启了安全引流功能，则不允许取消授权。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|InstanceId|String|sgc-e8lgeu4wzf\*\*\*\*\*\*\*|授权成功后返回的授权实例ID。 |
|RequestId|String|6E1674AC-083C-4031-B047-7A66E418E0C6|请求ID。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=GrantSagInstanceToCcn
&CcnInstanceId=ccn-jdh**********
&CcnUid=123535455445666
&RegionId=cn-hangzhou
&SmartAGId=sag-hdh************
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<GrantSagInstanceToCcnResponse>
  <InstanceId>sgc-e8lgeu4w********</InstanceId>
  <RequestId>5F40561D-1EB7-48CB-AA5B-79713E003356</RequestId>
</GrantSagInstanceToCcnResponse>
```

`JSON` 格式

```
{
    "InstanceId":"sgc-e8lgeu4w********",
    "RequestId":"5F40561D-1EB7-48CB-AA5B-79713E003356"
}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|CCN.InvalidUid|The specified CCN user ID is invalid.|非法的云连接网用户ID。|
|400|CCN.InvalidId|You must specify the CCN instance ID.|云连接网实例ID不存在。|
|400|SAG.InstanceIdEmpty|You must specify the SAG instance ID.|智能网关实例ID为空。|
|400|SAG.InstanceNoFound|The specified SAG instance does not exist.|智能网关实例不存在。|
|400|SAG.GrantDuplicated|You have authorized another CCN instance to bind to the specified SAG instance. Revoke the authorization first.|当前SAG实例已经被授权给其他CCN实例，请先解除授权。|

访问[错误中心](https://error-center.alibabacloud.com/status/product/Smartag)查看更多错误码。

