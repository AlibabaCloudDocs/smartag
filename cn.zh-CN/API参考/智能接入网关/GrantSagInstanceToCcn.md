# GrantSagInstanceToCcn {#doc_api_Smartag_GrantSagInstanceToCcn .reference}

调用GrantSagInstanceToCcn跨账号授权智能接入网关实例可以加入云连接网CCN。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=GrantSagInstanceToCcn&type=RPC&version=2018-03-13)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|CcnInstanceId|String|是|ccn-jdh\*\*\*\*\*\*\*\*\*\*|云连接网实例ID。

 |
|CcnUid|Long|是|123535455445666|云连接网实例所属的用户ID。

 |
|RegionId|String|是|cn-hangzhou|智能接入网关实例所属的实例ID。

 |
|SmartAGId|String|是|sag-hdh\*\*\*\*\*\*\*\*\*\*\*\*|智能接入网关实例ID。

 |
|Action|String|否|GrantSagInstanceToCcn|要执行的操作。

 取值：**GrantSagInstanceToCcn**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|InstanceId|String|sgc-e8lgeu4wzf\*\*\*\*\*\*\*|跨账号授权成功后返回的ID。

 |
|RequestId|String|6E1674AC-083C-4031-B047-7A66E418E0C6|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=GrantSagInstanceToCcn
&CcnInstanceId=ccn-jdh**********
&CcnUid=123535455445666
&RegionId=cn-hangzhou
&SmartAGId=sag-hdh************
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<GrantSagInstanceToCcnResponse>
	  <InstanceId>sgc-e8lgeu4wzfzxpwhel1</InstanceId>
	  <RequestId>5F40561D-1EB7-48CB-AA5B-79713E003356</RequestId>
    </GrantSagInstanceToCcnResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"5F40561D-1EB7-48CB-AA5B-79713E003356",
	"InstanceId":"sgc-e8lgeu4w********"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|CCN.InvalidUid|The specified CCN user ID is invalid.|非法的云连接网用户ID|
|400|CCN.InvalidId|You must specify the CCN instance ID.|云连接网实例ID不存在。|
|400|SAG.InstanceIdEmpty|You must specify the SAG instance ID.|智能网关实例ID为空。|
|400|SAG.InstanceNoFound|The specified SAG instance does not exist.|智能网关实例不存在。|
|400|SAG.GrantDuplicated|You have authorized another CCN instance to bind to the specified SAG instance. Revoke the authorization first.|当前SAG实例已经被授权给其他CCN实例，请先解除授权。|

访问[错误中心](https://error-center.aliyun.com/status/product/Smartag)查看更多错误码。

