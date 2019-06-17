# ModifySmartAccessGateway {#doc_api_Smartag_ModifySmartAccessGateway .reference}

调用ModifySmartAccessGateway修改智能接入网关的配置。

TEST

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Smartag&api=ModifySmartAccessGateway)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|RegionId|String|是|cn-hangzhou|智能接入网关的所属区域。

 |
|SmartAGId|String|是|sag-0ovhf732a9j0\*\*\*\*\*\*|智能接入网关ID。

 |
|Action|String|否|ModifySmartAccessGateway|要执行的操作。

 取值： **ModifySmartAccessGateway**

 |
|CidrBlock|String|否|172.16.0.1/24|线下机构客户端用来通信的私网网段，确保各私网网段不冲突。

 如果智能接入网关终端设备的LAN口配置为动态方式，则线下已开启DHCP的客户端使用的IP地址会从您指定的第一个私网网段中分配。

 |
|Description|String|否|sag描述|智能接入网关的描述。

 长度为2-256个字符，必须以字母或中文开头，但不能以`http://`或`https:/`/开头。

 |
|Name|String|否|sag|智能接入网关的名称。

 长度为2-128个字符，必须以字母或中文开头，可包含数字，点号（.），下划线（\_）和短横线（-），但不能以`http://` 或`https://`开头。

 |
|SecurityLockThreshold|Integer|否|3|离线锁定功能用户设定的阈值，大于等于0。

 单位：秒

 |
|SnatEntries.N.CidrBlock|String|否|172.16.22.0/24|配置本地终端接入阿里云使用的私网网段。

 |
|SnatEntries.N.SnatIp|String|否|172.16.22.5|外网地址是云连接网SNAT网段内的一个IP地址，不填则系统自动分配。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|CE6642D4-21EB-4168-9BF9-F217953F9892|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://smartag.cn-shanghai.aliyuncs.com/?Action=ModifySmartAccessGateway
&SmartAGId=sag-0ovhf732a9j0pt0aeo
&Name=DocTest
&CommonParameters

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ModifySmartAccessGatewayResponse>
  <RequestId>CE6642D4-21EB-4168-9BF9-F217953F9892</RequestId>
</ModifySmartAccessGatewayResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"CE6642D4-21EB-4168-9BF9-F217953F9892"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|CidrConflict|Cidr is conflict, Please Check your input.|子网网段冲突，请检查输入|
|403|MissingParameter|The input parameter is missing, please check your input.|输入参数缺失，请检查您的输入|
|403|InvalidId.SMARTAG|The specified smart access gateway instance id is invalid.|无效的智能接入网关ID|
|403|InvalidCidr|Cidr is illegal, please check your input.|Cidr不合法，请检查您的输入|
|403|Forbidden|User not authorized to operate on the specified resource.|用户没有操作此资源的权限|
|500|SmartAccessGatewayInArrears|The specified Smart Access Gateway has expired.|该智能接入网关已经到期停服，请续费。|
|500|SmartAccessGatewayNotActivated|The specified Smart Access Gateway has not been activated.|该智能接入网关尚未激活，请先激活该实例。|
|403|VbrConflict.ChangeSubnet|The subnet of the gateway conflicts with the VBR. Modify the subnet first.|该智能接入网关的子网网段与VBR有冲突，请修改子网网段。|
|403|VbrConflict.CreateBackup|The subnet of the gateway conflicts with the VBR. Create a backup relationship first.|该智能接入网关的子网网段与VBR有冲突，请先创建专线备份。|
|403|SmartAccessGatewayNotBind|The instance has not yet been bound.|该实例未被绑定|

[查看本产品错误码](https://error-center.aliyun.com/status/product/Smartag)

