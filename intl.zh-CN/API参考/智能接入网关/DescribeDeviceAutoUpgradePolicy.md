# DescribeDeviceAutoUpgradePolicy

调用DescribeDeviceAutoUpgradePolicy查看智能接入网关设备运行软件的升级策略。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=DescribeDeviceAutoUpgradePolicy&type=RPC&version=2018-03-13)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|DescribeDeviceAutoUpgradePolicy|要执行的操作。

 取值：**DescribeDeviceAutoUpgradePolicy**。 |
|RegionId|String|是|cn-shanghai|智能接入网关实例所属的地域ID。 |
|SerialNumber|String|是|sage62x022502\*\*\*\*|智能接入网关设备序列号。 |
|SmartAGId|String|是|sag-kxe2cv7hot7qrv\*\*\*\*|智能接入网关实例ID。 |
|VersionType|String|否|Device|要查看的软件类型：

 -   **Device**：表示智能接入网关设备运行的操作系统软件。
-   **Dpi**：表示智能接入网关设备运行的应用特征库软件。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|CronExpression|String|0 0 4 1/1 \* ?|升级开始时间。升级开始时间使用cron表达式。

 例如：`0 0 4 1/1 * ?`表示从每月第一天上午4时开始，每天执行升级操作。 |
|Duration|String|60|升级时间段。

 取值范围：**30~120**。

 单位：分钟。 |
|Jitter|String|5|升级时间的上下偏差。单位：分钟。 |
|RequestId|String|0E20FBB8-BCFC-4F5E-BD94-77FF6A2133D0|请求ID。 |
|SerialNumber|String|sage62x022502\*\*\*\*|智能接入网关设备序列号。 |
|SmartAGId|String|sag-kxe2cv7hot7qrv\*\*\*\*|智能接入网关实例ID。 |
|TimeZone|String|Asia/Shanghai|时区。 |
|UpgradeType|String|scheduled|升级类型。

 -   **scheduled**：定时升级。
-   **boot**：开机自动升级。
-   **manual**：手动升级。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=DescribeDeviceAutoUpgradePolicy
&RegionId=cn-shanghai
&SerialNumber=sage62x022502****
&SmartAGId=sag-1um5x5nwhilymw****
&<公共请求参数>
```

正常返回示例

`XML`格式

```
<DescribeDeviceAutoUpgradePolicyResponse>
  <SerialNumber>sage62x022502****</SerialNumber>
  <SmartAGId>sag-kxe2cv7hot7qrv****</SmartAGId>
  <UpgradeType>scheduled</UpgradeType>
  <Duration>60</Duration>
  <RequestId>0E20FBB8-BCFC-4F5E-BD94-77FF6A2133D0</RequestId>
  <CronExpression>0 0 4 1/1 * ?</CronExpression>
  <TimeZone>Asia/Shanghai</TimeZone>
</DescribeDeviceAutoUpgradePolicyResponse>
```

`JSON`格式

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

## 错误码

访问[错误中心](https://error-center.alibabacloud.com/status/product/Smartag)查看更多错误码。

