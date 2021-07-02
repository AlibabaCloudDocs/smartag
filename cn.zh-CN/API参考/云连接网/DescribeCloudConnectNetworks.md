# DescribeCloudConnectNetworks

调用DescribeCloudConnectNetworks接口查询指定地域下已创建的云连接网实例信息。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=DescribeCloudConnectNetworks&type=RPC&version=2018-03-13)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|RegionId|String|是|cn-shanghai|云连接网实例所属地域ID。 |
|Name|String|否|ccnname|云连接网实例名称。

 名称长度为2~100个字符，以大小写字母或中文开头，可包含数字、下划线（\_）、半角句号（.）和短划线（-）。 |
|CcnId|String|否|ccn-l9340rlu5enst\*\*\*\*\*|云连接网实例ID。 |
|PageSize|Integer|否|10|分页查询时每页包含的条目数，默认值为**10**，最大值为**50**。 |
|PageNumber|Integer|否|1|查询页码，默认值是**1**。 |
|Action|String|否|DescribeCloudConnectNetworks|系统规定参数。取值：**DescribeCloudConnectNetworks**。 |
|Tag.N.Key|String|否|test|标签键。 |
|Tag.N.Value|String|否|test|标签值。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|CloudConnectNetworks|Array of CloudConnectNetwork| |云连接网实例信息列表。 |
|CloudConnectNetwork| | | |
|CreateTime|Long|1523618639000|云连接网实例的创建时间戳。 |
|AssociatedCenOwnerId|String|168800000000\*\*\*\*|已加载该云连接网实例的云企业网实例的账号ID。 |
|AssociatedCloudBoxCount|String|1|云连接网实例绑定的智能接入网关实例数量。 |
|Tags|Array of Tag| |标签信息列表。 |
|Tag| | | |
|Key|String|test|标签键。 |
|Value|String|test|标签值。 |
|InterworkingStatus|String|enable|是否允许已绑定同一个云连接网实例的智能接入网关实例互通。

 -   **enable**：允许。
-   **disable**：不允许。 |
|CcnId|String|ccn-l9340rlu5enst\*\*\*\*\*\*|云连接网实例ID。 |
|AvailableCloudBoxCount|String|1|云连接网实例已绑定的智能接入网关实例中状态为**可用**的智能接入网关实例的数量。 |
|CidrBlock|String|10.10.10.0/24|私网网段。 |
|Description|String|ccndesc|云连接网实例的描述信息。 |
|SnatCidrBlock|String|10.10.10.0/25|SNAT网段。 |
|AssociatedCenId|String|cen-0jtu0bcbika5b5\*\*\*\*|云连接网实例绑定的云企业网实例ID。 |
|Name|String|ccnname|云连接网实例的名称。 |
|ResourceGroupId|String|rg-acfm2iu4fnc\*\*\*\*|云连接网实例所属的资源组ID。 |
|TotalCount|Integer|3|总条目数。 |
|PageSize|Integer|10|分页查询时每页包含的条目数。 |
|RequestId|String|3F2A0B80-D6D1-4764-8D77-38067DBBA345|请求ID。 |
|PageNumber|Integer|1|查询页码。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?RegionId=cn-shanghai
&Name=ccnname
&CcnId=ccn-l9340rlu5enst*****
&PageSize=10
&PageNumber=1
&Action=DescribeCloudConnectNetworks
&Tag=[{"Key":"test","Value":"test"}]
&公共请求参数
```

正常返回示例

`XML`格式

```
HTTP/1.1 200 OK
Content-Type:application/xml

<DescribeCloudConnectNetworksResponse>
    <CloudConnectNetworks>
        <CloudConnectNetwork>
            <IsDefault>false</IsDefault>
            <InterworkingStatus>enable</InterworkingStatus>
            <ResourceGroupId>rg-acfm2iu4fnc****</ResourceGroupId>
            <CreateTime>1604385674000</CreateTime>
            <CcnId>ccn-iz26o9zye6lhoo****</CcnId>
            <AvailableCloudBoxCount>1</AvailableCloudBoxCount>
            <AssociatedCenOwnerId>1688000000000000</AssociatedCenOwnerId>
            <AssociatedCenId>cen-9z595pdzhmi3jz****</AssociatedCenId>
            <AssociatedCloudBoxCount>1</AssociatedCloudBoxCount>
            <Name>zxtest-202106</Name>
        </CloudConnectNetwork>
        <CloudConnectNetwork>
            <IsDefault>false</IsDefault>
            <InterworkingStatus>enable</InterworkingStatus>
            <ResourceGroupId>rg-acfm2iu4fnc****</ResourceGroupId>
            <CreateTime>1594619327000</CreateTime>
            <CcnId>ccn-frx6evdue4daza****</CcnId>
            <AvailableCloudBoxCount>3</AvailableCloudBoxCount>
            <AssociatedCenOwnerId>1688000000000000</AssociatedCenOwnerId>
            <AssociatedCenId>cen-ol0xptl3edqc8i****</AssociatedCenId>
            <AssociatedCloudBoxCount>3</AssociatedCloudBoxCount>
            <Name>zxtest-OSS</Name>
        </CloudConnectNetwork>
        <CloudConnectNetwork>
            <IsDefault>false</IsDefault>
            <InterworkingStatus>enable</InterworkingStatus>
            <ResourceGroupId>rg-acfm2iu4fnc****</ResourceGroupId>
            <CreateTime>1589866291000</CreateTime>
            <CcnId>ccn-wf0kz6wohe03h2****</CcnId>
            <AvailableCloudBoxCount>1</AvailableCloudBoxCount>
            <AssociatedCenOwnerId>1688000000000000</AssociatedCenOwnerId>
            <CidrBlock>192.168.10.0/24</CidrBlock>
            <AssociatedCenId>cen-8z69wtwqel33lq****</AssociatedCenId>
            <AssociatedCloudBoxCount>1</AssociatedCloudBoxCount>
            <Name>zxtest</Name>
        </CloudConnectNetwork>
    </CloudConnectNetworks>
    <TotalCount>3</TotalCount>
    <PageSize>10</PageSize>
    <RequestId>7DA93FE9-D008-49FB-8D9B-186F509EA307</RequestId>
    <PageNumber>1</PageNumber>
</DescribeCloudConnectNetworksResponse>
```

`JSON`格式

```
HTTP/1.1 200 OK
Content-Type:application/json

{
  "CloudConnectNetworks" : {
    "CloudConnectNetwork" : [ {
      "IsDefault" : false,
      "InterworkingStatus" : "enable",
      "ResourceGroupId" : "rg-acfm2iu4fnc****",
      "CreateTime" : 1604385674000,
      "CcnId" : "ccn-iz26o9zye6lhoo****",
      "AvailableCloudBoxCount" : 1,
      "AssociatedCenOwnerId" : 1688000000000000,
      "AssociatedCenId" : "cen-9z595pdzhmi3jz****",
      "AssociatedCloudBoxCount" : 1,
      "Name" : "zxtest-202106"
    }, {
      "IsDefault" : false,
      "InterworkingStatus" : "enable",
      "ResourceGroupId" : "rg-acfm2iu4fnc****",
      "CreateTime" : 1594619327000,
      "CcnId" : "ccn-frx6evdue4daza****",
      "AvailableCloudBoxCount" : 3,
      "AssociatedCenOwnerId" : 1688000000000000,
      "AssociatedCenId" : "cen-ol0xptl3edqc8i****",
      "AssociatedCloudBoxCount" : 3,
      "Name" : "zxtest-OSS"
    }, {
      "IsDefault" : false,
      "InterworkingStatus" : "enable",
      "ResourceGroupId" : "rg-acfm2iu4fnc****",
      "CreateTime" : 1589866291000,
      "CcnId" : "ccn-wf0kz6wohe03h2****",
      "AvailableCloudBoxCount" : 1,
      "AssociatedCenOwnerId" : 1688000000000000,
      "CidrBlock" : "192.168.10.0/24",
      "AssociatedCenId" : "cen-8z69wtwqel33lq****",
      "AssociatedCloudBoxCount" : 1,
      "Name" : "zxtest"
    } ]
  },
  "TotalCount" : 3,
  "PageSize" : 10,
  "RequestId" : "7DA93FE9-D008-49FB-8D9B-186F509EA307",
  "PageNumber" : 1
}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidTagKey|The specified tag key is invalid.|Tag标签的Key值不合法。|
|400|InvalidTagValue|The specified tag value is invalid.|Tag标签的Value值不合法。|
|400|SizeLimitExceeded.TagNum|The maximum number of tags is exceeded.|Tag个数超过了最大数量。|
|400|SizeLimitExceeded.ResourceId|The maximum number of resource IDs is exceeded.|ResourceIds个数超过了最大数量。|
|400|Forbidden.TagKey.Duplicated|The specified tag key already exists.|TagKey存在相同的值。|
|403|Forbidden|User not authorized to operate on the specified resource.|用户没有操作此资源的权限。|

访问[错误中心](https://error-center.aliyun.com/status/product/Smartag)查看更多错误码。

