# ListSmartAGByAccessPoint

调用ListSmartAGByAccessPoint查询指定地域内指定接入点下智能接入网关实例信息。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=ListSmartAGByAccessPoint&type=RPC&version=2018-03-13)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|ListSmartAGByAccessPoint|要执行的操作。

 取值：**ListSmartAGByAccessPoint**。 |
|AccessPointId|Integer|是|238|接入点ID。 |
|RegionId|String|是|cn-shanghai|智能接入网关实例所在的地域ID。

 一个地域内包含一个或多个接入点。您可以通过[ListAccessPoints](~~183876~~)查看地域下的接入点信息。 |
|PageSize|Integer|否|5|分页查询时每页的条目数。默认值为**10**。最大值为**50**。 |
|PageNumber|Integer|否|1|分页查询时的页码，默认值为**1**。 |
|SmartAGStatus|String|否|Active|智能接入网关实例状态。取值：

 -   **Active**：可用。
-   **Offline**：离线。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|AE203140-5D0C-4B4D-88D1-D008206B3A01|请求ID。 |
|SmartAccessGateways|Array of SmartAccessGateway| |智能接入网关实例信息。 |
|AssociatedCcnId|String|ccn-l42qf3vpvb\*\*\*\*|智能接入网关实例绑定的云连接网实例ID。 |
|HardwareVersion|String|sag-1000|智能接入网关实例绑定的设备类型。

 -   **sag-1000**。
-   **sag-100WM**。 |
|RoutingStrategy|String|static|当前智能接入网关实例线下路由同步方式。取值：

 -   **static**：静态路由。
-   **dynamic**：动态路由。 |
|SmartAGDescription|String|test|智能接入网关实例描述。 |
|SmartAGId|String|sag-p86e06z4geaji1\*\*\*\*|智能接入网关实例ID。 |
|SmartAGName|String|test|智能接入网关实例名称。 |
|SmartAGStatus|String|Active|智能接入网关实例状态：

 -   **Active**：可用。
-   **Offline**：离线。 |
|TotalCount|Integer|16|当前接入点下智能接入网关实例总个数。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=ListSmartAGByAccessPoint
&AccessPointId=238
&RegionId=cn-shanghai
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<ListSmartAGByAccessPointResponse>
  <TotalCount>16</TotalCount>
  <RequestId>ABEE83F9-610C-4EFF-9C02-32EB269BD34E</RequestId>
  <SmartAccessGateways>
        <SmartAGName>菜鸟-工业压测</SmartAGName>
        <SmartAGStatus>Offline</SmartAGStatus>
        <RoutingStrategy>static</RoutingStrategy>
        <AssociatedCcnId>ccn-l42qf3vpvb0hmq****</AssociatedCcnId>
        <SmartAGId>sag-71sh7ww783pdes****</SmartAGId>
        <HardwareVersion>sag-100wm</HardwareVersion>
  </SmartAccessGateways>
  <SmartAccessGateways>
        <SmartAGStatus>Offline</SmartAGStatus>
        <RoutingStrategy>static</RoutingStrategy>
        <AssociatedCcnId>ccn-3dmy71fs4tz69d****</AssociatedCcnId>
        <SmartAGId>sag-7b7gnu4dn6x9gz****</SmartAGId>
        <HardwareVersion>sag-1000</HardwareVersion>
  </SmartAccessGateways>
</ListSmartAGByAccessPointResponse>
```

`JSON` 格式

```
{
	"TotalCount": 16,
	"RequestId": "ABEE83F9-610C-4EFF-9C02-32EB269BD34E",
	"SmartAccessGateways": [
		{
			"SmartAGName": "菜鸟-工业压测",
			"SmartAGStatus": "Offline",
			"RoutingStrategy": "static",
			"AssociatedCcnId": "ccn-l42qf3vpvb0hmq****",
			"SmartAGId": "sag-71sh7ww783pdes****",
			"HardwareVersion": "sag-100wm"
		},
		{
			"SmartAGStatus": "Offline",
			"RoutingStrategy": "static",
			"AssociatedCcnId": "ccn-3dmy71fs4tz69d****",
			"SmartAGId": "sag-7b7gnu4dn6x9gz****",
			"HardwareVersion": "sag-1000"
		}
	]
}
```

## 错误码

访问[错误中心](https://error-center.aliyun.com/status/product/Smartag)查看更多错误码。

