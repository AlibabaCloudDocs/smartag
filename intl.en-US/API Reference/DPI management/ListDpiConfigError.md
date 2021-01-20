# ListDpiConfigError

Queries configuration errors of the deep packet inspection feature \(DPI\).

## Background information

If you have configured an application-aware access control list \(ACL\) or a quality of service \(QoS\) policy and associated it with a Smart Access Gateway \(SAG\) instance, you can call this operation to query whether the ACL rules or 5-tuples in the QoS policy are applied to the SAG instance. If settings are not applied to the SAG instance, the error information is returned.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=ListDpiConfigError&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|ListDpiConfigError|The operation that you want to perform.

 Set the value to **ListDpiConfigError**. |
|DpiConfigType|String|Yes|qos|The type of instance for which the DPI feature is configured. Valid values:

 -   **acl**: ACL
-   **qos**: QoS policy |
|RegionId|String|Yes|cn-shanghai|The ID of the region where the SAG instance is deployed. |
|SmartAGId|String|Yes|sag-1e8sgws6b133b8\*\*\*\*|The ID of the SAG instance. |
|RuleInstanceId|String|No|qos-1strcafl4wghpb\*\*\*\*|The ID of the instance for which the DPI feature is configured. |
|NextToken|String|No|caeba0bbb2be03f84eb48b699f0a\*\*\*\*|The token used to query the next page. |
|MaxResults|Integer|No|10|The maximum number of entries to return on each page.

 Valid values: **1** to **100**.

 Default value: **10**. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|DpiConfigError|Array of DpiConfigError| |The information about the configuration errors. |
|ErrorType|String|DeviceNotSupported|The type of the configuration error. Valid values:

 -   **DeviceNotSupported**: The SAG device does not support the DPI feature.
-   **VersionNotSupported**: The version of the DPI feature is outdated.
-   **NotEnable**: The DPI feature is disabled on the SAG device. |
|RuleConfigErrorList|Array of RuleConfigErrorList| |The information about the DPI configuration errors. |
|DpiGroupIds|List|1|The IDs of the application groups that have configuration errors.

 You can call the [ListDpiGroups](~~196754~~) operation to query application IDs and information. |
|DpiSignatureIds|List|1|The IDs of applications that have configuration errors.

 You can call the [ListDpiSignatures](~~196630~~) operation to query application IDs and information. |
|RuleId|String|qospy-axud4s62gz632b\*\*\*\*|The IDs of rules that are applied to applications with configuration errors.

 -   If you make the request to query configuration errors of ACLs, the IDs of ACL rules that have configuration errors are returned.
-   If you make the request to query configuration errors of QoS polices, the IDs of the 5-tuples in the QoS polices that have configuration errors are returned. |
|SN|String|sag-2160808\*\*\*\*|The serial number \(SN\) of the SAG device. |
|SmartAGId|String|sag-1e8sgws6b133b8\*\*\*\*|The ID of the SAG instance. |
|MaxResults|Integer|10|The maximum number of entries returned per page. |
|NextToken|String|caeba0bbb2be03f84eb48b699f0a\*\*\*\*|The token returned for the next page. |
|RequestId|String|F47B5293-27B6-48EF-A9C6-E90A41449813|The ID of the request. |
|Total|Integer|1|The total number of entries returned. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=ListDpiConfigError
&DpiConfigType=qos
&RegionId=cn-shanghai
&SmartAGId=sag-1e8sgws6b133b8****
&<Common request parameters>
```

Sample success responses

`XML` format

```
<ListDpiConfigErrorResponse>
  <RequestId>27A5B768-4366-4EF3-9524-7FD51331B1DC</RequestId>
  <Total>1</Total>
  <MaxResults>10</MaxResults>
  <DpiConfigError>
        <ErrorType>DeviceNotSupported</ErrorType>
        <RuleConfigErrorList>
              <RuleId>qospy-axud4s62gz632b****</RuleId>
              <DpiGroupIds>1</DpiGroupIds>
        </RuleConfigErrorList>
        <SN>sage62x0526****</SN>
        <SmartAGId>sag-4d6i45zess8nj4****</SmartAGId>
  </DpiConfigError>
</ListDpiConfigErrorResponse>
```

`JSON` format

```
{
	"RequestId": "27A5B768-4366-4EF3-9524-7FD51331B1DC",
	"Total": 1,
	"MaxResults": 10,
	"DpiConfigError": [
		{
			"ErrorType": "DeviceNotSupported",
			"RuleConfigErrorList": [
				{
					"DpiSignatureIds": [],
					"RuleId": "qospy-axud4s62gz632b****",
					"DpiGroupIds": [
						"1"
					]
				}
			],
			"SN": "sage62x0526****",
			"SmartAGId": "sag-4d6i45zess8nj4****"
		}
	]
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

