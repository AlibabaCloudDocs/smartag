# AddSnatEntry {#doc_api_Smartag_AddSnatEntry .reference}

调用AddSnatEntry给智能接入网关实例添加私网SNAT条目。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Smartag&api=AddSnatEntry)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|CidrBlock|String|是|192.168.0.1/24|目标网段。

 |
|RegionId|String|是|cn-hangzhou|智能接入网关实例所在的地域ID。

 |
|SmartAGId|String|是|sag-hgke\*\*\*\*\*\*\*\*\*\*\*\*\*|智能接入网关实例ID。

 |
|SnatIp|String|是|10.0.\*\*.\*\*|公网IP地址。

 |
|Action|String|否|AddSnatEntry|要执行的操作。

 取值：**AddSnatEntry**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|InstanceId|String|snat-m2obgkt5ya1puz\*\*\*\*|SNAT实例ID。

 |
|RequestId|String|56BF6C79-C77D-41A0-86DD-A4B156E784EA|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=AddSnatEntry
&CidrBlock=192.168.0.1/24
&RegionId=cn-hangzhou
&SmartAGId=sag-hgke*************
&SnatIp=10.0.**.**
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<AddSnatEntryResponse>
  <InstanceId>snat-m2obgkt5ya1puz8qh1</InstanceId>
  <RequestId>56BF6C79-C77D-41A0-86DD-A4B156E784EA</RequestId>
</AddSnatEntryResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"56BF6C79-C77D-41A0-86DD-A4B156E784EA",
	"InstanceId":"snat-m2obgkt5ya1puz8qh1"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|FeatureNotSupport|The current edition of the smart access gateway does not support this feature.|智能接入网关当前版本不支持该功能特性|
|400|SAG.InstanceNoFound|The specified SAG instance does not exist.|智能网关实例不存在。|
|500|SmartAccessGatewayInArrears|The specified Smart Access Gateway has expired.|该智能接入网关已经到期停服，请续费。|
|500|SmartAccessGatewayNotActivated|The specified Smart Access Gateway has not been activated.|该智能接入网关尚未激活，请先激活该实例。|
|400|SNAT.CidrConfigExist|The specified SNAT CIDR block already exists.|SNAT地址段已经存在。|
|400|SNAT.AmountLimit|The maximum number of SNAT entries is exceeded.|SNAT条目已经到达上限。|
|400|SNAT.SnatDnatIpConflict|The SNAT destination IP address is the same as the DNAT IP address.|SNAT目标IP与DNAT IP冲突|
|403|FeatureNotSupportForStandBySmartAG|The current edition of the standby smart access gateway does not support this feature.|备智能接入网关的当前版本不支持该功能特性|
|500|InternalError|An error occurred while processing your request.|请求失败，发生未知错误。|

访问[错误中心](https://error-center.alibabacloud.com/status/product/Smartag)查看更多错误码。

