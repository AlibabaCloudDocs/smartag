# ModifyDeviceAutoUpgradePolicy

Modifies the automatic upgrade policy of a Smart Access Gateway \(SAG\) device.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=ModifyDeviceAutoUpgradePolicy&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|ModifyDeviceAutoUpgradePolicy|The operation that you want to perform.

 Set the value to **ModifyDeviceAutoUpgradePolicy**. |
|CronExpression|String|Yes|0 0 4 1/1 \* ?|The time when upgrades start. Valid values: Set the parameter in a cron expression.

 For example, `0 0 4 1/1 * ?` indicates that upgrades start at 04:00:00 \(UTC+8\) on the first day of each month. |
|Duration|Integer|Yes|30|The time period during which upgrades are performed. Valid values: **30 to 120**.

 Unit: minutes. |
|RegionId|String|Yes|cn-shanghai|The ID of the region where the SAG instance is deployed. |
|SerialNumber|String|Yes|sage62x022502\*\*\*\*|The serial number of the SAG device. |
|SmartAGId|String|Yes|sag-1um5x5nwhilymw\*\*\*\*|The ID of the SAG instance. |
|TimeZone|String|Yes|Asia/Shanghai|The time zone. |
|UpgradeType|String|Yes|scheduled|The upgrade type. Valid values:

 -   **scheduled**: scheduled upgrade.
-   **boot**: automatic upgrade upon device startup.
-   **manual**: manual upgrade. |
|VersionType|String|No|Device|The type of the software for which you want to modify the upgrade policy. Valid values:

 -   **Device**: The operating system run by the SAG device.
-   **Dpi**: The signature database used by the SAG device. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|F03C6897-2284-4BC8-94B4-1467BD992A2D|The ID of the request. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=ModifyDeviceAutoUpgradePolicy
&CronExpression=0 0 4 1/1 * ?
&Duration=30
&RegionId=cn-shanghai
&SerialNumber=sage62x022502****
&SmartAGId=sag-1um5x5nwhilymw****
&TimeZone=Asia/Shanghai
&UpgradeType=scheduled
&<Common request parameters>
```

Sample success responses

`XML` format

```
<ModifyDeviceAutoUpgradePolicyResponse>
  <RequestId>F03C6897-2284-4BC8-94B4-1467BD992A2D</RequestId>
</ModifyDeviceAutoUpgradePolicyResponse>
```

`JSON` format

```
{
	"RequestId": "F03C6897-2284-4BC8-94B4-1467BD992A2D"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|SAG.InstanceIdEmpty|You must specify the SAG instance ID.|The error message returned because the SAG instance ID is not specified.|
|400|SAG.InvalidSerialNumber|The specified SerialNumber is invalid.|The error message returned because the specified device serial number is invalid.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

