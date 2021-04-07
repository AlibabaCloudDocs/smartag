# DescribeQosPolicies

调用DescribeQosPolicies查询QoS策略五元组规则配置信息。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=DescribeQosPolicies&type=RPC&version=2018-03-13)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|DescribeQosPolicies|要执行的操作。

 取值：**DescribeQosPolicies**。 |
|QosId|String|是|qos-jdj\*\*\*\*\*\*\*\*\*\*\*\*|QoS策略的实例ID。 |
|RegionId|String|是|cn-hangzhou|QoS策略实例所属的地域ID。 |
|QosPolicyId|String|否|qospy-xhwhyuo43l\*\*\*\*\*\*\*\*|QoS策略五元组规则的实例ID。 |
|Description|String|否|docdesc|QoS策略五元组规则实例的描述。

 长度为1~512个字符，以大小写字母或中文开头，可包含数字、下划线（\_）和短划线（-）。 |
|PageSize|Integer|否|2|分页查询时每页展示的五元组规则条目数。

 默认值为**10**，最大值为**50**。 |
|PageNumber|Integer|否|2|分页查询时的页码。

 默认值为**1**。 |
|Priority|Integer|否|1|QoS策略五元组规则所属的限速规则的优先级。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|PageNumber|Integer|2|分页查询时的页码。 |
|PageSize|Integer|2|分页查询时每页展示的五元组规则条目数。 |
|QosPolicies|Array of QosPolicy| |QoS策略五元组规则配置信息列表。 |
|QosPolicy| | | |
|Description|String|docdesc|QoS策略五元组规则描述。 |
|DestCidr|String|10.10.10.0/24|目的网段。 |
|DestPortRange|String|90/90|目的端口范围。 |
|DpiGroupIds|List|20|应用组ID列表。

 您可以通过[ListDpiGroups](~~196754~~)查询应用组ID及其包含的应用信息。 |
|DpiSignatureIds|List|1|应用ID列表。

 您可以通过[ListDpiSignatures](~~196630~~)查询应用ID及其对应的应用信息。 |
|EndTime|String|2019-07-14T16:41:33+0800|QoS策略五元组规则生效结束时间。 |
|IpProtocol|String|TCP|QoS策略五元组规则应用的协议类型。 |
|Name|String|test|QoS策略五元组规则名称。 |
|Priority|Integer|3|QoS策略五元组规则所属的限速规则的优先级。 |
|QosId|String|qos-dw\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*|QoS策略的实例ID。 |
|QosPolicyId|String|qospy-xhwhyuo43l\*\*\*\*\*\*\*\*|QoS策略五元组规则的实例ID。 |
|SourceCidr|String|10.0.0.0/24|源网段。 |
|SourcePortRange|String|80/80|源端口范围。 |
|StartTime|String|2019-07-14T16:41:33+0800|QoS策略五元组规则生效开始时间。 |
|RequestId|String|97862812-2C7E-4D25-B0D5-B26DAC7FA293|请求ID。 |
|TotalCount|Integer|2|当前符合查询条件的QoS策略五元组规则条目总数。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=DescribeQosPolicies
&QosId=qos-jdj************
&RegionId=cn-hangzhou
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<DescribeQosPoliciesResponse>
  <PageNumber>1</PageNumber>
  <PageSize>10</PageSize>
  <QosPolicies>
        <QosPolicy>
              <Description>bvt-test</Description>
              <DestCidr>10.10.0.0/24</DestCidr>
              <DestPortRange>-1/-1</DestPortRange>
              <IpProtocol>ALL</IpProtocol>
              <Priority>1</Priority>
              <QosId>qos-awfxl1adxeqyk*****</QosId>
              <QosPolicyId>qospy-7h91hp3h9ykd*****</QosPolicyId>
              <SourceCidr>192.168.0.0/24</SourceCidr>
              <SourcePortRange>-1/-1</SourcePortRange>
        </QosPolicy>
        <QosPolicy>
              <Description>bvt-test</Description>
              <DestCidr>10.10.2.0/24</DestCidr>
              <DestPortRange>80/80</DestPortRange>
              <IpProtocol>TCP</IpProtocol>
              <Priority>3</Priority>
              <QosId>qos-awfxl1adxeqy*****</QosId>
              <QosPolicyId>qospy-3avavlksll******</QosPolicyId>
              <SourceCidr>192.168.2.0/24</SourceCidr>
              <SourcePortRange>1/65535</SourcePortRange>
        </QosPolicy>
  </QosPolicies>
  <RequestId>A6B0BBEC-3101-4A98-9805-368B04956C02</RequestId>
  <TotalCount>2</TotalCount>
</DescribeQosPoliciesResponse>
```

`JSON` 格式

```
{
    "PageNumber":1,
    "PageSize":10,
    "QosPolicies":{
        "QosPolicy":[
            {
                "Description":"bvt-test",
                "DestCidr":"10.10.0.0/24",
                "DestPortRange":"-1/-1",
                "IpProtocol":"ALL",
                "Priority":1,
                "QosId":"qos-awfxl1adxeqyk*****",
                "QosPolicyId":"qospy-7h91hp3h9ykd*****",
                "SourceCidr":"192.168.0.0/24",
                "SourcePortRange":"-1/-1"
            },
            {
                "Description":"bvt-test",
                "DestCidr":"10.10.2.0/24",
                "DestPortRange":"80/80",
                "IpProtocol":"TCP",
                "Priority":3,
                "QosId":"qos-awfxl1adxeqy*****",
                "QosPolicyId":"qospy-3avavlksll******",
                "SourceCidr":"192.168.2.0/24",
                "SourcePortRange":"1/65535"
            }
        ]
    },
    "RequestId":"A6B0BBEC-3101-4A98-9805-368B04956C02",
    "TotalCount":2
}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|MissingParameter|The input parameter is missing, please check your input.|输入参数缺失，请检查您的输入。|
|403|InvalidParameter|The specified parameter is invalid.|非法参数。|
|400|InvalidId.Qos|The specified QosId is invalid.|您输入的参数"QosId"不合法。|
|403|InternalError|An internal server error occurred.|内部服务错误|

访问[错误中心](https://error-center.alibabacloud.com/status/product/Smartag)查看更多错误码。

