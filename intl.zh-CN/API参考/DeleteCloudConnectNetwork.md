# DeleteCloudConnectNetwork {#reference_k22_nks_j2b .reference}

删除云连接网。

**说明：** 确保要删除的云连接网没有关联的智能接入网关和云企业网。

## 请求参数 {#section_jby_xp5_j2b .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 执行的操作，取值：

 DeleteCloudConnectNetwork

 |
|CcnId|String|是|云连接网ID。|
|RegionId|String|否| 云连接网的所属区域。取值：

 cn-shanghai：中国大陆

 |

## 返回参数 {#section_gqm_lm5_j2b .section}

|参数|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_s52_kp5_j2b .section}

**请求示例**

```
https://smartag.cn-shanghai.aliyuncs.com/?Action=DeleteCloudConnectNetwork
&CcnId=ccn-bxuau4ezctts2kfxyr
&CommonParameters
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <DeleteCloudConnectNetworkResponse>
      <RequestId>0BAAF2B9-88B8-4574-BDBE-102A90EE3FEE</RequestId>
    </DeleteCloudConnectNetworkResponse>
    ```

-   JSON格式

    ```
    {
       "RequestId":"0BAAF2B9-88B8-4574-BDBE-102A90EE3FEE"
    }
    ```


