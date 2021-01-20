# ModifySagWan

调用ModifySagWan修改智能接入网关设备的WAN口配置。

## 背景信息

在您修改WAN口配置前，建议您先了解WAN口的功能信息。更多信息，请参见[配置WAN口](~~163955~~)。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=ModifySagWan&type=RPC&version=2018-03-13)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|ModifySagWan|要执行的操作。

 取值：**ModifySagWan**。 |
|IPType|String|是|DHCP|WAN口连接类型。取值：

 -   **DHCP**：通过DHCP协议动态获取IP地址，进而访问互联网。
-   **STATIC**：通过静态指定IP地址，进而访问互联网。此种方式需要为WAN口配置静态IP地址、地址掩码及网关IP地址。
-   **PPPOE**：通过拨号方式接入互联网。此种方式需要输入运营商提供的PPPOE账号和密码。 |
|PortName|String|是|0|WAN口所属的端口号。 |
|RegionId|String|是|cn-shanghai|智能接入网关实例地域ID。 |
|SmartAGId|String|是|sag-whfn\*\*\*\*|智能接入网关实例ID。 |
|SmartAGSn|String|是|sag32a30\*\*\*\*|智能接入网关设备序列号。 |
|IP|String|否|192.XX.XX.1|WAN口IP地址。

 **说明：** IPType为STATIC时需要输入。 |
|Mask|String|否|255.255.255.0|WAN口IP地址掩码。

 **说明：** IPType为STATIC时需要输入。 |
|Gateway|String|否|192.XX.XX.254|网关IP地址。

 **说明：**

-   IPType为STATIC时需要输入。
-   配置网关后，智能接入网关设备会自动生成一条默认路由。 |
|Username|String|否|P12ppp\*\*\*|PPPOE账号。

 长度为6~30位字符，可包含数字、大小写字母。

 **说明：** IPType为PPPOE时需要输入。 |
|Password|String|否|P12ppq\*\*\*|PPPOE密码。

 长度为6~30位字符，可包含数字、大小写字母。

 **说明：** IPType为PPPOE时需要输入。密码不修改时可以不指定该项。 |
|Priority|Integer|否|1|WAN口优先级。

 取值范围：**-1**或**1~50**。

 数值越小优先级越高。**-1**表示该WAN口不启用流量转发。 |
|Weight|Integer|否|100|WAN口权重。

 取值范围：**1~100**。默认值：**100**。 |
|ISP|String|否|CT|WAN口连接的运营商链路。取值：

 -   **CT**：电信
-   **CM**：移动
-   **CU**：联通
-   **Other**：其他 |
|Bandwidth|Integer|否|50|WAN口的限速带宽。单位：Mbps。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|AFF7E5A6-6897-4FDC-A5A8-1978B5B3E545|请求ID。 |

## 示例

请求示例

```
http(s)://smartag.cn-shanghai.aliyuncs.com/?Action=ModifySagWan
&IPType=DHCP
&PortName=0
&RegionId=cn-shanghai
&SmartAGId=sag-whfn****
&SmartAGSn=sag32a30****
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<ModifySagWanResponse>
     <RequestId>AFF7E5A6-6897-4FDC-A5A8-1978B5B3E545</RequestId>
</ModifySagWanResponse>
```

`JSON` 格式

```
{
"RequestId": "AFF7E5A6-6897-4FDC-A5A8-1978B5B3E545"
}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|Sag.PortNotExist|The specified port does not exist.|当前端口不存在|
|400|Sag.PortRoleInvalid|The port role is invalid.|设备端口角色不正确|

访问[错误中心](https://error-center.alibabacloud.com/status/product/Smartag)查看更多错误码。

