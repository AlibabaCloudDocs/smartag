# CreateCloudConnectNetwork {#reference_rzp_jks_j2b .reference}

Create a CCN instance. CCN is a device matrix composed of Alibaba Cloud distributed Smart Access Gateways. You can bind a CCN instance to a CEN instance to connect your local branches to Alibaba Cloud.

## Request parameters {#section_jby_xp5_j2b .section}

|Name|Type|Required|Description |
|:---|:---|:-------|:-----------|
|Action|String |Yes| The action to perform. Valid value:

 CreateCloudConnectNetwork

 |
|Name|String|No| The name of the CCN instance.

 The name can contain 2 to 128 characters including a-z, A-Z, 0-9, periods, underlines, and hyphens. The name must start with an English letter, but cannot start with `http://` or `https://`.

 |
|Description|String|No| The description of the CCN instance.

 The description can contain 2 to 256 characters. The description must start with English letters, but cannot start with `http://` or `https://`.

 |
|RegionId|String|No| The area of the CCN instance. Valid value:

 cn-shanghai: Mainland China

 |

## Response parameters {#section_a3q_bp5_j2b .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|
|CcnId|String|The ID of the CCN instance.|
|Name|String|The name of the CCN instance.|
|Description|String|The description of the CCN instance.|

## Examples {#section_s52_kp5_j2b .section}

**Request example**

```
https://smartag.cn-shanghai.aliyuncs.com/?Action=CreateCloudConnectNetwork
&Name=DocTest
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
    <CreateCloudConnectNetworkResponse>
      <Name>DocTest</Name>
      <Status>Active</Status>
      <RequestId>F0C4D78D-C60E-4A3B-A652-3A2835305C0B</RequestId>
      <CcnId>ccn-l9340rlu5enstmzj5i</CcnId>
    </CreateCloudConnectNetworkResponse>
    ```

-   JSON format

    ```
    {
      "Name": "DocTest",
      "Status": "Active",
      "RequestId": "F0C4D78D-C60E-4A3B-A652-3A2835305C0B",
      "CcnId": "ccn-l9340rlu5enstmzj5i"
    }
    ```


