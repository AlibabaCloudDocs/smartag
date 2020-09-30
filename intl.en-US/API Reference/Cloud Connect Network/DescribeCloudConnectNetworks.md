# DescribeCloudConnectNetworks

You can call this operation to query the information about Cloud Connect Network \(CCN\) instances that you have created.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=DescribeCloudConnectNetworks&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|DescribeCloudConnectNetworks|The operation that you want to perform.

 Set the value to **DescribeCloudConnectNetworks**. |
|RegionId|String|Yes|cn-hangzhou|The region where the CCN instance is deployed. |
|Name|String|No|The name of the CCN instance|The name of the CCN instance. |
|CcnId|String|No|ccn-l9340rlu5enst\*\*\*\*\*|The ID of the CCN instance. |
|PageSize|Integer|No|4|The number of entries returned on each page. Maximum value: **50**. Default value: **10**. |
|PageNumber|Integer|No|4|The number of the page to return. Pages start from page 1. Default value: **1**. |
|Tag.N.Key|String|No|2|The tag of the CCN instance. Maximum value of N: **20**. |
|Tag.N.Value|String|No|2|The value of the tag. Maximum value of N: **20**. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|3F2A0B80-D6D1-4764-8D77-38067DBBA345|The ID of the request. |
|TotalCount|Integer|2|The total number of entries returned. |
|PageNumber|Integer|1|The page number of the returned page. |
|PageSize|Integer|2|The number of entries returned on each page. |
|CloudConnectNetworks|Array| |The information about the CCN instances. |
|CcnId|String|ccn-l9340rlu5enst\*\*\*\*\*\*|The ID of the CCN instance. |
|Name|String|The name of the CCN instance|The name of the CCN instance. |
|AssociatedCloudBoxCount|String|3|The number of Smart Access Gateway \(SAG\) devices that are associated with the CCN instance. |
|AvailableCloudBoxCount|String|2|The number of available SAG devices of the associated SAG devices. |
|AssociatedCenId|String|cen-0jtu0bcbika5b5\*\*\*\*|The ID of the Cloud Enterprise Network \(CEN\) instance that is associated with the CCN instance. |
|AssociatedCenOwnerId|String|1954105122583124|The account ID of the CEN instance. |
|Description|String|The description of the CCN instance|The description of the CCN instance. |
|CreateTime|Long|1523618639000|The time when the CCN instance was created. |
|IsDefault|Boolean|false|Specifies whether the CCN instance was created by default.

 If no CCN instance is available when you associate the SAG device, a CCN instance is created by default. |
|CidrBlock|String|10.10.10.0/24|The private CIDR block. |
|SnatCidrBlock|String|10.10.10.5/24|The Source Network Address Translation \(SNAT\) CIDR block. |
|InterworkingStatus|String|enable|Specifies whether to allow the SAG device associated with a CCN instance to communicate with each other.

 -   **enable**: enables the communication.
-   **disable**: disables the communication. |
|Tags|Array| |The list of tags. |
|Key|String|2|The ordinal number of the tag. |
|Value|String|2|The value of the tag. |

## Examples

Sample requests

```
https://smartag.cn-shanghai.aliyuncs.com/?Action=DescribeCloudConnectNetworks
&CommonParameters
```

Sample success responses

`XML` format

```
<DescribeCloudConnectNetworksResponse>
  <PageNumber>1</PageNumber>
  <CloudConnectNetworks>
        <CloudConnectNetwork>
              <Name>None</Name>
              <CidrBlock>192.168.0.0/16,10.0.0.0/8</CidrBlock>
              <Description>None</Description>
              <AvailableCloudBoxCount>0</AvailableCloudBoxCount>
              <AssociatedCenOwnerId>1688401595963306</AssociatedCenOwnerId>
              <IsDefault>true</IsDefault>
              <AssociatedCloudBoxCount>1</AssociatedCloudBoxCount>
              <CreateTime>1582204971000</CreateTime>
              <InterworkingStatus>disable</InterworkingStatus>
              <CcnId>ccn-e3rmhknrs5h51h****</CcnId>
        </CloudConnectNetwork>
        <CloudConnectNetwork>
              <Name>None</Name>
              <CidrBlock>192.168.0.0/16,10.0.0.0/8</CidrBlock>
              <Description>None</Description>
              <AvailableCloudBoxCount>0</AvailableCloudBoxCount>
              <AssociatedCenOwnerId>1688401595963306</AssociatedCenOwnerId>
              <IsDefault>true</IsDefault>
              <AssociatedCloudBoxCount>1</AssociatedCloudBoxCount>
              <CreateTime>1582204958000</CreateTime>
              <InterworkingStatus>enable</InterworkingStatus>
              <CcnId>ccn-l4olvf0dthc4iw****</CcnId>
        </CloudConnectNetwork>
        <CloudConnectNetwork>
              <Name>ccn-bvt-sag1000-2020-02-18-01-25-42</Name>
              <AvailableCloudBoxCount>1</AvailableCloudBoxCount>
              <AssociatedCenOwnerId>1688401595963306</AssociatedCenOwnerId>
              <IsDefault>false</IsDefault>
              <AssociatedCloudBoxCount>3</AssociatedCloudBoxCount>
              <CreateTime>1581960342000</CreateTime>
              <InterworkingStatus>enable</InterworkingStatus>
              <CcnId>ccn-t67f7x9yhnuoav****</CcnId>
        </CloudConnectNetwork>
        <CloudConnectNetwork>
              <Name>test1212</Name>
              <AvailableCloudBoxCount>0</AvailableCloudBoxCount>
              <AssociatedCenOwnerId>1688401595963306</AssociatedCenOwnerId>
              <IsDefault>false</IsDefault>
              <AssociatedCloudBoxCount>0</AssociatedCloudBoxCount>
              <CreateTime>1581910623000</CreateTime>
              <InterworkingStatus>enable</InterworkingStatus>
              <CcnId>ccn-2v3svns35flx76****</CcnId>
        </CloudConnectNetwork>
        <CloudConnectNetwork>
              <Name>ccn-bvt-sag1000-2020-02-14-19-15-25</Name>
              <AssociatedCenId></AssociatedCenId>
              <AvailableCloudBoxCount>0</AvailableCloudBoxCount>
              <AssociatedCenOwnerId>1688401595963306</AssociatedCenOwnerId>
              <IsDefault>false</IsDefault>
              <AssociatedCloudBoxCount>2</AssociatedCloudBoxCount>
              <CreateTime>1581678926000</CreateTime>
              <InterworkingStatus>enable</InterworkingStatus>
              <CcnId>ccn-fp1a0et30tpd9s****</CcnId>
        </CloudConnectNetwork>
        <CloudConnectNetwork>
              <Name>split-ccn-test</Name>
              <AssociatedCenId>cen-h1qbyjcot38czx68nl</AssociatedCenId>
              <AvailableCloudBoxCount>1</AvailableCloudBoxCount>
              <AssociatedCenOwnerId>1688401595963306</AssociatedCenOwnerId>
              <IsDefault>false</IsDefault>
              <AssociatedCloudBoxCount>1</AssociatedCloudBoxCount>
              <CreateTime>1581563640000</CreateTime>
              <InterworkingStatus>enable</InterworkingStatus>
              <CcnId>ccn-k7eyqq0nw7uy5v****</CcnId>
        </CloudConnectNetwork>
  </CloudConnectNetworks>
  <TotalCount>219</TotalCount>
  <PageSize>10</PageSize>
  <RequestId>F6BCDE40-C334-4592-AD49-854680DA44D3</RequestId>
</DescribeCloudConnectNetworksResponse>
```

`JSON` format

```
{
    "PageNumber": 1,
    "CloudConnectNetworks": {
        "CloudConnectNetwork": [
            {
                "Name": "None",
                "CidrBlock": "192.168.0.0/16,10.0.0.0/8",
                "Description": "None",
                "AvailableCloudBoxCount": 0,
                "AssociatedCenOwnerId": 1688401595963306,
                "IsDefault": true,
                "AssociatedCloudBoxCount": 1,
                "CreateTime": 1582204971000,
                "InterworkingStatus": "disable",
                "CcnId": "ccn-e3rmhknrs5h51h****"
            },
            {
                "Name": "None",
                "CidrBlock": "192.168.0.0/16,10.0.0.0/8",
                "Description": "None",
                "AvailableCloudBoxCount": 0,
                "AssociatedCenOwnerId": 1688401595963306,
                "IsDefault": true,
                "AssociatedCloudBoxCount": 1,
                "CreateTime": 1582204958000,
                "InterworkingStatus": "enable",
                "CcnId": "ccn-l4olvf0dthc4iw****"
            },
            {
                "Name": "ccn-bvt-sag1000-2020-02-18-01-25-42",
                "AvailableCloudBoxCount": 1,
                "AssociatedCenOwnerId": 1688401595963306,
                "IsDefault": false,
                "AssociatedCloudBoxCount": 3,
                "CreateTime": 1581960342000,
                "InterworkingStatus": "enable",
                "CcnId": "ccn-t67f7x9yhnuoav****"
            },
            {
                "Name": "test1212",
                "AvailableCloudBoxCount": 0,
                "AssociatedCenOwnerId": 1688401595963306,
                "IsDefault": false,
                "AssociatedCloudBoxCount": 0,
                "CreateTime": 1581910623000,
                "InterworkingStatus": "enable",
                "CcnId": "ccn-2v3svns35flx76****"
            },
            {
                "Name": "ccn-bvt-sag1000-2020-02-14-19-15-25",
                "AssociatedCenId": "",
                "AvailableCloudBoxCount": 0,
                "AssociatedCenOwnerId": 1688401595963306,
                "IsDefault": false,
                "AssociatedCloudBoxCount": 2,
                "CreateTime": 1581678926000,
                "InterworkingStatus": "enable",
                "CcnId": "ccn-fp1a0et30tpd9s****"
            },
            {
                "Name": "split-ccn-test",
                "AssociatedCenId": "cen-h1qbyjcot38czx68nl",
                "AvailableCloudBoxCount": 1,
                "AssociatedCenOwnerId": 1688401595963306,
                "IsDefault": false,
                "AssociatedCloudBoxCount": 1,
                "CreateTime": 1581563640000,
                "InterworkingStatus": "enable",
                "CcnId": "ccn-k7eyqq0nw7uy5v****"
            }
        ]
    },
    "TotalCount": 219,
    "PageSize": 10,
    "RequestId": "F6BCDE40-C334-4592-AD49-854680DA44D3"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|403|Forbidden|User not authorized to operate on the specified resource.|The error code returned because you do not have the permission to manage the resource.|
|400|InvalidTagKey|The specified tag key is invalid.|The error code returned because the value of the tag key is invalid.|
|400|InvalidTagValue|The specified tag value is invalid.|The error code returned because the value of the tag key is invalid.|
|400|SizeLimitExceeded.TagNum|The maximum number of tags is exceeded.|The error code returned because the number of tags exceeds the upper limit.|
|400|SizeLimitExceeded.ResourceId|The maximum number of resource IDs is exceeded.|The error code returned because the number of resource IDs exceeds the upper limit.|
|400|Forbidden.TagKey.Duplicated|The specified tag key already exists.|The error code returned because a tag key value overlaps with another.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

