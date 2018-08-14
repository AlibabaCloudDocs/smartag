# GetSmartAccessGatewayUseLimit {#reference_iqr_hks_j2b .reference}

Query the maximum number of Smart Access Gateway instances that can be purchased.

## Request parameters {#section_hxv_xn5_j2b .section}

|Name|Type|Required|Description |
|:---|:---|:-------|:-----------|
|Action|String |Yes| The action to perform. Valid value:

 GetSmartAccessGatewayUseLimit

 |
|RegionId|String |Yes| The area of the Smart Access Gateway instances. Valid value:

 cn-shanghai: Mainland China

 |

## Response parameters {#section_a3q_bp5_j2b .section}

|Name|Type|Description|
|----|----|-----------|
|RequestId|String|The ID of the request.|
|TotalAmount|Integer|The number of Smart Access Gateway instances that can be purchased.|
|UsedAmount|Integer|The number of Smart Access Gateway instances that have been purchased.|

## Examples {#section_s52_kp5_j2b .section}

**Request example**

```
https://smartag.cn-shanghai.aliyuncs.com/?Action=GetSmartAccessGatewayUseLimit
&SmartAGId=sag-0ovhf732a9j0pt0aeo
&Name=DocTest
&CommonParameters
```

**Response example**

-   XML format

    ```
    https://smartag.cn-shanghai.aliyuncs.com/?Action=GetSmartAccessGatewayUseLimit
    &SmartAGId=sag-0ovhf732a9j0pt0aeo
    &Name=DocTest
    &CommonParameters
    ```

-   JSON format

    ```
    {
      "RequestId": "2265DB11-F5CC-496E-ADE7-D043AC37926A",
      "TotalAmount": 500,
      "UsedAmount": 47
    }
    ```


