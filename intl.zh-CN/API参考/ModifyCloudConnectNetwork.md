# ModifyCloudConnectNetwork {#concept_fvh_mks_j2b .concept}

修改云连接网的名称和描述。

## 请求参数 {#section_jby_xp5_j2b .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 执行的操作，取值：

 ModifyCloudConnectNetwork

 |
|RegionId|String|是| 云连接网的所属区域。取值：

 cn-shanghai：中国大陆

 |
|CcnId|String|是|云连接网ID。|
|Name|String|否| 云连接网的名称。

 长度为2-128个字符，必须以字母或中文开头，可包含数字，点号（.），下划线（\_）和短横线（-），但不能以`http://` 或 `https://`开头。

 |
|Description|String|否| 云连接网的描述。

 长度为2-256个字符，必须以字母或中文开头，但不能以`http://` 或 `https://`开头。

 |

## 返回参数 {#section_gqm_lm5_j2b .section}

|参数|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_s52_kp5_j2b .section}

**请求示例**

```
https://smartag.cn-shanghai.aliyuncs.com/?Action=ModifyCloudConnectNetwork
&RegionId=cn-shanghai
&CcnId=ccn-l9340rlu5enstmzj5
&Description=ConnectChina
&CommonParameters
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <ModifyCloudConnectNetworkResponse>
      <RequestId>0BAAF2B9-88B8-4574-BDBE-102A90EE3FEE</RequestId>
    </ModifyCloudConnectNetworkResponse>
    ```

-   JSON格式

    ```
    {
       "RequestId":"0BAAF2B9-88B8-4574-BDBE-102A90EE3FEE"
    }
    ```


