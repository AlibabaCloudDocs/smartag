# DescribeACLs {#doc_api_Smartag_DescribeACLs .reference}

调用DescribeACLs查询访问控制信息。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=DescribeACLs&type=RPC&version=2018-03-13)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|RegionId|String|是|cn-hangzhou|地域ID。

 |
|AclIds|String|否|acl-xhwhyuo43l\*\*\*\*\*\*\*|访问控制集合ACL的ID。

 多个ID以逗号隔开，不填则查询region内所有ACL规则。

 |
|Action|String|否|DescribeACLs|要执行的操作。

 取值：**DescribeACLs**

 |
|Name|String|否|test|ACL名称。

 |
|PageNumber|Integer|否|1|列表的页码，默认值为1。

 |
|PageSize|Integer|否|1|分页查询时每页的行数，最大值为50，默认值为10。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Acls| | |访问控制信息。

 |
|AclId|String|acl-ohlexqptfhy\*\*\*\*\*\*\*|访问控制ID。

 |
|Name|String|test|访问控制名称。

 |
|SagCount|String|3|绑定的sag实例数。

 |
|PageNumber|Integer|1|列表的页码，默认值为1。

 |
|PageSize|Integer|2|分页查询时每页的行数。

 |
|RequestId|String|3200E8A3-563F-4FFC-8BDB-0F1263FA69E8|请求ID。

 |
|TotalCount|Integer|3|返回总数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?RegionId=cn-hangzhou
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeACLs>
      <PageNumber>1</PageNumber>
	  <TotalCount>3</TotalCount>
	  <PageSize>10</PageSize>
	  <RequestId>3200E8A3-563F-4FFC-8BDB-0F1263FA69E8</RequestId>
	  <Acls>
		    <Acl>
			      <Name>vmeixme</Name>
			      <SagCount>0</SagCount>
			      <AclId>acl-e30a66to95csjy75r9</AclId>
		    </Acl>
		    <Acl>
			      <Name>test</Name>
			      <SagCount>0</SagCount>
			      <AclId>acl-ohlexqptfhygf4xebg</AclId>
		    </Acl>
		    <Acl>
			      <Name>test</Name>
			      <SagCount>3</SagCount>
			      <AclId>acl-xhwhyuo43l0n2b832u</AclId>
		    </Acl>
	  </Acls>
    </DescribeACLs>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"PageNumber":1,
	"TotalCount":3,
	"PageSize":10,
	"RequestId":"3200E8A3-563F-4FFC-8BDB-0F1263FA69E8",
	"Acls":{
		"Acl":[
			{
				"Name":"vmeixme",
				"SagCount":0,
				"AclId":"acl-e30a66to95csjy75r9"
			},
			{
				"Name":"test",
				"SagCount":0,
				"AclId":"acl-ohlexqptfhygf4xebg"
			},
			{
				"Name":"test",
				"SagCount":3,
				"AclId":"acl-xhwhyuo43l0n2b832u"
			}
		]
	}
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|Forbidden|User not authorized to operate on the specified resource.|用户没有操作此资源的权限|
|403|MissingParameter|The input parameter is missing, please check your input.|输入参数缺失，请检查您的输入|
|403|InvalidParameter|The specified parameter is invalid.|非法参数|
|403|InternalError|An internal server error occurred.|内部服务错误|

访问[错误中心](https://error-center.aliyun.com/status/product/Smartag)查看更多错误码。

