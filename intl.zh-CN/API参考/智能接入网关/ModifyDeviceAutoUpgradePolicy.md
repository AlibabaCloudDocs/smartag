# ModifyDeviceAutoUpgradePolicy

调用ModifyDeviceAutoUpgradePolicy修改智能接入网关设备软件的升级策略。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=ModifyDeviceAutoUpgradePolicy&type=RPC&version=2018-03-13)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|ModifyDeviceAutoUpgradePolicy|要执行的操作。

 取值：**ModifyDeviceAutoUpgradePolicy**。 |
|CronExpression|String|是|0 0 4 1/1 \* ?|升级开始时间。升级开始时间使用cron表达式。

 例如：`0 0 4 1/1 * ?`表示从每月第一天上午4时开始，每天的上午4时执行升级操作。 |
|Duration|Integer|是|30|升级时间段。取值范围：**30~120**。

 单位：分钟。 |
|RegionId|String|是|cn-shanghai|智能接入网关实例的地域ID。 |
|SerialNumber|String|是|sage62x022502\*\*\*\*|智能接入网关设备序列号。 |
|SmartAGId|String|是|sag-1um5x5nwhilymw\*\*\*\*|智能接入网关实例ID。 |
|TimeZone|String|是|Asia/Shanghai|时区。 |
|UpgradeType|String|是|scheduled|升级类型。取值：

 -   **scheduled**：定时升级。
-   **boot**：开机自动升级。
-   **manual**：手动升级。 |
|VersionType|String|否|Device|指定要修改升级策略的软件类型。取值：

 -   **Device**：表示智能接入网关设备运行的操作系统软件。
-   **Dpi**：表示智能接入网关设备运行的应用特征库软件。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|F03C6897-2284-4BC8-94B4-1467BD992A2D|请求ID。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=ModifyDeviceAutoUpgradePolicy
&CronExpression=0 0 4 1/1 * ?
&Duration=30
&RegionId=cn-shanghai
&SerialNumber=sage62x022502****
&SmartAGId=sag-1um5x5nwhilymw****
&TimeZone=Asia/Shanghai
&UpgradeType=scheduled
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<ModifyDeviceAutoUpgradePolicyResponse>
  <RequestId>F03C6897-2284-4BC8-94B4-1467BD992A2D</RequestId>
</ModifyDeviceAutoUpgradePolicyResponse>
```

`JSON` 格式

```
{
	"RequestId": "F03C6897-2284-4BC8-94B4-1467BD992A2D"
}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|SAG.InstanceIdEmpty|You must specify the SAG instance ID.|智能网关实例ID为空。|
|400|SAG.InvalidSerialNumber|The specified SerialNumber is invalid.|非法的序列号。|

访问[错误中心](https://error-center.alibabacloud.com/status/product/Smartag)查看更多错误码。

