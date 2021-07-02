# CreateACL

调用CreateACL接口创建访问控制实例。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=CreateACL&type=RPC&version=2018-03-13)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|CreateACL|要执行的操作。取值：**CreateACL**。 |
|RegionId|String|是|cn-shanghai|访问控制实例所属的地域ID。 |
|Name|String|是|test|访问控制实例名称。

 名称长度为2~128个字符，必须以大小写字母或中文开头，可包含数字、半角句号（.）、下划线（\_）和短划线（-）。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|EE837E9F-BD50-4C2B-9E47-260F9D848480|请求ID。 |
|AclId|String|acl-o6yol7zowii5n2\*\*\*\*|访问控制实例ID。 |
|ResourceGroupId|String|rg-acfm2iu4fnc\*\*\*\*|访问控制实例所属资源组ID。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=CreateACL
&RegionId=cn-shanghai
&Name=test
&公共请求参数
```

正常返回示例

`XML`格式

```
HTTP/1.1 200 OK
Content-Type:application/xml

<CreateACLResponse>
    <RequestId>EE837E9F-BD50-4C2B-9E47-260F9D848480</RequestId>
    <AclId>acl-o6yol7zowii5n2****</AclId>
    <ResourceGroupId>rg-acfm2iu4fnc****</ResourceGroupId>
</CreateACLResponse>
```

`JSON`格式

```
HTTP/1.1 200 OK
Content-Type:application/json

{
  "RequestId" : "EE837E9F-BD50-4C2B-9E47-260F9D848480",
  "AclId" : "acl-o6yol7zowii5n2****",
  "ResourceGroupId" : "rg-acfm2iu4fnc****"
}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|Forbidden|User not authorized to operate on the specified resource.|用户没有操作此资源的权限。|
|403|MissingParameter|The input parameter is missing, please check your input.|输入参数缺失，请检查您的输入。|
|403|InvalidName|Name not valid.|名称不合法。|
|403|AclAmountLimit|No more ACL can be created. You can open a ticket to increase the quota of ACLs.|您创建的ACL实例已经达到限额，您可以通过工单申请提升限额。|
|403|InternalError|An internal server error occurred.|内部服务错误。|

访问[错误中心](https://error-center.alibabacloud.com/status/product/Smartag)查看更多错误码。

