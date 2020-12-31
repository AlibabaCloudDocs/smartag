# DeleteEnterpriseCode

调用DeleteEnterpriseCode删除指定企业码。

## 背景信息

在您删除企业码前，请先了解以下信息：

-   不支持删除默认企业码。

    如果您要删除的企业码为默认企业码，您可以先修改默认企业码为普通企业码，然后对其进行删除。具体操作，请参见[UpdateEnterpriseCode](~~197700~~)。

-   不支持删除已绑定智能接入网关APP实例的企业码。

    如果您要删除的企业码下已经有绑定的智能接入网关APP实例，您可以先更换智能接入网关APP实例的企业码为其他企业码，然后再删除当前企业码。具体操作，请参见[UpdateSmartAGEnterpriseCode](~~197701~~)。


## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=DeleteEnterpriseCode&type=RPC&version=2018-03-13)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DeleteEnterpriseCode|要执行的操作。

 取值：**DeleteEnterpriseCode**。 |
|EnterpriseCode|String|是|12\*\*\*|企业码。 |
|RegionId|String|是|cn-shanghai|地域ID。

 您可以调用[DescribeRegions](~~69813~~)查询智能接入网关支持的地域及对应的地域ID。 |
|ClientToken|String|否|02fb3da4\*\*\*\*|客户端Token，用于保证请求的幂等性。

 由客户端生成该参数值，要保证在不同请求间唯一，最大值不超过64个ASCII字符。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|9DD3DFB2-A9BF-4BEE-9542-661411A9851E|请求ID。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=DeleteEnterpriseCode
&EnterpriseCode=12***
&RegionId=cn-shanghai
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<DeleteEnterpriseCodeResponse>
  <RequestId>9DD3DFB2-A9BF-4BEE-9542-661411A9851E</RequestId>
</DeleteEnterpriseCodeResponse>
```

`JSON` 格式

```
{
	"RequestId": "9DD3DFB2-A9BF-4BEE-9542-661411A9851E"
}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|EnterpriseCode.BeingUsed|The specified enterprise code is being used.|企业码正在被使用。|
|400|EnterpriseCode.DeleteLimit|The specified default enterprise code cannot be deleted.|默认企业码不能删除。|
|400|EnterpriseCode.NotExist|The specified enterprise code does not exist.|企业码不存在。|

访问[错误中心](https://error-center.aliyun.com/status/product/Smartag)查看更多错误码。

