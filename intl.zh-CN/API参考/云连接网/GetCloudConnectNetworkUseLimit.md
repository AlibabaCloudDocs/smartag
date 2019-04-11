# GetCloudConnectNetworkUseLimit {#doc_api_1109169 .reference}

调用GetCloudConnectNetworkUseLimit查询当前账号在指定区域内的云连接网个数限制。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Smartag&api=GetCloudConnectNetworkUseLimit)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|RegionId|String|是|cn-hangzhou|云连接网的所属区域。

 |
|Action|String|否|GetCloudConnectNetworkUseLimit|要执行的操作。

 取值： **GetCloudConnectNetworkUseLimit**

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|BCD04867-56C3-43DC-8FEF-923EFB8B56DA|请求ID。

 |
|TotalAmount|Integer|10|当前账号在指定的区域最多可创建的云连接网个数。

 |
|UsedAmount|Integer|6|已创建的云连接网个数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://smartag.cn-shanghai.aliyuncs.com/?Action=GetCloudConnectNetworkUseLimit
&RegionId=cn-shanghai
&CommonParameters

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<GetCloudConnectNetworkUseLimitResponse>
  <RequestId>BCD04867-56C3-43DC-8FEF-923EFB8B56DA</RequestId>
  <TotalAmount>10</TotalAmount>
  <UsedAmount>6</UsedAmount>
</GetCloudConnectNetworkUseLimitResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"BCD04867-56C3-43DC-8FEF-923EFB8B56DA",
	"TotalAmount":10,
	"UsedAmount":6
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|Forbidden|User not authorized to operate on the specified resource.|用户没有操作此资源的权限|

[查看本产品错误码](https://error-center.aliyun.com/status/product/Smartag)

