# DescribeDeviceAutoUpgradePolicy

Queries automatic update policies of Smart Access Gateway \(SAG\) devices.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=DescribeDeviceAutoUpgradePolicy&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|DescribeDeviceAutoUpgradePolicy|The operation that you want to perform.

 Set the value to **DescribeDeviceAutoUpgradePolicy**. |
|RegionId|String|Yes|cn-shanghai|The ID of the region where the SAG instance is deployed. |
|SerialNumber|String|Yes|sage62x022502\*\*\*\*|The serial number \(SN\) of the SAG device. |
|SmartAGId|String|Yes|sag-1um5x5nwhilymw\*\*\*\*|The ID of the SAG instance. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|CronExpression|String|0 0 4 1/1 \* ?|The time when upgrades start. The time is returned in the cron expression.

 For example, `0 0 4 1/1 * ?` indicates that upgrades start at 4:00 on the first day of each month. |
|Duration|String|60|The time period of upgrade. Valid values: **30 to 120**.

 Unit: minute. |
|RequestId|String|E38E950D-28A4-4C41-9428-A8908EC6AE5C|The ID of the request. |
|SerialNumber|String|sage62x022502\*\*\*\*|The serial number \(SN\) of the SAG device. |
|SmartAGId|String|sag-1um5x5nwhilymw\*\*\*\*|The ID of the SAG instance. |
|TimeZone|String|Asia/Shanghai|The time zone. |
|UpgradeType|String|scheduled|The upgrade type. Valid values:

 -   **scheduled** : scheduled upgrade.
-   **boot**: automatic upgrade upon device starting.
-   **manual**: manual upgrade. |

## Examples

Sample request

```
http(s)://[Endpoint]/? Action=DescribeDeviceAutoUpgradePolicy
&RegionId=cn-shanghai
&SerialNumber=sage62x022502****
&SmartAGId=sag-1um5x5nwhilymw****
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeDeviceAutoUpgradePolicyResponse>
  <SerialNumber>sage62x022502****</SerialNumber>
  <SmartAGId>sag-kxe2cv7hot7qrv****</SmartAGId>
  <UpgradeType>scheduled</UpgradeType>
  <Duration>60</Duration>
  <RequestId>0E20FBB8-BCFC-4F5E-BD94-77FF6A2133D0</RequestId>
  <CronExpression>0 0 4 1/1 * ? </CronExpression>
  <TimeZone>Asia/Shanghai</TimeZone>
</DescribeDeviceAutoUpgradePolicyResponse>
```

`JSON` format

```
{
	"SerialNumber": "sage62x022502****",
	"SmartAGId": "sag-kxe2cv7hot7qrv****",
	"UpgradeType": "scheduled",
	"Duration": 60,
	"RequestId": "0E20FBB8-BCFC-4F5E-BD94-77FF6A2133D0",
	"CronExpression": "0 0 4 1/1 * ?",
	"TimeZone": "Asia/Shanghai"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

