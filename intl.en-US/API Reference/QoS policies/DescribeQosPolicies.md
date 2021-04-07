# DescribeQosPolicies

Queries quality of service \(QoS\) rules that contain 5-tuples.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=DescribeQosPolicies&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|DescribeQosPolicies|The operation that you want to perform.

Set the value to **DescribeQosPolicies**. |
|QosId|String|Yes|qos-jdj\*\*\*\*\*\*\*\*\*\*\*\*|The ID of the QoS policy. |
|RegionId|String|Yes|cn-hangzhou|The ID of the region where the QoS policy is deployed. |
|QosPolicyId|String|No|qospy-xhwhyuo43l\*\*\*\*\*\*\*\*|The ID of the 5-tuple. |
|Description|String|No|docdesc|The description of the 5-tuple.

The description must be 1 to 512 characters in length, and can contain digits, underscores \(\_\), and hyphens \(-\). It must start with a letter. |
|PageSize|Integer|No|2|The number of entries to return on each page.

Default value: **10**. Maximum value: **50**. |
|PageNumber|Integer|No|2|The number of the page to return.

Default value: **1**. |
|Priority|Integer|No|1|The priority of the traffic throttling rule that is applied to the 5-tuple. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|PageNumber|Integer|2|The page number of the returned page. |
|PageSize|Integer|2|The number of entries returned per page. |
|QosPolicies|Array of QosPolicy| |The details about the 5-tuple. |
|QosPolicy| | | |
|Description|String|docdesc|The description of the 5-tuple. |
|DestCidr|String|10.10.10.0/24|The destination CIDR block. |
|DestPortRange|String|90/90|The range of the destination ports. |
|DpiGroupIds|List|20|The IDs of application groups.

You can call the [ListDpiGroups](~~196754~~) operation to query application group IDs and information. |
|DpiSignatureIds|List|1|The IDs of applications.

You can call the [ListDpiSignatures](~~196630~~) operation to query application IDs and information. |
|EndTime|String|2019-07-14T16:41:33+0800|The time when the 5-tuple stops taking effect. |
|IpProtocol|String|TCP|The type of the protocol that is applied to the 5-tuple. |
|Name|String|test|The name of the 5-tuple. |
|Priority|Integer|3|The priority of the traffic throttling rule that is applied to the 5-tuple. |
|QosId|String|qos-dw\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*|The ID of the QoS policy. |
|QosPolicyId|String|qospy-xhwhyuo43l\*\*\*\*\*\*\*\*|The ID of the 5-tuple. |
|SourceCidr|String|10.0.0.0/24|The source CIDR block. |
|SourcePortRange|String|80/80|The range of the source ports. |
|StartTime|String|2019-07-14T16:41:33+0800|The time when the 5-tuple starts to take effect. |
|RequestId|String|97862812-2C7E-4D25-B0D5-B26DAC7FA293|The ID of the request. |
|TotalCount|Integer|2|The total number of entries returned. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=DescribeQosPolicies
&QosId=qos-jdj************
&RegionId=cn-hangzhou
&<Common request parameters>
```

Sample success responses

`XML` fomat

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

`JSON` format

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

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|403|MissingParameter|The input parameter is missing, please check your input.|The error message returned because one or more required parameters are not set. Check whether you have set all required parameters.|
|403|InvalidParameter|The specified parameter is invalid.|The error message returned because the specified parameter is set to an invalid value.|
|400|InvalidId.Qos|The specified QosId is invalid.|The error message returned because the specified ID \(QosId\) of the QoS policy parameter is invalid.|
|403|InternalError|An internal server error occurred.|The error message returned because an internal server error occurred.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

