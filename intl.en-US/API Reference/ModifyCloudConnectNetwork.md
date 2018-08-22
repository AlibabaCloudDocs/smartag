# ModifyCloudConnectNetwork {#concept_fvh_mks_j2b .concept}

Modify the name and description of a CCN instance.

## Request parameters {#section_jby_xp5_j2b .section}

|Name|Type|Required|Description |
|:---|:---|:-------|:-----------|
|Action|String |Yes| The action to perform. Valid value:

 ModifyCloudConnectNetwork

 |
|RegionId|String |Yes| The area of the CCN instance. Valid value:

 cn-shanghai: Mainland China

 |
|CcnId|String |Yes|The ID of the CCN instance.|
|Name|String|No| The name of the CCN instance.

 The name can contain 2 to 128 characters including a-z, A-Z, 0-9, periods, underlines, and hyphens. The name must start with an English letter, but cannot start with `http://` or `https://`.

 |
|Description|String|No| The description of the CCN instance.

 The description can contain 2 to 256 characters. The description must start with English letters, but cannot start with `http://` or `https://`.

 |

## Response parameters {#section_gqm_lm5_j2b .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|

## Examples {#section_s52_kp5_j2b .section}

**Request example**

```
https://smartag.cn-shanghai.aliyuncs.com/?Action=ModifyCloudConnectNetwork
&RegionId=cn-shanghai
&CcnId=ccn-l9340rlu5enstmzj5
&Description=ConnectChina
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
    <ModifyCloudConnectNetworkResponse>
      <RequestId>0BAAF2B9-88B8-4574-BDBE-102A90EE3FEE</RequestId>
    </ModifyCloudConnectNetworkResponse>
    ```

-   JSON format

    ```
    {
       "RequestId":"0BAAF2B9-88B8-4574-BDBE-102A90EE3FEE"
    }
    ```


