# CreateQosPolicy

Adds a quality of service \(QoS\) rule that contains 5-tuples to a QoS policy.

## Prerequisites

Make sure that a traffic throttling rule is created before you call this operation. For more information, see [CreateQosCar](~~131806~~).

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=CreateQosPolicy&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|CreateQosPolicy|The operation that you want to perform.

 Set the value to **CreateQosPolicy**. |
|DestCidr|String|Yes|10.10.20.0/24|The range of the destination IP addresses.

 Set this parameter in CIDR notation. Example: 192.168.10.0/24. |
|DestPortRange|String|Yes|80/80|The range of the destination ports.

 Valid values: **-1** and **1** to **65535**.

 Set this parameter in one of the following formats:

 -   1/200, which indicates a port range from 1 to 200.
-   80/80, which indicates port 80.
-   A value of -1/-1 indicates that all ports are available. |
|IpProtocol|String|Yes|TCP|The type of the protocol that is applied to the 5-tuple.

 The supported protocols provided in this topic are for reference only. The actual protocols in the console shall prevail. |
|Priority|Integer|Yes|3|The priority of the traffic throttling rule which is applied to the 5-tuple.

 If rules have the same priority, whichever applied to the SAG devices earlier takes effect. |
|QosId|String|Yes|qos-dhf\*\*\*\*\*\*\*\*\*\*\*|The ID of the QoS policy. |
|RegionId|String|Yes|cn-hangzhou|The ID of the region where the QoS policy is deployed. |
|SourceCidr|String|Yes|10.10.10.0/24|The range of the source IP addresses.

 Set this parameter in CIDR notation. Example: 192.168.1.0/24. |
|SourcePortRange|String|Yes|80/80|The range of the source ports.

 Valid values: **-1** and **1** to **65535**.

 Set this parameter in one of the following formats:

 -   1/200, which indicates a port range from 1 to 200.
-   80/80, which indicates port 80.
-   A value of -1/-1 indicates that all ports are available. |
|Description|String|No|test|The description of the 5-tuple.

 The description must be 1 to 512 characters in length, and can contain digits, underscores \(\_\), and hyphens \(-\). It must start with a letter. |
|StartTime|String|No|2019-07-14T16:41:33+0800|The time when the 5-tuple starts to take effect. |
|EndTime|String|No|2019-09-14T16:41:33+0800|The time when the 5-tuple stops taking effect. |
|Name|String|No|nametest|The name of the 5-tuple.

 The name must be 2 to 100 characters in length, and can contain digits, hyphens \(-\), and underscores \(\_\). It must start with a letter. |
|DpiSignatureIds.N|RepeatList|No|1|The IDs of application groups.

 You can call the [ListDpiGroups](~~196754~~) operation to query application group IDs and information. Maximum value of N: **10**. |
|DpiGroupIds.N|RepeatList|No|20|The IDs of applications.

 You can call the [ListDpiSignatures](~~196630~~) operation to query application IDs and information. Maximum value of N: **10**. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Description|String|bvt-test|The description of the 5-tuple. |
|DestCidr|String|10.10.10.0/24|The destination CIDR block. |
|DestPortRange|String|80/80|The range of the destination ports. |
|DpiGroupIds|List|20|The IDs of application groups.

 You can call the [ListDpiGroups](~~196754~~) operation to query application group IDs and information. |
|DpiSignatureIds|List|1|The IDs of applications.

 You can call the [ListDpiSignatures](~~196630~~) operation to query application IDs and information. |
|EndTime|String|2019-09-14T16:41:33+0800|The time when the 5-tuple stops taking effect. |
|IpProtocol|String|TCP|The type of the protocol that is applied to the 5-tuple. |
|Name|String|nametest|The name of the 5-tuple. |
|Priority|Integer|3|The priority of the traffic throttling rule that is applied to the 5-tuple. |
|QosId|String|qos-xhwhyuo43l\*\*\*\*\*\*\*\*|The ID of the QoS policy. |
|QosPolicyId|String|qospy-xhwhyuo43l\*\*\*\*\*\*\*\*|The ID of the 5-tuple. |
|RequestId|String|97862812-2C7E-4D25-B0D5-B26DAC7FA293|The ID of the request. |
|SourceCidr|String|10.10.10.0/24|The source CIDR block. |
|SourcePortRange|String|80/80|The range of the source ports. |
|StartTime|String|2019-07-14T16:41:33+0800|The time when the 5-tuple starts to take effect. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=CreateQosPolicy
&DestCidr=10.10.20.0/24
&DestPortRange=80/80
&IpProtocol=TCP
&Priority=3
&QosId=qos-dhf***********
&RegionId=cn-hangzhou
&SourceCidr=10.10.10.0/24
&SourcePortRange=80/80
&<Common request parameters>
```

Sample success responses

`XML` fomat

```
<CreateQosPolicyResponse>
  <Description>bvt-test</Description>
  <DestCidr>10.10.0.0/24</DestCidr>
  <DestPortRange>-1/-1</DestPortRange>
  <EndTime>2019-09-14T16:41:33+0800</EndTime>
  <IpProtocol>ALL</IpProtocol>
  <Priority>1</Priority>
  <QosId>qos-awfxl1adxeqykl****</QosId>
  <QosPolicyId>qospy-427m9fo6wkhofs1****</QosPolicyId>
  <RequestId>97862812-2C7E-4D25-B0D5-B26DAC7FA293</RequestId>
  <SourceCidr>192.168.0.0/24</SourceCidr>
  <SourcePortRange>-1/-1</SourcePortRange>
  <StartTime>2019-07-14T16:41:33+0800</StartTime>
</CreateQosPolicyResponse>
```

`JSON` format

```
{
    "Description":"bvt-test",
    "DestCidr":"10.10.0.0/24",
    "DestPortRange":"-1/-1",
    "EndTime":"2019-09-14T16:41:33+0800",
    "IpProtocol":"ALL",
    "Priority":1,
    "QosId":"qos-awfxl1adxeqykl****",
    "QosPolicyId":"qospy-427m9fo6wkhofs1****",
    "RequestId":"97862812-2C7E-4D25-B0D5-B26DAC7FA293",
    "SourceCidr":"192.168.0.0/24",
    "SourcePortRange":"-1/-1",
    "StartTime":"2019-07-14T16:41:33+0800"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|403|InternalError|An internal server error occurred.|The error message returned because an internal server error occurred.|
|400|NotSupportedProtocol|The specified protocol of the QoS policy is not supported.|The error message returned because the 5-tuple does not support the specified protocol.|
|403|InvalidPortRange|The specified port range is invalid.|The error message returned because the specified port range is invalid.|
|400|InvalidId.Qos|The specified QosId is invalid.|The error message returned because the specified ID \(QosId\) of the QoS policy parameter is invalid.|
|400|QosPyPerQosPyPerQosAmountLimitQosAmountLimit|The maximum number of policies in a QoS is exceeded. You can submit a ticket to increase the quota.|The error message returned because the number of 5-tuples that you have added to the QoS policy has reached the upper limit. You can submit a ticket to request a quota increase.|
|400|MissParameter.RegionId|You must specify RegionId.|The error message returned because the ID \(RegionId\) of the region is not specified.|
|400|MissParameter.QosId|You must specify QosId.|The error message returned because the ID \(QosId\) of the QoS policy is not specified.|
|400|MissParameter.QosPolicyId|You must specify QosPolicyId.|The error message returned because the ID \(QosPolicyId\) of the 5-tuple is not specified.|
|400|InvalidParameter.Priority|The specified Priority is invalid.|The error message returned because the specified priority \(Priority\) of the 5-tuple is invalid.|
|400|MissParameter.SourceCidr|You must specify SourceCidr.|The error message returned because the source CIDR block \(SourceCidr\) is not specified.|
|400|MissParameter.SourcePortRange|You must specify SourcePortRange.|The error message returned because the source port range \(SourceRange\) is not specified.|
|400|MissParameter.DestCidr|You must specify DestCidr.|The error message returned because the destination CIDR block \(DestCidr\) is not specified.|
|400|MissParameter.DestPortRange|You must specify DestPortRange.|The error message returned because the destination port range \(DestPortRange\) is not specified.|
|400|MissParameter.IpProtocol|You must specify IpProtocol.|The error message returned because the transport layer protocol \(IpProtocol\) is not specified.|
|400|InvalidParameter.Description|The specified Description is invalid.|The error message returned because the specified description \(Description\) of the traffic throttling policy is invalid.|
|400|InvalidParameter.DestCidr|The specified DestCidr is invalid.|The error message returned because the specified destination CIDR block \(DestCidr\) is invalid.|
|400|InvalidParameter.DestPortRange|The specified DestPortRange is invalid.|The error message returned because the specified destination port range \(DestPortRange\) is invalid.|
|400|InvalidParameter.SourceCidr|The specified SourceCidr is invalid.|The error message returned because the specified source CIDR block \(SourceCidr\) is invalid.|
|400|InvalidParameter.SourcePortRange|The specified SourcePortRange is invalid.|The error message returned because the specified source port range \(SourcePortRange\) is invalid.|
|400|InvalidParameter.StartTime|The specified StartTime is invalid.|The error message returned because the specified time \(StartTime\) when the 5-tuple takes effect is invalid.|
|400|InvalidParameter.EndTime|The specified EndTime is invalid.|The error message returned because the specified time \(EndTime\) when the 5-tuple expires is invalid.|
|400|InvalidTimeRangeCompare|The specified end time is earlier than the start time. Please check your input.|The error message returned because the specified end time is earlier than the start time. Check whether the parameters are correctly set.|
|400|InvalidParameter.Name|The specified Name is invalid.|The error message returned because the specified name \(Name\) of the traffic throttling policy is invalid.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

