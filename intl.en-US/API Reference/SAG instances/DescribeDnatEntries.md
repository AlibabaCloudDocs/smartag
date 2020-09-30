# DescribeDnatEntries

You can call this operation to query DNAT entries associated with a Smart Access Gateway \(SAG\) instance.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=DescribeDnatEntries&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|DescribeDnatEntries|The operation that you want to perform.

 Set the value to **DescribeDnatEntries**. |
|RegionId|String|Yes|cn-hangzhou|The ID of the region where the SAG instance is deployed. |
|SagId|String|Yes|sag-djgd\*\*\*\*\*\*\*\*\*\*\*\*\*|The ID of the SAG instance.

 **Note:** Only SAG instances used to manage SAG devices supported DNAT. |
|Type|String|No|Intranet|The type of the DNAT entry. Valid values:

 -   **Intranet**: the default value. Translates the destination IP address to a specific internal IP address.
-   **Internet**: translates the destination IP address to a specific public IP address. |
|PageSize|Integer|No|12|The number of entries to return on each page. Default value: **10**. Maximum value: **50**. |
|PageNumber|Integer|No|1|The number of the page to return. Default value: **1**. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|635640CA-2335-4856-A9CB-1CB5C444DC5A|The ID of the request. |
|TotalCount|Integer|50|The total number of entries returned. |
|PageNumber|Integer|12|The page number of the returned page. Default value: **1**. |
|PageSize|Integer|1|The number of entries returned per page. Default value: **10**. Maximum value: **50**. |
|DnatEntries|Array| |The list of DNAT entries. |
|DnatEntryId|String|fwd-kxe4fq3xuzczze\*\*\*\*|The ID of the DNAT entry. |
|Type|String|Intranet|The type of the DNAT entry. Valid values:

 -   **Intranet**: the default value. Translates the destination IP address to a specific internal IP address.
-   **Internet**: translates the destination IP address to a specific public IP address. |
|SagId|String|sag-jfh\*\*\*\*\*\*\*\*|The ID of the SAG instance. |
|ExternalIp|String|10.10.\*\*. \*\*|The public IP address. |
|ExternalPort|String|12|The Internet-facing port.

 Valid values: **1 to 65535**. |
|InternalIp|String|192.168.0.1|The IP address of the private network for which packets are destined. |
|IpProtocol|String|tcp|The protocol used in DNAT. Valid values:

 -   tcp: forwards TCP packets.
-   udp: forwards UDP packets.
-   any: forwards packets of all protocols. |
|InternalPort|String|80|The port number of the private network for which packets are destined.

 Valid values: **1 to 65535**. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=DescribeDnatEntries
&RegionId=cn-hangzhou
&SagId=sag-djgd*************
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeDnatEntriesResponse>
      <DnatEntries></DnatEntries>
	  <PageNumber>1</PageNumber>
	  <PageSize>10</PageSize>
	  <RequestId>635640CA-2335-4856-A9CB-1CB5C444DC5A</RequestId>
	  <TotalCount>0</TotalCount>
    </DescribeDnatEntriesResponse>
```

`JSON` format

```
{
"DnatEntries":{
"DnatEntry":[]
},
"PageNumber":1,
"PageSize":10,
"RequestId":"635640CA-2335-4856-A9CB-1CB5C444DC5A",
"TotalCount":0
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|403|Forbidden|User not authorized to operate on the specified resource.|The error message returned because you do not have the permission to manage the specified resource.|
|403|MissingParameter|The input parameter is missing, please check your input.|The error message returned because a required parameter is not set. Check whether you have set all required parameters.|
|403|InvalidParameter|The specified parameter is invalid.|The error message returned because a specified parameter is invalid.|
|403|InternalError|An internal server error occurred.|The error message returned because an internal error occurred.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

