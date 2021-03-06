# SAG-100WM Web配置 {#task_1340440 .task}

使用智能接入网关设备接入阿里云，需要对设备进行Web配置。

## 步骤1 配置本地客户端 {#section_ja0_y8g_0bz .section}

在进行SAG-100WM Web配置前，您需要为访问Web配置的本地客户端开启DHCP。

-   Windows客户端：为Windows客户端配置动态IP，以下以Windows10举例说明。
    1.  右键单击右下角的网络连接图标，然后单击**打开“网络和Internet”设置**。
    2.  在右侧面板，单击**更改适配器选项**。
    3.  右键单击所有连接的网络，然后单击**属性**。
    4.  双击**Internet 协议版本4（TCP/IPv4）**选项。

        ![TCP/IPv4](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/40489/156809834421208_zh-CN.png)

    5.  选择**自动获得IP地址**和**自动获得DNS服务器地址**。

        ![DNS](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/40489/156809834421209_zh-CN.png)

    6.  单击**确定**。
-   Mac客户端：为Mac客户端配置动态IP。
    1.  在桌面单击**系统偏好设置**图标，然后单击互联网和无线选项中的**网络**。
    2.  单击所有连接的网络，然后单击**高级**。
    3.  在以太网设置界面，单击**TCP/IP**页签。
    4.  在**配置IPv4**选项中，选择**使用DHCP**。

        ![DHCP](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/40489/156809834421226_zh-CN.png)


## 步骤2 首次登录设置密码 {#section_a8o_atv_nph .section}

在收到智能接入网关设备接通电源后，首次登录Web控制台，您需要设置Web控制台的登录密码。

在登录Web配置前，请确保：

-   智能接入网关设备已正常启动。
-   确保其LAN口与本地客户端相连。
-   本地客户端已经开启了DHCP服务自动获取IP地址。

1.  在连接的本地PC上打开浏览器，在地址栏输入`192.168.0.1`。 

    `192.168.0.1`是网关设备的默认Web配置地址。

    **说明：** 

    -   若LAN口配置为静态方式，通过您配置的静态IP登录。
    -   若LAN口配置为动态方式，用户在控制台上配置了网段，WAN口为DHCP，插上网线CLOUD指示亮，则通过控制台第一个私网网段的首地址登录。

        例如您设置的第一个私网网段为192.168.0.0/16，则Web配置的地址为192.168.0.1。

    -   若LAN口和控制台都未配置，默认地址为`192.168.0.1`。
2.  设置Web登录密码。 

    ![Web密码](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/40490/156809834421180_zh-CN.png)

3.  单击**下一步**，输入新设置的密码，登录Web配置页面。 请妥善保管您的登录密码。如果您忘记了设置的初始密码，按RESET键1秒可以清除密码，登录Web控制台，重新设置密码。

    **说明：** 

    -   网关加电情况下，长按RESET键5秒，松掉后，看到CLOUD指示灯快闪，将清空所有配置并重启设备。
    -   当需要恢复出厂版本时，先下电，然后长按RESET键，同时加电至CLOUD灯亮，此时松掉RESET键，等待网关进行恢复出厂版本操作。

        大概2~3分钟后，CLOUD灯灭表示恢复出厂版本成功，之后网关会进行重启。


## 步骤3 配置WAN口 {#section_skx_psp_zfv .section}

智能接入网关WAN模式用于配置Internet接入，支持动态IP、静态IP和PPPoE连接。

1.  登录智能接入网关Web配置页面。
2.  在Web配置首页，单击**设置**。
3.  单击**WAN口管理**，在WAN口管理页面，配置WAN口。
4.  选择是否开启SNAT转发，开启SNAT转发后，由本地局域网向广域网发送的数据包默认经过NAT转发。 

    选择一种连接方式：

    -   动态IP：

        如果通过DHCP协议从互联网路由器中分配一个地址访问互联网，选择该方式。

    -   静态IP：

        如果通过指定的IP地址访问互联网，选择该方式。此种连接方式需要配置静态IP、子网地址掩码及网关。

        **说明：** 确保指定的静态IP地址和上行路由设备在同一个网段内。

    -   PPPoE：如果通过拨号方式接入互联网，选择该方式。然后输入运营商提供的PPPoE的账号和密码。

        ![wan口管理](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/40491/156809834441150_zh-CN.png)

5.  单击**确定**，完成WAN口配置。

## 步骤4 配置LAN口 {#section_ttc_j0r_3tc .section}

LAN口配置用于线下客户端接入。

1.  登录智能接入网关Web配置页面。
2.  配置完WAN口后，单击**LAN口管理**。
3.  在LAN口管理页面，配置LAN口信息。 
    -   无线功能

        LAN口配置用于线下客户端接入，如果您选择开启无线功能，参考以下信息配置LAN口。

        |配置|说明|
        |:-|:-|
        |**SSID**|局域网的名称，用于区分不同的网络，可自定义。|
        |**SSID广播**|开启SSID广播后，无线设备才能搜索到该SSID名称的WIFI信号。|
        |**无线安全**|打开无线安全，可以设置密码。 关闭无线安全，表示不设置密码，任何人都可以接入。

 |
        |**认证类型**|支持WPA-PSK和WPA2-PSK两种认证类型，WPA2-PSK安全性更高。|
        |**加密算法**|         -   TKIP为临时密钥完整性协议，不安全，不推荐使用。
        -   AES是WiFi授权的高效加密标准。
 |
        |**密码**|设置连接WiFi的密码。|

        ![无线设置](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1069024/156809834459415_zh-CN.png)

    -   有线模式

        LAN口配置用于线下客户端接入，如果您选择通过网线连接LAN口，选择一种连接方式：

        -   动态IP：

            系统会从控制台网络配置中设置的第一个私网网段中分配LAN口的IP地址。

            如果您的线下客户端直接通过智能接入网关接入阿里云，如下图所示，使用默认配置即可。

            ![线下接入](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15409/15680983456822_zh-CN.png)

        -   静态IP：

            如果线下客户端的IP已经通过线下交换机配置好了，如下图所示，请选择静态IP方式。

            ![静态IP](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1069024/156809834559413_zh-CN.png)

            选择该方式需要配置静态IP和路由：

            -   静态IP：智能接入网关终端设备的转发地址。

                **说明：** 确保该静态IP地址和要连接的所有网络都不冲突。

            -   如果LAN口的连接方式为**静态IP**，您需要分别在智能接入网关和线下交换机中添加路由。
                -   智能接入网关路由配置

                    在LAN配置页面，勾选**路由配置**。然后添加目标网段为线下客户端IP，下一跳为交换机的交换地址的路由。

                    如果您线下有多个客户端，您需要为每个客户端单独配置路由。

                -   交换机路由配置
                    -   如果与云上VPC进行通信，需要在交换机中添加一条目标网段为云上VPC的网段，下一跳为LAN口静态IP的路由。
                    -   如果有其他线下分支机构通过智能接入网关互连，在交换机中添加其他分支机构的网段路由，下一跳为LAN口静态IP的路由。

## 步骤5 PING管理（可选） {#section_t8u_dct_662 .section}

通过PING管理，您可以测试智能接入网关与某个目的主机的网络连通性。

1.  登录智能接入网关Web配置页面。
2.  在Web配置首页，单击**设置**。
3.  单击**PING管理**。
4.  在PING管理页面，输入目标地址（域名或者IP）和源地址，设置包个数和包长。
5.  单击**开始**即可开始PING测试，单击**停止**即可停止PING测试。![PING管理](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1280310/156809834554952_zh-CN.png)



## 步骤6 Traceroute管理（可选） {#section_gju_aer_se8 .section}

通过Traceroute管理，您可以获取从智能接入网关到目的主机之间所经过的详细路由信息。

1.  登录智能接入网关Web配置页面。
2.  在Web配置首页单击**设置**。
3.  单击**Traceroute管理**。
4.  在Traceroute管理页面，输入目标地址（域名或者IP）和源地址。
5.  单击**开始**进行Traceroute测试，单击**停止**停止Trceroute测试。![Traceroute管理](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1280323/156809834554953_zh-CN.png)



## 步骤7 VRRP配置（可选） {#section_get_g5m_ir7 .section}

您可以通过配置VRRP，来解决智能接入网关单点路由失效的问题。

**说明：** 当您购买的智能接入网关为2台SAG-100WM，且设备的软件版本为1.7.1及以上时，并[提交工单](https://selfservice.console.aliyun.com/ticket/createIndex?spm=a2c8b.12571063.console-base-top.dwork-order-1.6c3a5675P2NEW9)修改智能接入网关为双机热备模式，才可以配置VRRP功能。

虚拟路由冗余协议VRRP（Virtual Router Redundancy Protocol）通过把几台路由设备联合组成一台虚拟的路由设备，将虚拟路由设备的IP地址作为局域网内主机的默认网关实现与外部网络通信。当主网关设备发生故障时，VRRP机制能够从备份的网关设备中选举一台设备成为新的主网关设备，用来承担数据流量，从而保障网络的可靠通信。

SAG-100WM配置VRRP时，仅支持同一实例中的设备组建VRRP备份组，系统会指定默认的主设备和备设备，您可以登录智能接入网关管理控制台查看设备的默认主备状态。当默认主设备发生故障时，默认备设备自动切换为主设备，实现数据的转发。当默认主设备恢复正常时，取代默认备设备成为主设备进行数据转发。您可以登录设备的Web配置页面查看设备的VRRP主备状态。

1.  登录智能接入网关SAG-100WM的Web配置页面。
2.  在Web配置首页，单击**设置**。
3.  单击**VRRP配置**。
4.  在VRRP配置页面，进行如下配置。 

    ![配置VRRP](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1513207/156809834557940_zh-CN.png)

    配置详情请参见下表。

    |配置|说明|
    |--|--|
    |**开启VRRP**|单击**开启VRRP**开关，开启/关闭VRRP功能。 **说明：** 在开启端口的VRRP功能之前，需确保端口为静态IP模式。

 |
    |**端口**|选择智能接入网关的端口： 请根据组网需要选择**WAN口**或**LAN口**。|
    |**VRRP ID**|VRRP备份组编号，取值范围1~255。 **说明：** 为确保主备智能接入网关能加入同一备份组，请将主备智能接入网关的VRRP ID设置为相同值。

 |
    |**虚IP**|智能接入网关的虚拟IP地址，输入形式为：IP地址/掩码，例如192.168.0.2/24。 **说明：** 

    -   虚IP必须跟端口实IP在同一网段，且不能与网段内已分配IP冲突。
    -   主备智能接入网关的虚IP需保持一致。
    -   您需要将局域网内的主机的默认网关设置为虚IP。
 |

5.  单击**确定**。

