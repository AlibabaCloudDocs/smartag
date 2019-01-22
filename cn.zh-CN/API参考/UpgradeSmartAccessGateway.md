# UpgradeSmartAccessGateway {#reference_snr_hjf_2gb .reference}

使用UpgradeSmartAccessGateway接口升高智能接入网关实例的带宽。

## 请求参数 {#section_stb_xd5_j2b .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 执行的操作，取值：

 UpgradeSmartAccessGateway

 |
|AutoPay|Boolean|是|是否是自动支付预付费实例的账单，取值：true|false 默认值是false。

|
|BandWidthSpec|String|是|智能接入网关的带宽。-   如果网关设备规格为sag-100wm，带宽取值：2~50Mbps
-   如果网关设备规格为sag-1000，带宽取值：10~500Mbps

|
|SmartAGId|String|是|智能接入网关实例ID。|
|RegionId|String|是|智能接入网关的地域ID。|

## 返回参数 {#section_ntb_hf5_j2b .section}

|参数|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|OrderId|String|订单ID。|

