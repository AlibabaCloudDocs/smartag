# CreateACL {#doc_api_Smartag_CreateACL .reference}

调用CreateACL创建访问控制。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=CreateACL&type=RPC&version=2018-03-13)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Name|String|是|test|访问控制名称。

 长度为2-128个字符，必须以字母或中文开头，可包含数字，点号（.），下划线（\_）和短横线（-），但不能以`http://`或`https://`开头

 |
|RegionId|String|是|cn-hangzhou|地域ID。

 |
|Action|String|否|CreateACL|要执行的操作。

 取值：**CreateACL**

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|AclId|String|acl-xhwhyuo43l\*\*\*\*\*\*\*\*|访问控制集合ID。

 |
|RequestId|String|EE837E9F-BD50-4C2B-9E47-260F9D848480|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Name=test
&RegionId=cn-hangzhou
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<CreateACL>
	  <AclId>acl-ohlexqptfhygf4xebg</AclId>
	  <RequestId>EE837E9F-BD50-4C2B-9E47-260F9D848480</RequestId>
    </CreateACL>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"AclId":"acl-ohlexqptfhyg******",
	"RequestId":"EE837E9F-BD50-4C2B-9E47-260F9D848480"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|Forbidden|User not authorized to operate on the specified resource.|用户没有操作此资源的权限|
|403|MissingParameter|The input parameter is missing, please check your input.|输入参数缺失，请检查您的输入|
|403|InvalidName|Name not valid.|名称不合法|
|403|AclAmountLimit|No more ACL can be created. You can open a ticket to increase the quota of ACLs.|您创建的ACL组已经达到限额，您可以通过工单申请提升限额|
|403|InternalError|An internal server error occurred.|内部服务错误|

访问[错误中心](https://error-center.aliyun.com/status/product/Smartag)查看更多错误码。

