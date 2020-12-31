# GetAclAttribute

调用GetAclAttribute查询指定访问控制实例中应用识别DPI功能配置异常的信息。

## 前提条件

-   您已经创建了基于应用的访问控制实例。具体操作，请参见[AddACLRule](~~114012~~)。
-   您已经将创建的基于应用的访问控制实例关联到了目标智能接入网关实例中。具体操作，请参见[AssociateACL](~~114009~~)。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=GetAclAttribute&type=RPC&version=2018-03-13)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|GetAclAttribute|要执行的操作。

 取值：**GetAclAttribute**。 |
|AclId|String|是|acl-xhwhyuo43l0n\*\*\*\*\*|访问控制实例ID。 |
|RegionId|String|是|cn-shanghai|访问控制实例所属的地域ID。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|AclId|String|acl-xhwhyuo43l0n\*\*\*\*\*|访问控制实例ID。 |
|AclName|String|dpi\_test|访问控制实例名称。 |
|ErrorConfigSmartAGCount|Integer|0|访问控制实例DPI功能配置异常关联的智能接入网关设备数量。

 您可以通过[ListDpiConfigError](~~197566~~)查看具体的异常信息及相关的智能接入网关设备信息。 |
|RequestId|String|5D2013F0-85AB-4332-9094-8023A598C2C1|请求ID。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=GetAclAttribute
&AclId=acl-xhwhyuo43l0n*****
&RegionId=cn-shanghai
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<GetAclAttributeResponse>
  <RequestId>5D2013F0-85AB-4332-9094-8023A598C2C1</RequestId>
  <AclId>acl-j8s80200h3cli****</AclId>
  <ErrorConfigSmartAGCount>0</ErrorConfigSmartAGCount>
  <AclName>dpi_test</AclName>
</GetAclAttributeResponse>
```

`JSON` 格式

```
{
	"RequestId": "5D2013F0-85AB-4332-9094-8023A598C2C1",
	"AclId": "acl-j8s80200h3cli****",
	"ErrorConfigSmartAGCount": 0,
	"AclName": "dpi_test"
}
```

## 错误码

访问[错误中心](https://error-center.aliyun.com/status/product/Smartag)查看更多错误码。

