# BindSmartAccessGateway {#reference_n2f_2ks_j2b .reference}

将智能接入网关绑定到指定的云连接网中。

## 请求参数 {#section_amr_hj5_j2b .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 执行的操作，取值：

 BindSmartAccessGateway

 |
|SmartAGId|String|是|智能接入网关ID。|
|CcnId|String|是|要绑定的云连接网ID。|
|RegionId|String|否| 智能接入网关的所属区域。取值：

 cn-shanghai：中国大陆

 |

## 返回参数 {#section_nbh_rj5_j2b .section}

|参数|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_y5x_dk5_j2b .section}

**请求示例**

```
https://smartag.cn-shanghai.aliyuncs.com/?Action=BindSmartAccessGateway
&SmartAGId=ccn-bxuau4ezctts2kfxyr
&CcnId=sag-0ovhf732a9j0pt0aeo
&CommonParameters
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <BindSmartAccessGatewayResponse>
      <RequestId>6877D55B-08F7-4DA3-916B-32A6FD402E06</RequestId>
    </BindSmartAccessGatewayResponse>
    ```

-   JSON格式

    ```
    {
       "RequestId":"6877D55B-08F7-4DA3-916B-32A6FD402E06"
    }
    ```


