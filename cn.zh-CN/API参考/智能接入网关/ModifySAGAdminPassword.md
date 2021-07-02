# ModifySAGAdminPassword

调用ModifySAGAdminPassword接口修改智能接入网关设备的登录密码。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=ModifySAGAdminPassword&type=RPC&version=2018-03-13)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|ModifySAGAdminPassword|要执行的操作。取值：**ModifySAGAdminPassword**。 |
|RegionId|String|是|cn-shanghai|智能接入网关实例所属地域ID。 |
|SmartAGId|String|是|sag-tq3sazs17smldn\*\*\*\*|智能接入网关实例ID。 |
|SmartAGSn|String|是|sag32a30\*\*\*\*|智能接入网关设备序列号。 |
|Password|String|是|\*\*\*\*\*\*\*\*|智能接入网关设备新的登录密码。

 密码格式要求：密码长度为8~30个字符，可包含大小写字母、数字和下划线（\_）。

 **说明：** 示例值中使用星号（\*）以掩盖真实密码，不表示密码支持使用星号（\*），输入密码时请以密码格式要求为准。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|DB0A026C-A8E5-40AB-977E-3A87DD78F694|请求ID。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=ModifySAGAdminPassword
&RegionId=cn-shanghai
&SmartAGId=sag-tq3sazs17smldn****
&SmartAGSn=sag32a30****
&Password=********
&公共请求参数
```

正常返回示例

`XML`格式

```
HTTP/1.1 200 OK
Content-Type:application/xml

<ModifySAGAdminPasswordResponse>
    <RequestId>DB0A026C-A8E5-40AB-977E-3A87DD78F694</RequestId>
</ModifySAGAdminPasswordResponse>
```

`JSON`格式

```
HTTP/1.1 200 OK
Content-Type:application/json

{
  "RequestId" : "DB0A026C-A8E5-40AB-977E-3A87DD78F694"
}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|IllegalParam.Password|The specified Password is invalid.|参数Password非法。|
|400|MissingParam.Password|You must specify Password.|缺少参数Password。|
|400|SAG.InstanceNoFound|The specified SAG instance does not exist.|智能网关实例不存在。|
|400|SAG.SoftwareNotSupport|The specified SAG software edition instance does not support ACL.|智能接入网关软件版实例不支持ACL。|
|400|SAG.SoftwareNotSupportFeature|The specified SAG Software instance does not support this feature.|智能接入网关软件版实例不支持当前特性。|
|400|SmartAccessGatewayInArrears|The specified Smart Access Gateway has expired.|该智能接入网关已经到期停服，请续费。|
|400|SmartAccessGatewayNotActivated|The specified Smart Access Gateway has not been activated.|该智能接入网关尚未激活，请先激活该实例。|
|400|SmartAccessGatewayOffline|The request cannot be completed. The Smart Access Gateway is offline.|智能接入网关离线，请求无法完成。|
|400|InstanceNotExit|The specified instance does not exist.|指定的实例不存在。|
|400|ConfigUnsynchronized|The network configuration is not synchronized.|网络配置未同步。|
|403|SmartAccessGatewayNotOnline|The specified smart access gateway is not online.|该智能接入网关当前不是在线状态，无法完成操作。|
|403|FeatureNotSupport|The current edition of the smart access gateway does not support this feature.|智能接入网关当前版本不支持该功能特性。|
|403|FeatureNotSupportForActiveSmartAG|The current edition of the active smart access gateway does not support this feature.|主智能接入网关的当前版本不支持该功能特性。|
|403|FeatureNotSupportForStandBySmartAG|The current edition of the standby smart access gateway does not support this feature.|备智能接入网关的当前版本不支持该功能特性。|

访问[错误中心](https://error-center.aliyun.com/status/product/Smartag)查看更多错误码。

