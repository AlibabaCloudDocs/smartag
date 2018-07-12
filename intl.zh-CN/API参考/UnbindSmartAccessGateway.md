# UnbindSmartAccessGateway {#reference_z5g_fks_j2b .reference}

将智能接入网关从指定的云连接网中解绑。

## 请求参数 {#section_okv_sk5_j2b .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 执行的操作，取值：

 UnbindSmartAccessGateway

 |
|SmartAGId|String|是|智能接入网关的ID。|
|CcnId|String|是|云连接网ID。|
|RegionId|String|否| 智能接入网关的所属区域。取值：

 cn-shanghai：中国大陆

 |

## 返回参数 {#section_cky_dl5_j2b .section}

|参数|类型|描述|
|--|--|--|
|RequestId|String|请求ID。|

## 示例 {#section_pmd_3l5_j2b .section}

**请求示例**

```
https://smartag.cn-shanghai.aliyuncs.com/?Action=UnbindSmartAccessGateway
&SmartAGId=sag-0ovhf732a9j0pt0aeo
&CcnId=ccn-kygbldwikzdg2g9b8e
&CommonParameters
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <UnbindSmartAccessGatewayResponse>
      <RequestId>CE6642D4-21EB-4168-9BF9-F217953F9892</RequestId>
    </UnbindSmartAccessGatewayResponse>
    ```

-   JSON格式

    ```
    {
       "RequestId":"CE6642D4-21EB-4168-9BF9-F217953F9892"
    }
    ```


