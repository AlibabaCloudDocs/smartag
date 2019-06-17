# DeleteCloudConnectNetwork {#reference_k22_nks_j2b .reference}

You can use the DeleteCloudConnectNetwork API to delete a CCN instance.

**Note:** Make sure the CCN instance to delete is not associated with any Smart Access Gateway instance or CEN instance.

## Request parameters {#section_jby_xp5_j2b .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value:

 DeleteCloudConnectNetwork

 |
|CcnId|String|Yes|The ID of the CCN instance.|
|RegionId|String|No| The area of the CCN instance. Valid value:

 cn-shanghai: Mainland China

 |

## Response parameters {#section_gqm_lm5_j2b .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|

## Examples {#section_s52_kp5_j2b .section}

**Request example**

```
https://smartag.cn-shanghai.aliyuncs.com/?Action=DeleteCloudConnectNetwork
&CcnId=ccn-bxuau4ezctts2kfxyr
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
    <DeleteCloudConnectNetworkResponse>
      <RequestId>0BAAF2B9-88B8-4574-BDBE-102A90EE3FEE</RequestId>
    </DeleteCloudConnectNetworkResponse>
    ```

-   JSON format

    ```
    {
       "RequestId":"0BAAF2B9-88B8-4574-BDBE-102A90EE3FEE"
    }
    ```


