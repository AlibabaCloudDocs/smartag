# CreateSmartAccessGateway {#reference_dwv_zjs_j2b .reference}

创建智能接入网关实例。

## 请求参数 {#section_stb_xd5_j2b .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 执行的操作，取值：

 CreateSmartAccessGateway

 |
|AutoPay|Boolean|是|是否是自动支付预付费实例的账单，取值：true|false 默认值是false。

|
|BuyerMessage|String|是| 买家留言信息。

 |
|ChargeType|String|是| 实例的计费类型，取值：

-   PayOnDemand：按量付费
-   PrePay：预付费

 **说明：** 当前只支持预付费。

 |
|HardWareSpec|String|是|实例类型，取值：sag-100wm|sag-1000|
|HaType|String|是| 选择一种使用方式，取值：

-   no\_backup：只购买一台智能接入网关设备接入阿里云。
-   cold\_backup：购买两台网关设备共享带宽，主设备故障时切换到备用设备。

 |
|MaxBandWidth|Integer|是|智能接入网关的带宽。-   如果网关设备规格为sag-100wm，带宽取值：2~50Mbps
-   如果网关设备规格为sag-1000，带宽取值：10~500Mbps

|
|Period|Integer|是|购买时长，单位月。如果取值超过12，必须是12的倍数。|
|ReceiverAddress|String|是|网关设备的收货地址。|
|ReceiverCity|String|是|收货城市。|
|ReceiverCountry|String|是|收货国家。|
|ReceiverDistrict|String|是|收货街区。|
|ReceiverEmail|String|是|收货人的电子邮箱。|
|ReceiverMobile|String|是|收件人手机号。|
|ReceiverName|String|是|收件人姓名。|
|ReceiverState|String|是|收货省份。|
|ReceiverZip|String|是|收货省份邮编。|
|RegionId|String|是|智能接入网关实例的地域。您可以通过调用 DescribeRegions接口获取地域ID。|
|Name|String|否|智能接入网关实例名称。|
|Description|String|否|智能接入网关实例描述。|
|ReceiverTown|String|否|收货乡镇。|
|ReceiverPhone|String|否|收件人电话。|

## 返回参数 {#section_ntb_hf5_j2b .section}

|参数|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|Description|String|智能接入网关实例描述。|
|Name|String|智能接入网关实例名称。|
|OrderId|String|订单ID。|
|SmartAGId|String|智能接入网关实例ID。|

