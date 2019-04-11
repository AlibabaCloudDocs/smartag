# DescribeRegions {#doc_api_1109150 .reference}

调用DescribeRegions查询可用地域。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Smartag&api=DescribeRegions)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|AcceptLanguage|String|否|zh-CN|返回值语言。取值：

 -   zh-CN（默认值）：中文
-   en-US：英文

 |
|Action|String|否|DescribeRegions|要执行的操作。

 取值： **DescribeRegions**

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Regions| | |可用地域的集合。

 |
|└LocalName|String|华北 1|地域名称。

 |
|└RegionEndpoint|String|vpc.aliyuncs.com|地域服务的Endpoint。

 |
|└RegionId|String|cn-qingdao|地域ID。

 |
|RequestId|String|2F026E79-30AD-47B6-9E7D-D1D4BA77F1F1|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://smartag.cn-shanghai.aliyuncs.com/?Action=DescribeRegions
&公共请求参数

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<?xml version="1.0" encoding="UTF-8" ?> 
<DescribeRegionsResponse> 
<RequestId>611CB80C-B6A9-43DB-9E38-0B0AC3D9B58F</RequestId>
<Regions>
	<Region>
		<RegionId>cn-qingdao</RegionId>
		<RegionEndpoint>vpc.aliyuncs.com</RegionEndpoint>
		<LocalName>华北 1</LocalName>
	</Region>
	<Region>
		<RegionId>eu-central-1</RegionId>
		<RegionEndpoint>vpc.eu-central-1.aliyuncs.com</RegionEndpoint>
		<LocalName>欧洲中部 1 (法兰克福)</LocalName>
	</Region>
<Regions>
</DescribeRegionsResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"2F026E79-30AD-47B6-9E7D-D1D4BA77F1F1",
	"Regions":{
		"Region":[
			{
				"RegionId":"cn-qingdao",
				"RegionEndpoint":"vpc.aliyuncs.com",
				"LocalName":"华北 1"
			},
			{
				"RegionId":"eu-central-1",
				"RegionEndpoint":"vpc.eu-central-1.aliyuncs.com",
				"LocalName":"欧洲中部 1 (法兰克福)"
			}
		]
	}
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|Forbidden|User not authorized to operate on the specified resource.|用户没有操作此资源的权限|
|501|InnerServiceFailed|Call inner service failed.|调用内部服务失败|

[查看本产品错误码](https://error-center.aliyun.com/status/product/Smartag)

