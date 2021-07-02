# DescribeBindableSmartAccessGateways

调用DescribeBindableSmartAccessGateways接口查询指定地域下云连接网实例可绑定的智能接入网关实例信息。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=DescribeBindableSmartAccessGateways&type=RPC&version=2018-03-13)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeBindableSmartAccessGateways|要执行的操作。取值：**DescribeBindableSmartAccessGateways**。 |
|RegionId|String|是|cn-shanghai|智能接入网关实例的地域ID。 |
|CcnId|String|否|ccn-fu75a6m4clv7ai\*\*\*\*|云连接网实例ID。 |
|CrossAccount|Boolean|否|false|是否只查询跨账号所属的智能接入网关实例。取值：

 -   **false**（默认值）：否。
-   **true**：是。 |
|PageSize|Integer|否|10|分页查询时，每页包含的条目数。默认值为**10**，最大值为**50**。 |
|PageNumber|Integer|否|1|查询页码。默认值为**1**。 |
|SmartAGId|String|否|sag-00uc4vgxch1zsu\*\*\*\*|智能接入网关实例ID。 |
|Name|String|否|sdggd111|智能接入网关实例名称。

 名称长度为2~128个字符，以大小写字母或中文开头，可包含数字、下划线（\_）和短划线（-）。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|TotalCount|Integer|2|智能接入网关实例总数。 |
|PageSize|Integer|10|分页查询时，每页包含的条目数。 |
|RequestId|String|9731C2F5-B9A4-42FD-AFD2-361A403E6E85|请求ID。 |
|PageNumber|Integer|1|查询页码。 |
|SmartAccessGateways|Array of SmartAccessGateway| |智能接入网关实例信息列表。 |
|SmartAccessGateway| | | |
|SmartAGId|String|sag-00uc4vgxch1zsu\*\*\*\*|智能接入网关实例ID。 |
|Name|String|sdggd111|智能接入网关实例名称。 |
|SmartAGUid|Long|168840159596\*\*\*\*|智能接入网关实例所属账号ID。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=DescribeBindableSmartAccessGateways
&RegionId=cn-shanghai
&CcnId=ccn-fu75a6m4clv7ai****
&CrossAccount=false
&PageSize=10
&PageNumber=1
&SmartAGId=sag-00uc4vgxch1zsu****
&Name=sdggd111
&公共请求参数
```

正常返回示例

`XML`格式

```
HTTP/1.1 200 OK
Content-Type:application/xml

<DescribeBindableSmartAccessGatewaysResponse>
<PageNumber>1</PageNumber>
<PageSize>10</PageSize>
<RequestId>9731C2F5-B9A4-42FD-AFD2-361A403E6E85</RequestId>
<SmartAccessGateways>
    <SmartAccessGateway>
        <Name>zhen****-for-acl-performance-sag-154381343****</Name>
        <SmartAGId>sag-00uc4vgxch1zsu****</SmartAGId>
        <SmartAGUid>168840159596****</SmartAGUid>
    </SmartAccessGateway>
    <SmartAccessGateway>
        <Name>zhen****-for-acl-performance-sag-154383278****</Name>
        <SmartAGId>sag-0bs2aephgv7zfo****</SmartAGId>
        <SmartAGUid>168840159596****</SmartAGUid>
    </SmartAccessGateway>
</SmartAccessGateways>
<TotalCount>2</TotalCount>
</DescribeBindableSmartAccessGatewaysResponse>
```

`JSON`格式

```
HTTP/1.1 200 OK
Content-Type:application/json

{
  "PageNumber" : 1,
  "PageSize" : 10,
  "RequestId" : "9731C2F5-B9A4-42FD-AFD2-361A403E6E85",
  "SmartAccessGateways" : {
    "SmartAccessGateway" : [ {
      "Name" : "zhen****-for-acl-performance-sag-154381343****",
      "SmartAGId" : "sag-00uc4vgxch1zsu****",
      "SmartAGUid" : "168840159596****"
    }, {
      "Name" : "zhen****-for-acl-performance-sag-154383278****",
      "SmartAGId" : "sag-0bs2aephgv7zfo****",
      "SmartAGUid" : "168840159596*****"
    } ]
  },
  "TotalCount" : 2
}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|CCN.InvalidId|You must specify the CCN instance ID.|云连接网实例ID不存在。|
|400|InvalidRegionID|The specified regionId does not exist.|指定的RegionId不存在。|

访问[错误中心](https://error-center.alibabacloud.com/status/product/Smartag)查看更多错误码。

