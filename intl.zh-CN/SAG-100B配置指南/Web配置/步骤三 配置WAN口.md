# 步骤三 配置WAN口 {#task_wqg_tfc_pfb .task}

智能接入网关WAN模式用于配置Internet接入，支持动态IP、PPPoE连接和静态IP连接。

1.  登录智能接入网关Web配置页面。 
2.  输入登录密码，单击**确定**，在WAN配置页面，配置WAN口。 
3.  选择是否开启SNAT转发，开启SNAT转发后，由本地局域网向广域网发送的数据包默认经过NAT转发。 

    选择一种连接方式：

    -   动态IP：

        如果通过DHCP协议从互联网路由器中分配一个地址访问互联网，选择该方式。

    -   静态IP：

        如果通过指定的IP地址访问互联网，选择该方式。此种连接方式需要配置静态IP、子网地址掩码及网关。

        **说明：** 确保指定的静态IP地址和上行路由设备在同一个网段内。

    -   PPPoE：如果通过拨号方式接入互联网，选择该方式。然后输入运营商提供的PPPoE的账号和密码。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15409/15542634496821_zh-CN.png)


