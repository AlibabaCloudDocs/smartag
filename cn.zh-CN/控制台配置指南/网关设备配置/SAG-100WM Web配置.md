# SAG-100WM Web配置 {#concept_w1f_ns2_lfb .concept}

SAG-100WM设备支持动态IP、静态IP、PPPoE连接及SNAT转发。您可以使用默认配置，也可以根据需要更改WAN口和LAN口配置。

## 默认配置 {#section_defaultconfig .section}

如果线下机构直接通过智能接入网关设备接入，在网关设备接入电源后，您可以直接将网关设备的WAN口和网线连接，将LAN口和需要通信的本地客户端连接，无需更改网关设备的WAN口和LAN口配置。

默认WAN口通过DHCP协议从互联网路由器中分配一个地址访问互联网。LAN口默认使用动态IP连接方式，则本地已开启DHCP协议的客户端使用的IP地址会从您为网关实例配置的第一个私网网段中分配。

## WAN配置 {#section_dtr_dt2_lfb .section}

智能接入网关WAN模式用于配置Internet接入，支持动态IP、静态IP和PPPoE连接。

完成以下操作，配置WAN口：

1.  登录智能接入网关Web配置页面。
2.  单击**下一步**，配置WAN口。
3.  选择是否开启SNAT转发。

    开启SNAT转发后，由本地局域网向广域网发送的数据包默认经过NAT转发。

4.  选择一种连接方式：
    -   动态IP：

        如果您想通过DHCP协议从互联网路由器中分配一个地址访问互联网，选择该方式。

    -   静态IP：

        如果您想通过指定的IP地址访问互联网，选择该方式。此种连接方式需要配置静态IP、子网地址掩码及网关。

        **说明：** 确保指定的静态IP地址和上行路由设备在同一个网段内。

    -   PPPoE：如果您想通过拨号方式接入互联网，选择该方式。然后输入运营商提供的PPPoE的账号和密码。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15409/15489884636821_zh-CN.png)


## LAN配置（开启无线功能） {#section_fj3_zst_j2b .section}

LAN口配置用于线下客户端接入，如果您选择开启无线功能，参考以下信息配置LAN口。

|配置|说明|
|:-|:-|
|**SSID**|局域网的名称，用于区分不同的网络，可自定义。|
|**SSID广播**|开启SSID广播后，无线设备才能搜索到该SSID名称的WIFI信号。|
|**认证类型**|支持WPA-PSK和WPA2-PSK两种认证类型，WPA2-PSK安全性更高。|
|**加密算法**| -   TKIP提供结合信息完整性检查和重新按键机制的信息包密钥。
-   AES是WiFi授权的高效加密标准。

 |
|**密码**|设置连接WiFi的密码。|

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/23646/154898846313651_zh-CN.png)

## LAN配置（有线模式） { .section}

LAN口配置用于线下客户端接入，如果您选择通过网线连接LAN口，选择一种连接方式：

-   动态IP：

    系统会从控制台网络配置中设置的第一个私网网段中分配LAN口的IP地址。

    如果您的线下客户端直通过智能接入网关接入阿里云，如下图所示，使用默认配置即可。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15409/15489884636822_zh-CN.png)

-   静态IP:

    如果线下客户端的IP已经通过线下交换机配置好了，如下图所示，请选择静态IP方式。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15409/15489884636823_zh-CN.png)

    选择该方式需要配置静态IP和路由：

    -   静态IP：智能接入网关终端设备的转发地址。

        如果指定的静态IP和交换机的IP地址在同一个网段内，建议您将交换机的网关地址配置为指定的静态IP地址，这样就无需进行路由配置。

        **说明：** 确保该静态IP地址和要连接的所有网络都不冲突。


## 路由配置 {#section_kv1_jpv_mfb .section}

如果LAN口的连接方式为**静态IP**，您需要分别在智能接入网关和线下交换机中添加路由。

-   智能接入网关路由配置

    在LAN配置页面，勾选**路由配置**。然后添加目标网段为线下客户端IP，下一跳为交换机的交换地址的路由。

    如果您线下有多个客户端，您需要为每个客户端单独配置路由。

-   交换机路由配置

    -   如果与云上VPC进行通信，需要在交换机中添加一条目标网段为云上VPC的网段，下一跳为LAN口静态IP的路由。
    -   如果有其他线下分支机构通过智能接入网关互连，在交换机中添加其他分支机构的网段路由，下一跳为LAN口静态IP的路由。
    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15409/15489884636824_zh-CN.png)


