# GetSmartAccessGatewayUseLimit {#reference_iqr_hks_j2b .reference}

查询可购买的智能接入网关数量。

## 请求参数 {#section_hxv_xn5_j2b .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 执行的操作，取值：

 GetSmartAccessGatewayUseLimit

 |
|RegionId|String|是| 智能接入网关的所属区域。取值：

 cn-shanghai：中国大陆

 |

## 返回参数 {#section_a3q_bp5_j2b .section}

|参数|类型|描述|
|--|--|--|
|RequestId|String|请求ID。|
|TotalAmount|Integer|可购买的智能接入网关总数。|
|UsedAmount|Integer|已购买的智能接入网关数量。|

## 示例 {#section_s52_kp5_j2b .section}

**请求示例**

```
https://smartag.cn-shanghai.aliyuncs.com/?Action=GetSmartAccessGatewayUseLimit
&SmartAGId=sag-0ovhf732a9j0pt0aeo
&Name=DocTest
&CommonParameters
```

**返回示例**

-   XML格式

    ```
    https://smartag.cn-shanghai.aliyuncs.com/?Action=GetSmartAccessGatewayUseLimit
    &SmartAGId=sag-0ovhf732a9j0pt0aeo
    &Name=DocTest
    &CommonParameters
    ```

-   JSON格式

    ```
    {
      "RequestId": "2265DB11-F5CC-496E-ADE7-D043AC37926A",
      "TotalAmount": 500,
      "UsedAmount": 47
    }
    ```


