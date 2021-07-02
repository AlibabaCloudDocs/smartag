# CreateCloudConnectNetwork

调用CreateCloudConnectNetwork接口创建云连接网实例。

## 背景信息

云连接网CCN（Cloud Connect Network）是由阿里云分布式接入网关组成的设备接入矩阵，是智能接入网关的另一个重要组成部分。在将智能接入网关与云连接网绑定后，智能接入网关便可通过云连接网将本地网络连接至阿里云。更多信息，请参见[云连接网介绍](~~93667~~)。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=CreateCloudConnectNetwork&type=RPC&version=2018-03-13)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|RegionId|String|否|cn-shanghai|云连接网实例所属地域ID。 |
|Name|String|否|ccnname|云连接网实例的名称。

 名称长度为2~100个字符，以大小写字母或中文开头，可包含数字、下划线（\_）、半角句号（.）和短划线（-）。 |
|Description|String|否|ccndesc|云连接网实例的描述。

 描述长度为2~128个字符，以大小写字母或中文开头，可包含数字、下划线（\_）和短划线（-）。 |
|Action|String|否|CreateCloudConnectNetwork|要执行的操作。取值：**CreateCloudConnectNetwork**。 |
|CidrBlock|String|否|172.XX.XX.0/24|私网网段。 |
|SnatCidrBlock|String|否|172.XX.XX.0/25|SNAT私网网段。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|Status|String|Active|云连接网实例状态。

 -   **Active**：正常。
-   **Pending**：待创建。 |
|Description|String|ccndesc|云连接网实例的描述信息。 |
|RequestId|String|C48E8EB2-37A4-495B-A95C-29CA1FD26C82|请求ID。 |
|CcnId|String|ccn-l9340rlu5ens\*\*\*\*\*|云连接网实例ID。 |
|CidrBlock|String|172.XX.XX.0/24|私网网段。 |
|SnatCidrBlock|String|172.XX.XX.0/25|SNAT私网网段。 |
|Name|String|ccnname|云连接网实例的名称。 |
|ResourceGroupId|String|rg-acfm2iu4fnc\*\*\*\*|云连接网实例所属的资源组ID。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?RegionId=cn-shanghai
&Name=ccnname
&Description=ccndesc
&Action=CreateCloudConnectNetwork
&CidrBlock=172.XX.XX.0/24
&SnatCidrBlock=172.XX.XX.0/25
&公共请求参数
```

正常返回示例

`XML`格式

```
HTTP/1.1 200 OK
Content-Type:application/xml

<CreateCloudConnectNetworkResponse>
<Status>Active</Status>
<RequestId>C48E8EB2-37A4-495B-A95C-29CA1FD26C82</RequestId>
<ResourceGroupId>rg-acfm2iu4fnc****</ResourceGroupId>
<CcnId>ccn-tcw17az0542xcj****</CcnId>
<Name>zxtest</Name>
</CreateCloudConnectNetworkResponse>
```

`JSON`格式

```
HTTP/1.1 200 OK
Content-Type:application/json

{
  "Status" : "Active",
  "RequestId" : "C48E8EB2-37A4-495B-A95C-29CA1FD26C82",
  "ResourceGroupId" : "rg-acfm2iu4fnc****",
  "CcnId" : "ccn-tcw17az0542xcj****",
  "Name" : "zxtest"
}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|CCN.CidrAmountLimit|The maximum number of CCN CIDR blocks is exceeded.|云连接网的地址段个数超限。|
|400|CCN.CidrEmpty|You must specify the CCN CIDR block.|云连接网的地址段为空。|
|400|CCN.InvalidCidr|The specified CCN CIDR block is invalid.|云连接网的地址段非法。|
|400|CCN.InvalidSnatCidr|The SNAT CIDR block of CCN is invalid.|云连接网SNAT地址段非法。|
|400|CCN.SnatCidrConflict|The specified SNAT CIDR block is invalid.|指定的SNAT地址段存在冲突。|
|403|InvalidDescription|Description not valid.|详情描述超过长度限制。|
|403|InvalidName|Name not valid.|名称不合法。|
|403|CcnAmountLimit|The CCNs you created has reached the limit, you can raise the limit by application.|您创建的智能连接网数量已经达到限额，您可以通过工单申请提升限额。|
|403|Forbidden|User not authorized to operate on the specified resource.|用户没有操作此资源的权限。|

访问[错误中心](https://error-center.aliyun.com/status/product/Smartag)查看更多错误码。

