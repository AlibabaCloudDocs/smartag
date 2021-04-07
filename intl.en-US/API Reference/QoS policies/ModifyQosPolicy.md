# ModifyQosPolicy

Modifies the configuration of a quality of service \(QoS\) policy that contains 5-tuples.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=ModifyQosPolicy&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|ModifyQosPolicy|The operation that you want to perform.

 Set the value to **ModifyQosPolicy**. |
|QosId|String|Yes|qos-djhgg\*\*\*\*\*\*\*\*\*\*\*|The ID of the QoS policy. |
|QosPolicyId|String|Yes|qospy-427m9fo6wkh\*\*\*\*\*\*\*\*\*|The ID of the 5-tuple. |
|RegionId|String|Yes|cn-hangzhou|The ID of the region where the QoS policy is deployed. |
|Priority|Integer|No|3|The priority of the 5-tuple to which the traffic throttling policy is applied.

 Valid values: **1 to 3**. A smaller value indicates a higher priority. |
|SourceCidr|String|No|10.10.10.0/24|The range of the source IP addresses.

 Set this parameter in CIDR notation. Example: 192.168.1.0/24. |
|DestCidr|String|No|10.10.20.0/24|The range of the destination IP addresses.

 Set this parameter in CIDR notation. Example: 192.168.10.0/24. |
|IpProtocol|String|No|tcp|The type of the protocol that is applied to the 5-tuple.

 The supported protocols provided in this topic are for reference only. The actual supported protocols in the console shall prevail. |
|SourcePortRange|String|No|1/200|The range of the source ports.

 Valid values: **-1** and **1** to **65535**.

 Set the source port range in one of the following formats: 1/200 or 80/80. A value of -1/-1 indicates that all ports are available. |
|DestPortRange|String|No|300/400|The range of the destination ports.

 Valid values: **-1** and **1** to **65535**.

 Set the source port range in one of the following formats: 1/200 or 80/80. A value of -1/-1 indicates that all ports are available. |
|StartTime|String|No|2019-07-14T16:41:33+0800|The time when the 5-tuple starts to take effect. |
|EndTime|String|No|2019-09-14T16:41:33+0800|The time when the 5-tuple stops taking effect. |
|Description|String|No|docdesc|The description of the 5-tuple.

 The description must be 1 to 512 characters in length, and can contain digits, underscores \(\_\), and hyphens \(-\). It must start with a letter. |
|Name|String|No|doctest|The name of the 5-tuple.

 The name must be 2 to 100 characters in length, and can contain digits, hyphens \(-\), and underscores \(\_\). It must start with a letter. |
|DpiSignatureIds.N|RepeatList|No|1|The IDs of applications.

 You can call the [ListDpiSignatures](~~196630~~) operation to query application IDs and information. Maximum value of N: **10**. |
|DpiGroupIds.N|RepeatList|No|20|The IDs of application groups.

 You can call the [ListDpiGroups](~~196754~~) operation to query application group IDs and information. Maximum value of N: **10**. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|551CD836-9E46-4F2C-A167-B4363180A647|The ID of the request. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=ModifyQosPolicy
&QosId=qos-djhgg***********
&QosPolicyId=qospy-427m9fo6wkh*********
&RegionId=cn-hangzhou
&<Common request parameters>
```

Sample success responses

`XML` fomat

```
<ModifyQosPolicyRespon>
  <RequestId>551CD836-9E46-4F2C-A167-B4363180A647</RequestId>
</ModifyQosPolicyRespon>
```

`JSON` format

```
{
"RequestId":"551CD836-9E46-4F2C-A167-B4363180A647"
}
```

## Error codes

|HttpCode|Error code|Error message|Required|
|--------|----------|-------------|--------|
|400|MissParameter.RegionId|You must specify RegionId.|The error message returned because the ID \(RegionId\) of the region is not specified.|
|400|MissParameter.QosId|You must specify QosId.|The error message returned because the ID \(QosId\) of the QoS policy is not specified.|
|400|MissParameter.QosPolicyId|You must specify QosPolicyId.|The error message returned because the ID \(QosPolicyId\) of the QoS rule is not specified.|
|400|InvalidParameter.Description|The specified Description is invalid.|The error message returned because the specified description \(Description\) of the traffic throttling policy is invalid.|
|400|InvalidParameter.Priority|The specified Priority is invalid.|The error message returned because the specified priority \(Priority\) of the QoS rule is invalid.|
|400|InvalidParameter.SourcePortRange|The specified SourcePortRange is invalid.|The error message returned because the specified source port range \(SourcePortRange\) is invalid.|
|400|InvalidParameter.DestCidr|The specified DestCidr is invalid.|The error message returned because the specified destination CIDR block \(DestCidr\) is invalid.|
|400|InvalidParameter.DestPortRange|The specified DestPortRange is invalid.|The error message returned because the specified destination port range \(DestPortRange\) is invalid.|
|400|InvalidParameter.SourceCidr|The specified SourceCidr is invalid.|The error message returned because the specified source CIDR block \(SourceCidr\) is invalid.|
|400|InvalidParameter.StartTime|The specified StartTime is invalid.|The error message returned because the specified time \(StartTime\) when the QoS rule takes effect is invalid.|
|400|InvalidParameter.EndTime|The specified EndTime is invalid.|The error message returned because the specified time \(EndTime\) when the QoS rule expires is invalid.|
|400|InvalidTimeRangeCompare|The specified end time is earlier than the start time. Please check your input.|The error message returned because the specified end time is earlier than the start time. Check whether the parameters are correctly set.|
|400|InvalidId.QOSPY|The specified QosPolicyId is invalid.|The error message returned because the ID of the QoS rule specified in the QosPolicy parameter is invalid.|
|403|InternalError|An internal server error occurred.|The error code returned because an internal server error occurred.|
|400|InvalidId.Qos|The specified QosId is invalid.|The error message returned because the specified ID \(QosId\) of the QoS policy is invalid.|
|400|NotSupportedProtocol|The specified protocol of the QoS policy is not supported.|The error message returned because the specified transport layer protocol is not supported by the QoS rule.|
|403|InvalidPortRange|The specified port range is invalid.|The error code returned because the specified port range is invalid.|
|400|InvalidParameter.Name|The specified Name is invalid.|The error message returned because the specified name \(Name\) of the traffic throttling policy is invalid.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

