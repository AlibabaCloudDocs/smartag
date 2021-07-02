# DescribeQoses

调用DescribeQoses接口查询指定地域下QoS策略实例信息。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=DescribeQoses&type=RPC&version=2018-03-13)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|DescribeQoses|要执行的操作。取值：**DescribeQoses**。 |
|RegionId|String|是|cn-shanghai|QoS策略实例所属的地域ID。 |
|QosIds|String|否|qos-oek3r2cmvk7m8q\*\*\*\*|QoS策略实例ID。

 -   如果要同时查询多个QoS策略实例，多个实例ID之间以半角逗号（,）分隔开。
-   如果不填写该项，则默认查询该地域下所有QoS策略实例信息。 |
|QosName|String|否|zxtest|QoS策略实例名称。

 名称长度为2~100个字符，以大小写字母或中文开头，可包含数字、下划线（\_）、半角句号（.）和短划线（-）。 |
|PageSize|Integer|否|10|分页查询时，每页包含的条目数。默认值为**10**，最大值为**50**。 |
|PageNumber|Integer|否|1|查询页码。默认值为**1**。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|TotalCount|Integer|1|总条目数。 |
|PageSize|Integer|10|分页查询时，每页包含的条目数。 |
|RequestId|String|2B5F35DD-0D66-41FC-AA99-BAE473E1A7A2|请求ID。 |
|PageNumber|Integer|1|查询页码。 |
|Qoses|Array of Qos| |QoS策略实例信息列表。 |
|Qos| | | |
|QosDescription|String|description|QoS策略实例的描述信息。 |
|SagCount|String|0|QoS策略实例关联的智能接入网关实例数量。 |
|SmartAGIds|String|sag-x34wj76fe0vhw\*\*\*\*\*,sag-jp04l844chg16\*\*\*\*\*|QoS策略实例关联的智能接入网关实例列表。 |
|QosId|String|qos-oek3r2cmvk7m8q\*\*\*\*|QoS策略实例ID。 |
|QosName|String|zxtest|QoS策略实例的名称。 |
|ResourceGroupId|String|rg-acfm2iu4fnc\*\*\*\*|QoS策略实例所属的资源组ID。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=DescribeQoses
&RegionId=cn-shanghai
&QosIds=qos-oek3r2cmvk7m8q****
&QosName=zxtest
&PageSize=10
&PageNumber=1
&公共请求参数
```

正常返回示例

`XML`格式

```
HTTP/1.1 200 OK
Content-Type:application/xml

<DescribeQosesResponse>
    <TotalCount>1</TotalCount>
    <PageSize>10</PageSize>
    <RequestId>2B5F35DD-0D66-41FC-AA99-BAE473E1A7A2</RequestId>
    <PageNumber>1</PageNumber>
    <Qoses>
        <Qos>
            <SagCount>0</SagCount>
            <ResourceGroupId>rg-acfm2iu4fnc****</ResourceGroupId>
            <QosId>qos-oek3r2cmvk7m8q****</QosId>
            <QosName>zxtest</QosName>
        </Qos>
    </Qoses>
</DescribeQosesResponse>
```

`JSON`格式

```
HTTP/1.1 200 OK
Content-Type:application/json

{
  "TotalCount" : 1,
  "PageSize" : 10,
  "RequestId" : "2B5F35DD-0D66-41FC-AA99-BAE473E1A7A2",
  "PageNumber" : 1,
  "Qoses" : {
    "Qos" : [ {
      "SagCount" : 0,
      "ResourceGroupId" : "rg-acfm2iu4fnc****",
      "QosId" : "qos-oek3r2cmvk7m8q****",
      "QosName" : "zxtest"
    } ]
  }
}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|InvalidParameter|The specified parameter is invalid.|非法参数。|
|403|MissingParameter|The input parameter is missing, please check your input.|输入参数缺失，请检查您的输入。|
|403|InternalError|An internal server error occurred.|内部服务错误。|

访问[错误中心](https://error-center.alibabacloud.com/status/product/Smartag)查看更多错误码。

