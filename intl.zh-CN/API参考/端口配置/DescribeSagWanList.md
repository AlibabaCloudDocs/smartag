# DescribeSagWanList

调用DescribeSagWanList查询智能接入网关设备WAN口配置信息。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=DescribeSagWanList&type=RPC&version=2018-03-13)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|DescribeSagWanList|要执行的操作。

 取值：**DescribeSagWanList**。 |
|RegionId|String|是|cn-shanghai|智能接入网关实例地域ID。 |
|SmartAGId|String|是|sag-whfn\*\*\*\*|智能接入网关实例ID。 |
|SmartAGSn|String|是|sag32a30\*\*\*\*|智能接入网关设备序列号。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|CE6642D4-21EB-4168-9BF9-F217953F9892|请求ID。 |
|TaskStates|Array of TaskState| |查询任务信息及状态。 |
|CreateTime|String|1586834861000|查询任务创建时间。 |
|ErrorCode|String|200|错误码。200标识查询任务成功。 |
|ErrorMessage|String|Successful|错误信息。Successful标识查询任务成功。 |
|State|String|Succeed|查询任务状态：

 -   **Initialized**：查询任务初始化。
-   **Offline**：智能接入网关设备离线未下发查询任务，智能接入网关设备上线后会继续下发。
-   **Succeed**：查询任务下发成功。
-   **Processing**：查询任务下发中。
-   **VersionNotSupport**：智能接入网关设备当前版本不支持。
-   **BuildRequestError**：管控不支持。
-   **HardwareError**：由于设备原因查询任务下发失败。
-   **TaskNotExist**：查询任务不存在。
-   **OfflineNotConfiged**：智能接入网关设备离线未下发查询任务，智能接入网关设备上线后也不会下发。 |
|Wans|Array of Wan| |WAN口配置信息列表。 |
|BandWidth|Integer|50|WAN口的限速带宽。单位：Mbps。 |
|Gateway|String|192.XX.XX.1|网关IP地址。 |
|IP|String|172.XX.XX.1|WAN口IP地址。 |
|IPType|String|STATIC|WAN口连接类型：

 -   **DHCP**：通过DHCP协议动态获取IP地址，进而访问互联网。
-   **STATIC**：通过静态指定IP地址，进而访问互联网。
-   **PPPOE**：通过拨号方式接入互联网。 |
|ISP|String|CT|WAN口连接的运营商链路。

 -   **CT**：电信
-   **CM**：移动
-   **CU**：联通
-   **Other**：其他 |
|Mask|String|255.255.255.240|WAN口IP地址掩码。 |
|PortName|String|1|WAN口所属的端口号。 |
|Priority|Integer|1|WAN口优先级。

 数值范围：**-1**或**1~50**，数值越小优先级越高。

 **说明：** 优先级为**-1**时，表示端口不启用流量转发。 |
|TrafficState|String|active|WAN口流量状态。

 -   **active**：表示当前WAN端口为主端口，优先进行转发流量。
-   **standby**：表示当前WAN端口为备端口，在主端口故障后进行流量转发。 |
|Username|String|Usernamexx|PPPOE账号。 |
|Weight|Integer|100|WAN口权重。 |

## 示例

请求示例

```
http(s)://smartag.cn-shanghai.aliyuncs.com/?Action=DescribeSagWanList
&RegionId=cn-shanghai
&SmartAGId=sag-whfn****
&SmartAGSn=sag32a30****
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<DescribeSagWanListResponse>
  <RequestId>D6E2D7AF-6721-462F-B460-D1CE616BC557</RequestId>
  <Wans>
        <IPType>DHCP</IPType>
        <Username></Username>
        <Gateway>172.XX.XX.254</Gateway>
        <Priority>10</Priority>
        <IP>172.XX.XX.43</IP>
        <Mask>255.255.255.0</Mask>
        <PortName>3</PortName>
  </Wans>
  <Wans>
        <IPType>STATIC</IPType>
        <Username></Username>
        <Gateway>10.XX.XX.254</Gateway>
        <Priority>20</Priority>
        <IP>10.XX.XX.200</IP>
        <Mask>255.255.255.0</Mask>
        <PortName>4</PortName>
  </Wans>
</DescribeSagWanListResponse>
```

`JSON` 格式

```
{
	"RequestId": "D6E2D7AF-6721-462F-B460-D1CE616BC557",
	"Wans": [
		{
			"IPType": "DHCP",
			"Username": "",
			"Gateway": "172.XX.XX.254",
			"Priority": 10,
			"IP": "172.XX.XX.43",
			"Mask": "255.255.255.0",
			"PortName": "3"
		},
		{
			"IPType": "STATIC",
			"Username": "",
			"Gateway": "10.XX.XX.254",
			"Priority": 20,
			"IP": "10.XX.XX.200",
			"Mask": "255.255.255.0",
			"PortName": "4"
		}
	]
}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|SAG.InstanceNoFound|The specified SAG instance does not exist.|智能网关实例不存在。|
|400|SAG.SoftwareNotSupport|The specified SAG software edition instance does not support ACL.|智能接入网关软件版实例不支持ACL。|
|500|SmartAccessGatewayInArrears|The specified Smart Access Gateway has expired.|该智能接入网关已经到期停服，请续费。|
|500|SmartAccessGatewayNotActivated|The specified Smart Access Gateway has not been activated.|该智能接入网关尚未激活，请先激活该实例。|
|403|SmartAccessGatewayNotOnline|The specified smart access gateway is not online.|该智能接入网关当前不是在线状态，无法完成操作。|
|500|SmartAccessGatewayOffline|The request cannot be completed. The Smart Access Gateway is offline.|智能接入网关离线，请求无法完成。|
|400|InstanceNotExit|The specified instance does not exist.|指定的实例不存在。|
|400|ConfigUnsynchronized|The network configuration is not synchronized.|网络配置未同步|
|403|FeatureNotSupport|The current edition of the smart access gateway does not support this feature.|智能接入网关当前版本不支持该功能特性。|
|403|FeatureNotSupportForActiveSmartAG|The current edition of the active smart access gateway does not support this feature.|主智能接入网关的当前版本不支持该功能特性。|
|403|FeatureNotSupportForStandBySmartAG|The current edition of the standby smart access gateway does not support this feature.|备智能接入网关的当前版本不支持该功能特性。|
|400|Sag.PortRoleInvalid|The port role is invalid.|设备端口角色不正确|
|400|Sag.PortMgtError|The role of a management port cannot be changed.|管理口角色不能修改。|

访问[错误中心](https://error-center.alibabacloud.com/status/product/Smartag)查看更多错误码。

