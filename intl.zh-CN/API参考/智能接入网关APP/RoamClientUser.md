# RoamClientUser

调用RoamClientUser实现智能接入网关APP客户端漫游，客户端可跨区域访问内网。

## 前提条件

在您执行本操作前，请先详细了解智能接入网关APP漫游功能及其说明。详情请参见[配置客户端漫游](~~177220~~)。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=RoamClientUser&type=RPC&version=2018-03-13)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|RoamClientUser|要执行的操作。

 取值：**RoamClientUser**。 |
|OriginRegionId|String|是|cn-shanghai|源智能接入网关APP实例所在的地域ID。 |
|OriginSmartAGId|String|是|sag-m9uhqekwnqcnyy\*\*\*\*|源智能接入网关APP实例ID。 |
|RegionId|String|是|cn-hangzhou|目的智能接入网关APP实例所在的地域ID。 |
|TargetSmartAGId|String|是|sag-ghwa10ko6ndwug\*\*\*\*|目的智能接入网关APP实例ID。 |
|UserName|String|是|test1|要漫游的客户端账号用户名。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|3200E8A3-563F-4FFC-8BDB-0F1263FA69E8|请求ID。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=RoamClientUser
&OriginRegionId=cn-shanghai
&OriginSmartAGId=sag-m9uhqekwnqcnyy****
&TargetSmartAGId=sag-ghwa10ko6ndwug****
&UserName=test1
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<RoamClientUserResponse>
  <RequestId>26C24B63-5E5A-413A-9E49-FC0C0AE9DFB7</RequestId>
</RoamClientUserResponse>
```

`JSON` 格式

```
{
	"RequestId": "26C24B63-5E5A-413A-9E49-FC0C0AE9DFB7"
}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|SAG.InstanceNoFound|The specified SAG instance does not exist.|智能网关实例不存在。|
|400|ClientUser.NotSupportAction|You cannot create a user in the current SAG instance.|当前智能网关实例不支持创建客户端用户。|
|400|SAG.CidrEmpty|You must specify the CIDR blocks of SAG.|智能网关地址段为空。|
|400|ClientUser.BandwidthInvalid|The specified Bandwidth is invalid.|用户带宽非法。|
|400|ClientUser.InvalidClientIp|The specified ClientIp is invalid.|非法的用户IP|
|400|ClientUser.UserOverLimit|The maximum number of users is exceeded.|用户数已超限|
|400|ClientUser.UserExist|The specified user already exists.|用户已经存在。|
|400|ClientUser.NameInvalid|The specified UserName is invalid.|用户名格式非法。|
|400|SAG.CidrOverlap|The specified CIDR overlaps with an existing CIDR.|存在重叠私网地址段。|

访问[错误中心](https://error-center.alibabacloud.com/status/product/Smartag)查看更多错误码。

