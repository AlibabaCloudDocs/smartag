# GetSmartAGDpiAttribute

调用GetSmartAGDpiAttribute查询智能接入网关实例应用识别DPI（Deep Packet Inspection）功能配置信息。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=GetSmartAGDpiAttribute&type=RPC&version=2018-03-13)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|GetSmartAGDpiAttribute|要执行的操作。

 取值：**GetSmartAGDpiAttribute**。 |
|RegionId|String|是|cn-shanghai|智能接入网关实例所属地域ID。 |
|SmartAGId|String|是|sag-tq3sazs17smldn\*\*\*\*|智能接入网关实例ID。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|DpiMonitorStatus|String|Inactive|智能接入网关实例DPI监控功能开启状态。

 -   **Active**：已开启。
-   **Inactive**：未开启。 |
|DpiStatus|String|On|智能接入网关实例DPI功能开启状态。

 -   **On**：已开启。
-   **Off**：未开启。 |
|LogstoreName|String|test1|智能接入网关实例DPI功能关联的Logstore实例名称。 |
|ProjectName|String|test2|智能接入网关实例DPI功能关联的Project实例名称。 |
|RequestId|String|B2997DC4-F1A2-418B-81FC-C8892CD31CFF|请求ID。 |
|SlsRegion|String|cn-shanghai|智能接入网关实例DPI功能关联的日志服务的地域。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=GetSmartAGDpiAttribute
&RegionId=cn-shanghai
&SmartAGId=sag-tq3sazs17smldn****
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<GetSmartAGDpiAttributeResponse>
  <RequestId>B2997DC4-F1A2-418B-81FC-C8892CD31CFF</RequestId>
  <SlsRegion>cn-shanghai</SlsRegion>
  <DpiMonitorStatus>Inactive</DpiMonitorStatus>
  <DpiStatus>On</DpiStatus>
</GetSmartAGDpiAttributeResponse>
```

`JSON` 格式

```
{
	"RequestId": "B2997DC4-F1A2-418B-81FC-C8892CD31CFF",
	"SlsRegion": "cn-shanghai",
	"DpiMonitorStatus": "Inactive",
	"DpiStatus": "On"
}
```

## 错误码

访问[错误中心](https://error-center.aliyun.com/status/product/Smartag)查看更多错误码。

