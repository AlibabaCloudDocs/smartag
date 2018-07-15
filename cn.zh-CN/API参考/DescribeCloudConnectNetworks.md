# DescribeCloudConnectNetworks {#reference_w1w_kks_j2b .reference}

查询已创建的云连接网。

## 请求参数 {#section_jby_xp5_j2b .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 执行的操作，取值：

 DescribeCloudConnectNetworks

 |
|RegionId|String|否| 云连接网的所属区域。取值：

 cn-shanghai：中国大陆

 |
|Name|String|否|云连接网名称。|
|CcnId|String|否|云连接网ID。|
|PageNumber|Integer|否|实例状态列表的页码，默认值是1。|
|PageSize|Integer|否|分页查询时设置的每页行数，默认值为10，最大值为50。|

## 返回参数 {#section_a3q_bp5_j2b .section}

|参数|类型|描述|
|--|--|--|
|RequestId|String|请求ID。|
|PageNumber|Integer|当前页码。|
|TotalCount|Integer|列表条目数。|
|PageSize|Integer|当前分页包含多少条目。|
|CloudConnectNetworks|List|云连接网的信息。|

|参数|类型|描述|
|--|--|--|
|CcnId|String|云连接网ID。|
|Name|String|云连接网名称。|
|Description|String|云连接网描述。|
|AssociatedCloudBoxCount|String|云连接网绑定的智能接入网关。|
|AvailableCloudBoxCount|Integer|已绑定的智能接入网关中可用的网关数量。|
|AssociatedCenId|String|绑定的云企业网ID。|
|AssociatedCenOwnerId|String|云企业网的账号ID。|
|CreateTime|Long|云连接网的创建时间。|

## 示例 {#section_s52_kp5_j2b .section}

**请求示例**

```
https://smartag.cn-shanghai.aliyuncs.com/?Action=DescribeCloudConnectNetworks
&CommonParameters
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <DescribeCloudConnectNetworksResponse>
      <CloudConnectNetworks>
          <CloudConnectNetwork>
              <Name>DocTest</Name>
              <AvailableCloudBoxCount>2</AvailableCloudBoxCount>
              <AssociatedCenOwnerId>1954105122583124</AssociatedCenOwnerId>
              <IsDefault>false</IsDefault>
              <AssociatedCloudBoxCount>3</AssociatedCloudBoxCount>
              <CreateTime>1523618639000</CreateTime>
              <CcnId>ccn-l9340rlu5enstmzj5i</CcnId>
          </CloudConnectNetwork>
          <CloudConnectNetwork>
              <Name>CEN测试</Name>
              <Description></Description>
              <AvailableCloudBoxCount>0</AvailableCloudBoxCount>
              <AssociatedCenOwnerId>1954105122583124</AssociatedCenOwnerId>
              <IsDefault>false</IsDefault>
              <AssociatedCloudBoxCount>0</AssociatedCloudBoxCount>
              <CreateTime>1523190009000</CreateTime>
              <CcnId>ccn-oa5ftyg6t48gnhb61k</CcnId>
          </CloudConnectNetwork>
      </CloudConnectNetworks>
      <PageNumber>1</PageNumber>
      <TotalCount>3</TotalCount>
      <PageSize>10</PageSize>
      <RequestId>3F2A0B80-D6D1-4764-8D77-38067DBBA345</RequestId>
    </DescribeCloudConnectNetworksResponse>
    ```

-   JSON格式

    ```
    {
    "CloudConnectNetworks": {
      "CloudConnectNetwork": [
        {
          "Name": "DocTest",
          "AvailableCloudBoxCount": 2,
          "AssociatedCenOwnerId": "1954105122583124",
          "IsDefault": false,
          "AssociatedCloudBoxCount": 3,
          "CreateTime": 1523618639000,
          "CcnId": "ccn-l9340rlu5enstmzj5i"
        },
        {
          "Name": "CEN测试",
          "Description": "",
          "AvailableCloudBoxCount": 0,
          "AssociatedCenOwnerId": "1954105122583124",
          "IsDefault": false,
          "AssociatedCloudBoxCount": 0,
          "CreateTime": 1523190009000,
          "CcnId": "ccn-oa5ftyg6t48gnhb61k"
        }
      ]
    },
    "PageNumber": 1,
    "TotalCount": 3,
    "PageSize": 10,
    "RequestId": "3F2A0B80-D6D1-4764-8D77-38067DBBA345"
    }
    ```


