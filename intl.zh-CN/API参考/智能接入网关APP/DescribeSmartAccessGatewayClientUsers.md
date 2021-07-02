# DescribeSmartAccessGatewayClientUsers

调用DescribeSmartAccessGatewayClientUsers查询智能接入网关APP实例下的客户端账号信息。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=DescribeSmartAccessGatewayClientUsers&type=RPC&version=2018-03-13)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|DescribeSmartAccessGatewayClientUsers|要执行的操作。取值：**DescribeSmartAccessGatewayClientUsers**。 |
|RegionId|String|是|cn-shanghai|智能接入网关APP实例所属的地域ID。 |
|SmartAGId|String|是|sag-jfkskjfjf\*\*\*\*\*\*\*\*|智能接入网关APP实例ID。 |
|UserName|String|否|doctest|客户端的用户名。 |
|PageNumber|Integer|否|1|查询页码。默认值为**1**。 |
|PageSize|Integer|否|10|分页查询时每页的条目数。

默认值为**10**。 |
|UserMail|String|否|123456@example.com|客户端的邮箱地址。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|TotalCount|Integer|1|总条目数。 |
|PageSize|Integer|10|分页查询时每页的条目数。 |
|RequestId|String|62F4CF10-F909-487E-8E95-BC35457C5F50|请求ID。 |
|PageNumber|Integer|1|查询页码。 |
|Users|Array of User| |客户端信息列表。 |
|User| | | |
|Bandwidth|Integer|2000|客户端可使用的上云带宽。单位：Kbps。 |
|State|Integer|1|客户端的启用状态：

-   **0**：表示启用该客户端。
-   **1**：表示禁用该客户端。 |
|ClientIp|String|10.10.10.1|系统为客户端分配的IP地址。 |
|UserName|String|doctest|客户端的用户名。 |
|UserMail|String|123456@example.com|客户端的邮箱地址。 |
|AccelerateBandwidth|Long|1000|客户端可使用的应用加速带宽峰值。单位：Kbps。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=DescribeSmartAccessGatewayClientUsers
&RegionId=cn-shanghai
&SmartAGId=sag-jfkskjfjf********
&UserName=doctest
&PageNumber=1
&PageSize=10
&UserMail=123456@example.com
&公共请求参数
```

正常返回示例

`XML`格式

```
HTTP/1.1 200 OK
Content-Type:application/xml

<DescribeSmartAccessGatewayClientUsersResponse>
    <TotalCount>1</TotalCount>
    <PageSize>10</PageSize>
    <RequestId>C7BB5E46-6247-451B-8954-61868D5D66C4</RequestId>
    <PageNumber>1</PageNumber>
    <Users>
        <User>
            <AccelerateBandwidth>1000</AccelerateBandwidth>
            <UserName>zx1234567</UserName>
            <State>0</State>
            <UserMail>123@example.com</UserMail>
            <Bandwidth>2000</Bandwidth>
        </User>
    </Users>
</DescribeSmartAccessGatewayClientUsersResponse>
```

`JSON`格式

```
HTTP/1.1 200 OK
Content-Type:application/json

{
  "TotalCount" : 1,
  "PageSize" : 10,
  "RequestId" : "C7BB5E46-6247-451B-8954-61868D5D66C4",
  "PageNumber" : 1,
  "Users" : {
    "User" : [ {
      "AccelerateBandwidth" : 1000,
      "UserName" : "zx1234567",
      "State" : 0,
      "UserMail" : "123@example.com",
      "Bandwidth" : 2000
    } ]
  }
}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|SAG.InstanceIdEmpty|You must specify the SAG instance ID.|智能网关实例ID为空。|
|400|SAG.InstanceNoFound|The specified SAG instance does not exist.|智能网关实例不存在。|

访问[错误中心](https://error-center.alibabacloud.com/status/product/Smartag)查看更多错误码。

