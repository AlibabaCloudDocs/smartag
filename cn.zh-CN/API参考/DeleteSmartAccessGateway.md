# DeleteSmartAccessGateway

调用DeleteSmartAccessGateway删除智能接入网关实例。

## 前提条件

-   您要删除的智能接入网关实例为硬件版实例或VCPE实例。
-   您要删除的智能接入网关实例处于欠费锁定状态。
-   您要删除的智能接入网关实例未绑定任何云连接网（CCN）或边界路由器（VBR）实例。如有已绑定网络实例，您可以先进行解绑，详情请参见[解绑网络实例](~~164903~~)。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=DeleteSmartAccessGateway&type=RPC&version=2018-03-13)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DeleteSmartAccessGateway|系统规定参数。取值：**DeleteSmartAccessGateway**。 |
|InstanceId|String|是|sag-far8v6owtdxlua\*\*\*\*|要删除的智能接入网关实例ID。 |
|RegionId|String|否|cn-hangzhou|智能接入网关实例所属的地域ID。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|E26DBAAE-A796-4A48-98B4-B45AFCD1F299|请求ID。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=DeleteSmartAccessGateway
&InstanceId=sag-far8v6owtdxlua****
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<DeleteSmartAccessGatewayResponse>
  <RequestId>D133AFFC-6E37-414D-8ECD-246DEBE4388D</RequestId>
</DeleteSmartAccessGatewayResponse>
```

`JSON` 格式

```
{
	"RequestId": "D133AFFC-6E37-414D-8ECD-246DEBE4388D"
}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|MissingParameter|The input parameter is missing, please check your input.|输入参数缺失，请检查您的输入|

访问[错误中心](https://error-center.aliyun.com/status/product/Smartag)查看更多错误码。

