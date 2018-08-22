# DescribeSmartAccessGateways {#reference_kkg_dks_j2b .reference}

Query Smart Access Gateway instances.

## Request parameters {#section_hsb_5g5_j2b .section}

|Name|Type|Required|Description |
|:---|:---|:-------|:-----------|
|Action|String |Yes| The action to perform. Valid value:

 DescribeSmartAccessGateways

 |
|RegionId|String|No| The area of the Smart Access Gateway instance. Valid value:

 cn-shanghai: Mainland China

 |
|SmartAGId|String|No|The ID of the Smart Access Gateway instance.|
|Status|String|No| The status of the Smart Access Gateway instance. Valid value:

-   Ordered: The Smart Access Gateway device has been ordered.
-   Delivered: The Smart Access Gateway device has been delivered.
-   Received: The Smart Access Gateway device has been received.
-   Returning: The Smart Access Gateway device is being returned.
-   ACTIVE: The Smart Access Gateway device is active.
-   Init: The Smart Access Gateway device is being initiated.

 |
|Name|String|No|The name of the Smart Access Gateway instance.|
|AssociatedCcnId|String|No|The ID of the CCN instance bound to the Smart Access Gateway instance.|
|PageNumber|Integer|No|The number of pages to return. The default value is 1.|
|PageSize |Integer|No|The number of rows per page. The maximum value is 50 and the default value is 10.|

## Response parameters {#section_os2_ph5_j2b .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|
|PageNumber|Integer|The current page number.|
|TotalCount |Integer|The number of queried entries.|
|PageSize |Integer  |The number of entries on the current page.|
|SmartAccessGateways|List|A list of Smart Access Gateway instances.|

|Name|Type|Description|
|:---|:---|:----------|
|SmartAGId|String|The ID of the Smart Access Gateway instance.|
|Name|String|The name of the Smart Access Gateway instance.|
|MaxBandwidth|String|The bandwidth of the Smart Access Gateway instance.|
|Status|String|The status of the Smart Access Gateway instance.|
|CidrBlock|String|The private CIDR block used by the on-premises client for communication.|
|AssociatedCcnId|String|The ID of the CCN instance bound to the Smart Access Gateway instance.|
|AssociatedCcnId|String|The name of the CCN instance bound to the Smart Access Gateway instance.|
|Description|String|The description of the Smart Access Gateway instance.|
|CreateTime|Long|The time the Smart Access Gateway instance was created.|
|EndTime|Long|The time the Smart Access Gateway instance expires.|
|SoftwareVersion|String|The software version of the Smart Access Gateway instance.|
|SerialNumber|String|The serial number of the Smart Access Gateway instance.|

## Examples {#section_wyx_j35_j2b .section}

**Request example**

```
https://smartag.cn-shanghai.aliyuncs.com/?Action=DescribeSmartAccessGateways
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
    <DescribeSmartAccessGatewaysResponse>
      <PageNumber>1</PageNumber>
      <SmartAccessGateways>
          <SmartAccessGateway>
              <Name>test</Name>
              <SmartAGId>sag-v0fkpk4akfz5hebved</SmartAGId>
              <Status>Init</Status>
              <AssociatedCcnName>xuehao</AssociatedCcnName>
              <AssociatedCcnId>ccn-bxuau4ezctts2kfxyr</AssociatedCcnId>
              <CreateTime>1523604565000</CreateTime>
              <EndTime>1526227200000</EndTime>
              <SoftwareVersion>1.0.0</SoftwareVersion>
              <MaxBandwidth>1M</MaxBandwidth>
          </SmartAccessGateway>
          <SmartAccessGateway>
              <Name>xuehao</Name>
              <SmartAGId>sag-c3m3n1khz58lbfhfw1</SmartAGId>
              <CidrBlock>172.16.1.0/24</CidrBlock>
              <Status>Init</Status>
              <AssociatedCcnName>test</AssociatedCcnName>
              <AssociatedCcnId>ccn-kygbldwikzdg2g9b8e</AssociatedCcnId>
              <CreateTime>1523597460000</CreateTime>
              <EndTime>1526227200000</EndTime>
              <SoftwareVersion>1.0.0</SoftwareVersion>
              <MaxBandwidth>3M</MaxBandwidth>
          </SmartAccessGateway>
      </SmartAccessGateways>
      <TotalCount>2</TotalCount>
      <PageSize>10</PageSize>
      <RequestId>7F26258D-8BDE-4EC4-BB4D-4DDC64F64F77</RequestId>
    </DescribeSmartAccessGatewaysResponse>
    ```

-   JSON format

    ```
    {
      "PageNumber": 1,
      "Smartaccessgateways ":{
        "SmartAccessGateway": [
          {
            "Name": "test",
            "SmartAGId": "sag-v0fkpk4akfz5hebved",
            "Status": "Init",
            "AssociatedCcnName": "xuehao",
            "AssociatedCcnId": "ccn-bxuau4ezctts2kfxyr",
            "CreateTime": 1523604565000,
            "EndTime": 1526227200000,
            "SoftwareVersion": "1.0.0",
            "MaxBandwidth": "1M"
          },
          {
            "Name": "xuehao",
            "SmartAGId": "sag-c3m3n1khz58lbfhfw1",
            "CidrBlock": "10.0.0.0/24",
            "Status": "Init",
            "AssociatedCcnName": "test",
            "AssociatedCcnId": "ccn-kygbldwikzdg2g9b8e",
            "CreateTime": 1523597460000,
            "EndTime": 1526227200000,
            "SoftwareVersion": "1.0.0",
            "MaxBandwidth": "3M"
          }
        ]
      },
      "TotalCount": 2,
      "Pagesize": 10,
      "RequestId": "7F26258D-8BDE-4EC4-BB4D-4DDC64F64F77"
    }
    ```


