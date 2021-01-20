# UpgradeSmartAccessGatewaySoftware

调用UpgradeSmartAccessGatewaySoftware升级智能接入网关APP的客户端账号数规格。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=UpgradeSmartAccessGatewaySoftware&type=RPC&version=2018-03-13)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|UpgradeSmartAccessGatewaySoftware|要执行的操作。

 取值：**UpgradeSmartAccessGatewaySoftware**。 |
|AutoPay|Boolean|是|1|是否为自动支付预付费实例的账单：

 -   **0**：表示否。
-   **1**：表示是。

 **说明：** 如果您为非自动支付的预付费实例账单，调用本接口后，您还需要到智能接入网关管理控制台完成账单支付。 |
|DataPlan|Long|是|5|每个账号每月赠送的流量套餐规格。单位为GB。

 **说明：** 目前仅支持每个账号每个月赠送5 GB流量。 |
|RegionId|String|是|cn-shanghai|智能接入网关APP实例所属地域ID。 |
|SmartAGId|String|是|sag-8biez7habqwmx6\*\*\*\*|智能接入网关APP实例ID。 |
|UserCount|Integer|是|5|智能接入网关APP客户端账号数规格。

 购买后可创建相应数量的客户端账号，一般为每个需要登录的员工创建一个账号。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|OrderId|String|20697688135\*\*\*\*|订单ID。 |
|RequestId|String|97A4F8A5-603E-4C3B-A91E-17CD87090EA9|请求ID。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=UpgradeSmartAccessGatewaySoftware
&AutoPay=1
&DataPlan=5
&RegionId=cn-shanghai
&SmartAGId=sag-8biez7habqwmx6****
&UserCount=5
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<UpgradeSmartAccessGatewaySoftwareResponse>
  <RequestId>97A4F8A5-603E-4C3B-A91E-17CD87090EA9</RequestId>
  <OrderId>20697688135****</OrderId>
</UpgradeSmartAccessGatewaySoftwareResponse>
```

`JSON` 格式

```
{
	"RequestId": "97A4F8A5-603E-4C3B-A91E-17CD87090EA9",
	"OrderId": "20697688135****"
}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|SAG.InvalidUserCount|The specified UserCount is invalid.|非法的用户数。|
|400|SAG.InvalidDataPlan|The specified DataPlan is invalid.|非法的流量包套餐。|

访问[错误中心](https://error-center.alibabacloud.com/status/product/Smartag)查看更多错误码。

