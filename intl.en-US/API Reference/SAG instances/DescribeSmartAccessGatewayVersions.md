# DescribeSmartAccessGatewayVersions

Queries the version of a Smart Access Gateway \(SAG\) instance.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=DescribeSmartAccessGatewayVersions&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|DescribeSmartAccessGatewayVersions|The operation that you want to perform.

 Set the value to **DescribeSmartAccessGatewayVersions**. |
|RegionId|String|Yes|cn-hangzhou|The ID of the region where the SAG instance is deployed. |
|SmartAGId|String|Yes|sag-d3m51apgw4po5\*\*\*\*\*|The ID of the SAG instance. |
|SmartAGSn|String|No|sage62x022502\*\*\*\*|The serial number of the SAG device. |
|VersionType|String|No|Device|The type of software run by the SAG device. Valid values:

 -   **Device**: The operating system run by the SAG device. This is the default value.
-   **Dpi**: The signature database used by the SAG device. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|765AB188-69BF-47C6-BEDD-B9FC72BFBB0|The ID of the request. |
|SmartAGVersions|Array of SmartAGVersion| |The information about the version of the SAG instance. |
|SmartAGVersion| | | |
|CreateTime|Long|1522744623000|The timestamp when the version was released. |
|Type|String|release|The type of the version. Valid values:

 -   **beta**: a preview version.
-   **release**: an officially released version. |
|VersionCode|String|1.0|The version number. |
|VersionName|String|testpackage1|The name of the version. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=DescribeSmartAccessGatewayVersions
&RegionId=cn-hangzhou
&SmartAGId=sag-d3m51apgw4po5*****
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeSmartAccessGatewayVersionsResponse>
    <SmartAGVersions>
          <SmartAGVersion>
                <Type>release</Type>
                <CreateTime>1522744623000</CreateTime>
                <VersionCode>1.0</VersionCode>
                <VersionName>testpackage1</VersionName>
          </SmartAGVersion>
    </SmartAGVersions>
    <RequestId>765AB188-69BF-47C6-BEDD-B9FC72BFBB00</RequestId>
</DescribeSmartAccessGatewayVersionsResponse>
```

`JSON` format

```
{
"SmartAGVersions": {
"SmartAGVersion": [
{
"Type": "release",
"CreateTime": 1522744623000,
"VersionCode": "1.0",
"VersionName": "testpackage1"
}
]
},
"RequestId": "765AB188-69BF-47C6-BEDD-B9FC72BFBB00"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|403|Forbidden|User not authorized to operate on the specified resource.|The error message returned because you do not have the permissions to manage the specified resource.|
|400|VersionNotExist|The specified version does not exist.|The error message returned because the specified version does not exist.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

