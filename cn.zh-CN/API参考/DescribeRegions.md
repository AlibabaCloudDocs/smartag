# DescribeRegions {#reference_i4w_xmt_ndb .reference}

查询可用地域。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DescribeRegions

 |
|AcceptLanguage|String|否|返回值语言。取值：-   zh-CN（默认值）：中文
-   en-US：英文

|

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|Regions|List|可用地域的集合。|

|名称|类型|描述|
|:-|:-|:-|
|RegionId|String|地域ID。|
|LocalName|String|地域名称。|
|RegionEndpoint|String|地域服务的Endpoint。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://smartag.cn-shanghai.aliyuncs.com/?Action=DescribeRegions
&公共请求参数
```

**返回示例**

XML格式

```
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

JSON格式

```
{
    "RequestId": "2F026E79-30AD-47B6-9E7D-D1D4BA77F1F1", 
    "Regions": {
        "Region": [
            {
                "RegionId": "cn-qingdao", 
                "RegionEndpoint": "vpc.aliyuncs.com", 
                "LocalName": "华北 1"
            }, 
            {
                "RegionId": "eu-central-1", 
                "RegionEndpoint": "vpc.eu-central-1.aliyuncs.com", 
                "LocalName": "欧洲中部 1 (法兰克福)"
            }
        ]
    }
}
```

