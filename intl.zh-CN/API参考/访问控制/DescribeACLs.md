# DescribeACLs

调用DescribeACLs查询指定地域下访问控制实例信息。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=DescribeACLs&type=RPC&version=2018-03-13)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|DescribeACLs|要执行的操作。取值：**DescribeACLs**。 |
|RegionId|String|是|cn-shanghai|访问控制实例所属的地域ID。 |
|AclIds|String|否|acl-xhwhyuo43l\*\*\*\*\*\*\*|访问控制实例ID。

 -   若同时查询多个访问控制实例，多个实例ID请以半角逗号（,）隔开。
-   若不填写该项，则表示查询当前地域下所有访问控制实例的信息。 |
|Name|String|否|test|访问控制实例名称。

 名称长度为2~100个字符，以大小写字母或中文开头，可包含数字、下划线（\_）、半角句号（.）和短划线（-）。 |
|PageSize|Integer|否|10|分页查询时每页的条目数。最大值为**50**，默认值为**10**。 |
|PageNumber|Integer|否|1|查询页码，默认值为**1**。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|TotalCount|Integer|455|总条目数。 |
|PageSize|Integer|3|分页查询时每页的条目数。 |
|RequestId|String|660F303F-C88E-4026-BC6A-FC24B78FD7EA|请求ID。 |
|PageNumber|Integer|1|查询页码。 |
|Acls|Array of Acl| |访问控制实例信息列表。 |
|Acl| | | |
|SagCount|String|0|访问控制实例绑定的智能接入网关实例数量。 |
|AclId|String|acl-ohlexqptfhy\*\*\*\*\*\*\*|访问控制实例ID。 |
|Name|String|test|访问控制实例名称。 |
|ResourceGroupId|String|rg-acfm2iu4fnc\*\*\*\*|访问控制实例所属资源组ID。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=DescribeACLs
&RegionId=cn-shanghai
&AclIds=acl-xhwhyuo43l*******
&Name=test
&PageSize=10
&PageNumber=1
&公共请求参数
```

正常返回示例

`XML`格式

```
HTTP/1.1 200 OK
Content-Type:application/xml

<DescribeACLsResponse>
    <TotalCount>455</TotalCount>
    <PageSize>3</PageSize>
    <RequestId>660F303F-C88E-4026-BC6A-FC24B78FD7EA</RequestId>
    <PageNumber>1</PageNumber>
    <Acls>
        <Acl>
            <SagCount>0</SagCount>
            <ResourceGroupId>rg-acfm2iu4fnc****</ResourceGroupId>
            <AclId>acl-rsds2pk8gxcqce****</AclId>
            <Name>http</Name>
        </Acl>
        <Acl>
            <SagCount>0</SagCount>
            <ResourceGroupId>rg-acfm2iu4fnc****</ResourceGroupId>
            <AclId>acl-o6yol7zowii5n2****</AclId>
            <Name>zxtest</Name>
        </Acl>
        <Acl>
            <SagCount>0</SagCount>
            <ResourceGroupId>rg-acfm2iu4fnc****</ResourceGroupId>
            <AclId>acl-cl8gkzvldyxayo****</AclId>
            <Name>test-name-bvt-te</Name>
        </Acl>
    </Acls>
</DescribeACLsResponse>
```

`JSON`格式

```
HTTP/1.1 200 OK
Content-Type:application/json

{
  "TotalCount" : 455,
  "PageSize" : 3,
  "RequestId" : "660F303F-C88E-4026-BC6A-FC24B78FD7EA",
  "PageNumber" : 1,
  "Acls" : {
    "Acl" : [ {
      "SagCount" : 0,
      "ResourceGroupId" : "rg-acfm2iu4fnc****",
      "AclId" : "acl-rsds2pk8gxcqce****",
      "Name" : "http"
    }, {
      "SagCount" : 0,
      "ResourceGroupId" : "rg-acfm2iu4fnc****",
      "AclId" : "acl-o6yol7zowii5n2****",
      "Name" : "zxtest"
    }, {
      "SagCount" : 0,
      "ResourceGroupId" : "rg-acfm2iu4fnc****",
      "AclId" : "acl-cl8gkzvldyxayo****",
      "Name" : "test-name-bvt-te"
    } ]
  }
}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|Forbidden|User not authorized to operate on the specified resource.|用户没有操作此资源的权限。|
|403|MissingParameter|The input parameter is missing, please check your input.|输入参数缺失，请检查您的输入。|
|403|InvalidParameter|The specified parameter is invalid.|非法参数。|
|403|InternalError|An internal server error occurred.|内部服务错误。|

访问[错误中心](https://error-center.alibabacloud.com/status/product/Smartag)查看更多错误码。

