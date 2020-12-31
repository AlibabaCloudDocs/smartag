# GrantInstanceToCbn

调用GrantInstanceToCbn将云连接网实例授权给跨账号云企业网实例。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=GrantInstanceToCbn&type=RPC&version=2018-03-13)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|GrantInstanceToCbn|要执行的操作。

 取值：**GrantInstanceToCbn**。 |
|CcnInstanceId|String|是|ccn-n2935s1mnwv8i\*\*\*\*\*|云连接网实例ID。 |
|CenInstanceId|String|是|cen-7qthudw0ll6jm\*\*\*\*\*|云企业网实例ID。 |
|CenUid|Long|是|123456789|云企业网实例所属的账号ID。 |
|RegionId|String|是|cn-shanghai|云连接网实例所属的地域ID。 |
|GrantTrafficService|Boolean|否|true|是否给跨账号的云企业网实例授权云连接网实例的流量服务能力。

 -   **true**：授权。
-   **false**：（默认值）不授权。

 **说明：** 在您授权成功后，如果云连接网下的智能接入网关实例开启了安全引流功能，则不允许取消授权。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|22840034-ADE9-41D8-A5DC-A7CF435CEE75|请求ID。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=GrantInstanceToCbn
&CcnInstanceId=ccn-n2935s1mnwv8i*****
&CenInstanceId=cen-7qthudw0ll6jm*****
&CenUid=123456789
&RegionId=cn-shanghai
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<GrantInstanceToCbnResponse>
  <RequestId>22840034-ADE9-41D8-A5DC-A7CF435CEE75</RequestId>
</GrantInstanceToCbnResponse>
```

`JSON` 格式

```
{
	"RequestId": "22840034-ADE9-41D8-A5DC-A7CF435CEE75"
}
```

## 错误码

访问[错误中心](https://error-center.aliyun.com/status/product/Smartag)查看更多错误码。

