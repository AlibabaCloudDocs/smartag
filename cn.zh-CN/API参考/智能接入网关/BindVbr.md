# BindVbr {#doc_api_Smartag_BindVbr .reference}

调用BindVbr绑定边界路由器。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=BindVbr&type=RPC&version=2018-03-13)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|RegionId|String|是|cn-hangzhou|智能接入网关实例所属的地域ID。

 |
|SmartAGId|String|是|sag-jed\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*|智能接入网关实例ID。

 |
|VbrId|String|是|vbr-shf\*\*\*\*\*\*\*\*\*\*\*\*|要绑定的边界路由器实例ID。

 |
|VbrRegionId|String|是|cn-hangzhou|要绑定的边界路由器实例所属的地域ID。

 |
|Action|String|否|BindVbr|要执行的操作。

 取值：**BindVbr**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|09A2010F-602B-4EC6-A60F-9914AAE2DCA0|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=BindVbr
&RegionId=cn-hangzhou
&SmartAGId=sag-jed****************
&VbrId=vbr-shf************
&VbrRegionId=cn-hangzhou
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<BindVbrResponse>
	  <RequestId>09A2010F-602B-4EC6-A60F-9914AAE2DCA0</RequestId>
    </BindVbrResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"09A2010F-602B-4EC6-A60F-9914AAE2DCA0"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|Forbbiden.SubUser|You are not authorized to operate on the specified resource.|您不具有操作指定资源的权限|
|403|Forbidden|User not authorized to operate on the specified resource.|用户没有操作此资源的权限|
|403|InvalidId.SMARTAG|The specified smart access gateway instance id is invalid.|无效的智能接入网关ID|
|400|InvalidId.VBR|The specified VBR instance is invalid. You must specify a VBR instance that is associated with an ECC instance.|非法的vbr，当前vbr实例不是来自ecc实例。|
|400|SAG.SoftwareNoSupportVbr|You cannot bind an SAG software instance with a VBR instance.|智能接入网关软件版不被允许绑定VBR|
|403|NotBoundCCN|The specified smart access gateway has not bound CCN; please bind CCN first.|该智能接入网关没有绑定CCN；请先绑定CCN。|
|403|FeatureNotSupport|The current edition of the smart access gateway does not support this feature.|智能接入网关当前版本不支持该功能特性|
|400|SAG.VbrNotBondCen|Bind the specified VBR instance to a CEN instance first.|当前VBR还未绑定到CEN，请先绑定CEN。|
|403|VbrConflict.CreateBackup|The subnet of the gateway conflicts with the VBR. Create a backup relationship first.|该智能接入网关的子网网段与VBR有冲突，请先创建专线备份。|
|400|SAG.VbrBound|The specified SAG instance is bound to another VBR instance. Unbind them first.|已经绑定VBR，请先解绑。|
|400|LinkLevelBackupExists|The specified SAG instance is already used as a leased line backup.|当前实例已经存在专线备份。|
|400|SAG.VbrBoundToSAG|The specified VBR instance is bound to another SAG instance. Unbind them first.|当前VBR已经绑定到其他SAG，请先解绑。|
|500|InternalError|An error occurred while processing your request.|请求失败，发生未知错误。|

访问[错误中心](https://error-center.aliyun.com/status/product/Smartag)查看更多错误码。

