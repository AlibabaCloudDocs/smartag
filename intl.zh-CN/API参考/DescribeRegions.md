# DescribeRegions {#reference_h3b_qks_j2b .reference}

查询可用的区域。

## 请求参数 {#section_jby_xp5_j2b .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 执行的操作，取值：

 DescribeRegions

 |

## 返回参数 {#section_gqm_lm5_j2b .section}

|参数|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|Regions|List|区域列表。|

|名称|类型|描述|
|:-|:-|:-|
|RegionId|String|包含的地域ID。|
|LocalName|String| 区域名称，区域名称列表如下：

 上海：中国大陆

 |

## 示例 {#section_s52_kp5_j2b .section}

**请求示例**

```
https://smartag.cn-shanghai.aliyuncs.com/?Action=DescribeRegions
&CommonParameters
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <ModifySmartAccessGatewayResponse>
      <RequestId>0BAAF2B9-88B8-4574-BDBE-102A90EE3FEE</RequestId>
      <Regions>
      <Region>
          <RegionId>cn-hangzhou-test-306</RegionId>
          <LocalName>上海</LocalName>
      </Region>
    </Regions>
    </ModifySmartAccessGatewayResponse>
    ```

-   JSON格式

    ```
    {
    "RequestId"="0BAAF2B9-88B8-4574-BDBE-102A90EE3FEE"
    "Regions": {
      "Region": [
        {
          "RegionId": "cn-hangzhou",
          "LocalName": "上海"
        }
      ]
    }
    }
    ```


