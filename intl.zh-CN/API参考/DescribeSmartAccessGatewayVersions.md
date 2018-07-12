# DescribeSmartAccessGatewayVersions {#reference_v35_gks_j2b .reference}

查询智能接入网关的软件版本。

## 请求参数 {#section_ikz_dm5_j2b .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 执行的操作，取值：

 DescribeSmartAccessGatewayVersions

 |
|RegionId|String|是| 智能接入网关的所属区域。取值：

 cn-shanghai：中国大陆

 |

## 返回参数 {#section_gqm_lm5_j2b .section}

|参数|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|SmartAGVersions|List|智能接入网关的版本。|

|参数|类型|描述|
|:-|:-|:-|
|VersionCode|String|版本代码。|
|VersionName|String|版本名称。|
|CreateTime|Long|版本发布时间。|

## 示例 {#section_pzy_wm5_j2b .section}

**请求示例**

```
https://smartag.cn-shanghai.aliyuncs.com/?Action=DescribeSmartAccessGatewayVersions
&RegionId=cn-shanghai
&CommonParameters
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
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

-   JSON格式

    ```
    {
    "SmartAGVersions": {
    "SmartAGVersion": [
    {
    "CreateTime": 1522744623000,
    "VersionCode": "1.0",
    "VersionName": "testpackage1"
    }
    ]
    },
    "RequestId": "765AB188-69BF-47C6-BEDD-B9FC72BFBB00"
    }
    ```


