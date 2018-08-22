# GetCloudConnectNetworkUseLimit {#reference_cqj_4ks_j2b .reference}

Query the maximum number of CCN instances that the account can create in the area.

## Request parameters {#section_jby_xp5_j2b .section}

|Name|Type|Required|Description |
|:---|:---|:-------|:-----------|
|Action|String |Yes| The action to perform. Valid value:

 GetCloudConnectNetworkUseLimit

 |
|RegionId|String|No| The area of the CCN instance. Valid value:

 cn-shanghai: Mainland China

 |

## Response parameters {#section_gqm_lm5_j2b .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|
|TotalAmount|Integer|The maximum number of CCN instances that you can create in the area.|
|UsedAmount|Integer|The number of created CCN instances.|

## Examples {#section_s52_kp5_j2b .section}

**Request example**

```
https://smartag.cn-shanghai.aliyuncs.com/?Action=GetCloudConnectNetworkUseLimit
&RegionId=cn-shanghai
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
    <GetCloudConnectNetworkUseLimitResponse>
      <RequestId>BCD04867-56C3-43DC-8FEF-923EFB8B56DA</RequestId>
      <TotalAmount>10</TotalAmount>
      <UsedAmount>6</UsedAmount>
    </GetCloudConnectNetworkUseLimitResponse>
    ```

-   JSON format

    ```
    {
    "RequestId": "BCD04867-56C3-43DC-8FEF-923EFB8B56DA",
    "TotalAmount": 10,
    "UsedAmount": 6
    }
    ```


