# DescribeSagRemoteAccess

Queries remote logon information about a Smart Access Gateway \(SAG\) device.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=DescribeSagRemoteAccess&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|DescribeSagRemoteAccess|The operation that you want to perform.

 Set the value to **DescribeSagRemoteAccess**. |
|RegionId|String|Yes|cn-shanghai|The ID of the region where the SAG instance is deployed. |
|SerialNumber|String|Yes|sage62x022502\*\*\*\*|The serial number of the SAG device. |
|SmartAGId|String|Yes|sag-1um5x5nwhilymw\*\*\*\*|The ID of the SAG instance. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Code|String|200|The error code. The 200 error code indicates that the query task is successful. |
|Message|String|successful|The error message. The Successful error message indicates that the query task is successful. |
|RemoteAccesses|Array of RemoteAccess| |Remote logon information about the SAG device. |
|RemoteAccess| | | |
|RemoteAccessIp|String|192.XX.XX.1|The private IP address where the remote logon is initiated. |
|SerialNumber|String|sage62x022502\*\*\*\*|The serial number of the SAG device. |
|RequestId|String|E38E950D-28A4-4C41-9428-A8908EC6AE5C|The ID of the request. |
|SmartAGId|String|sag-1um5x5nwhilymw\*\*\*\*|The ID of the SAG instance. |
|Success|Boolean|true|Indicates whether the query task is successful. Valid values:

 -   **true**: The query task is successful.
-   **false**: The query task failed. |

## Examples

Sample request

```
http(s)://[Endpoint]/? Action=DescribeSagRemoteAccess
&RegionId=cn-shanghai
&SerialNumber=sage62x022502****
&SmartAGId=sag-1um5x5nwhilymw****
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeSagRemoteAccessResponse>
  <SmartAGId>sag-kxe2cv7hot7qrv****</SmartAGId>
  <RemoteAccesses>
        <RemoteAccess>
              <RemoteAccessIp></RemoteAccessIp>
              <SerialNumber>sage62x022502****</SerialNumber>
        </RemoteAccess>
  </RemoteAccesses>
  <Message>successful</Message>
  <RequestId>2E2A56D0-D2BD-4D0B-9314-D355A5C67EBA</RequestId>
  <Success>true</Success>
  <Code>200</Code>
</DescribeSagRemoteAccessResponse>
```

`JSON` format

```
{
	"SmartAGId": "sag-kxe2cv7hot7qrv****",
	"RemoteAccesses": {
		"RemoteAccess": [
			{
				"RemoteAccessIp": "",
				"SerialNumber": "sage62x022502****"
			}
		]
	},
	"Message": "successful",
	"RequestId": "2E2A56D0-D2BD-4D0B-9314-D355A5C67EBA",
	"Success": true,
	"Code": "200"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|InstanceNotExit|The specified instance does not exist.|The error message returned because the specified SAG instance does not exist.|
|400|InvalidId.SN|The specified smart access gateway serial number does not exist.|The error message returned because the specified serial number does not exist.|
|500|InternalError|An error occurred while processing your request.|The error message returned because an unknown error occurred.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

