# DescribeSmartAccessGatewayVersions {#doc_api_1109137 .reference}

调用DescribeSmartAccessGatewayVersions查询智能接入网关的软件版本。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Smartag&api=DescribeSmartAccessGatewayVersions)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|RegionId|String|是|cn-hangzhou|智能接入网关的所属区域。取值： cn-shanghai：中国大陆

 |
|Action|String|否|DescribeSmartAccessGatewayVersions|执行的操作，取值： DescribeSmartAccessGatewayVersions

 |
|SmartAGId|String|否|sag-d3m51apgw4po5\*\*\*\*\*|智能接入网关实例ID。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|765AB188-69BF-47C6-BEDD-B9FC72BFBB0|请求ID。

 |
|SmartAGVersions| | |智能接入网关的版本。

 |
|└CreateTime|Long|1522744623000|版本发布时间。

 |
|└VersionCode|String|1.0|版本代码。

 |
|└VersionName|String|testpackage1|版本名称。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://smartag.cn-shanghai.aliyuncs.com/?Action=DescribeSmartAccessGatewayVersions
&RegionId=cn-shanghai
&CommonParameters

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeSmartAccessGatewayVersionsResponse>
  <SmartAGVersions>
    <SmartAGVersion>
      <CreateTime>1522744623000</CreateTime>
      <VersionCode>1.0</VersionCode>
      <VersionName>testpackage1</VersionName>
    </SmartAGVersion>
  </SmartAGVersions>
  <RequestId>765AB188-69BF-47C6-BEDD-B9FC72BFBB00</RequestId>
</DescribeSmartAccessGatewayVersionsResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"SmartAGVersions":{
		"SmartAGVersion":[
			{
				"VersionCode":"1.0",
				"CreateTime":1522744623000,
				"VersionName":"testpackage1"
			}
		]
	},
	"RequestId":"765AB188-69BF-47C6-BEDD-B9FC72BFBB00"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|Forbidden|User not authorized to operate on the specified resource.|用户没有操作此资源的权限|

[查看本产品错误码](https://error-center.aliyun.com/status/product/Smartag)

