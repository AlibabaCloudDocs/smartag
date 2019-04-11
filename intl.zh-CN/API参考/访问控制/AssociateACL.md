# AssociateACL {#doc_api_1162897 .reference}

调用AssociateACL将访问控制与智能接入网关实例绑定。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Smartag&api=AssociateACL)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|AclId|String|是|acl-ohlexqptfhy\*\*\*\*\*\*|访问控制ID。

 |
|RegionId|String|是|cn-hangzhou|地域ID。

 |
|SmartAGId|String|是|sag-4yr0p2xa6o3k\*\*\*\*\*\*\*|需要绑定访问控制的智能网关实例。

 |
|Action|String|否|AssociateACL|要执行的操作。

 取值：**AssociateACL**

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|C9A75915-0260-4335-851A-D866A7ED396C|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?AclId=acl-ohlexqptfhy******
&RegionId=cn-hangzhou
&SmartAGId=sag-4yr0p2xa6o3k*******
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<AssociateACL>
  <RequestId>00546174-2CE6-4587-9550-04B6A3313938</RequestId>
</AssociateACL>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"C9A75915-0260-4335-851A-D866A7ED396C"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|Forbidden|User not authorized to operate on the specified resource.|用户没有操作此资源的权限|
|403|MissingParameter|The input parameter is missing, please check your input.|输入参数缺失，请检查您的输入|
|403|InvalidId.SMARTAG|The specified smart access gateway instance id is invalid.|无效的智能接入网关ID|
|403|FeatureNotSupport|The current edition of the smart access gateway does not support this feature.|智能接入网关当前版本不支持该功能特性|
|403|FeatureNotSupportForActiveSmartAG|The current edition of the active smart access gateway does not support this feature.|主智能接入网关的当前版本不支持该功能特性|
|403|FeatureNotSupportForStandBySmartAG|The current edition of the standby smart access gateway does not support this feature.|备智能接入网关的当前版本不支持该功能特性|
|403|SmartAGAlreadyAssociateAcl|The specified smart access gateway has already been associated with the specified ACL.|您选择的智能接入网关和您选择的ACL组已经绑定|
|403|AclPerSmartagAmountLimit|No more ACL can be associated with this smart access gateway.|该智能接入网关所关联的ACL组数量已经达到限额|
|403|InternalError|An internal server error occurred.|内部服务错误|
|403|InvalidId.ACL|The specified ACL ID is invalid.|无效的ACL组ID|

[查看本产品错误码](https://error-center.aliyun.com/status/product/Smartag)

