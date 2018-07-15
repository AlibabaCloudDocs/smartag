# UpdateSmartAccessGatewayVersion {#reference_y5q_3ks_j2b .reference}

升级智能接入网关的软件版本。

## 请求参数 {#section_jby_xp5_j2b .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 执行的操作，取值：

 UpdateSmartAccessGatewayVersion

 |
|SmartAGId|String|是|智能接入网关的ID。|
|VersionCode|String|是|要升级的智能接入网关的版本。|
|RegionId|String|否| 智能接入网关的所属区域。取值：

 cn-shanghai：中国大陆

 |

## 返回参数 {#section_a3q_bp5_j2b .section}

|参数|类型|描述|
|--|--|--|
|RequestId|String|请求ID。|

## 示例 {#section_s52_kp5_j2b .section}

**请求示例**

```
https://smartag.cn-shanghai.aliyuncs.com/?Action=UpdateSmartAccessGatewayVersion
&SmartAGId=sag-0ovhf732a9j0pt0aeo
&VersionCode=2.0
&CommonParameters
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <UpdateSmartAccessGatewayVersionResponse>
      <RequestId>CE6642D4-21EB-4168-9BF9-F217953F9892</RequestId>
    </UpdateSmartAccessGatewayVersionResponse>
    ```

-   JSON格式

    ```
    {
       "RequestId":"CE6642D4-21EB-4168-9BF9-F217953F9892"
    }
    ```


