# DescribeRegions {#reference_i4w_xmt_ndb .reference}

Query available regions.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Parameters|Required|Description|
|:---|:---------|:-------|:----------|
|Action|String| Yes| The action to perform.  Valid value:

 DescribeRegions

 |
|AcceptLanguage|String| No|The language of the response. Value:-   zh-CN \(Default\): Chinese
-   en-US: English

|

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|
|Regions|List|A list of regions.|

|Name |Type|Description|
|:----|:---|:----------|
|RegionId|String|The ID of the region.|
|Localname|String|The name of the region.|
|RegionEndpoint|String|The service endpoint of the region.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://smartag.cn-shanghai.aliyuncs.com/?Action=DescribeRegions
&CommonParameters
```

**Response example**

XML format

```
<? xml version="1.0" encoding="UTF-8" ? > 
<DescribeRegionsResponse> 
<RequestId>611CB80C-B6A9-43DB-9E38-0B0AC3D9B58F</RequestId>
<Regions>
	<Region>
		<RegionId>cn-qingdao</RegionId>
		<RegionEndpoint>vpc.aliyuncs.com</RegionEndpoint>
		<LocalName>China (Qingdao)</LocalName>
	</Region>
	<Region>
		<RegionId>eu-central-1</RegionId>
		<RegionEndpoint>vpc.eu-central-1.aliyuncs.com</RegionEndpoint>
		<LocalName>Germany (Frankfurt)</LocalName>
	</Region>
<Regions>
</DescribeRegionsResponse>
```

JSON format

```
{
    "RequestId": "2F026E79-30AD-47B6-9E7D-D1D4BA77F1F1", 
    "Regions": {
        "Region": [
            {
                "RegionId": "cn-qingdao", 
                "RegionEndpoint": "vpc.aliyuncs.com", 
                "LocalName": "China (Qingdao)"
            }, 
            {
                "RegionId": "eu-central-1", 
                "RegionEndpoint": "vpc.eu-central-1.aliyuncs.com", 
                "LocalName": "Germany (Frankfurt)"
            }
        ]
    }
}
```

