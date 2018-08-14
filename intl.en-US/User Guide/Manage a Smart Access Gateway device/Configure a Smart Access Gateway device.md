# Configure a Smart Access Gateway device {#concept_vdh_m3s_j2b .concept}

A Smart Access Gateway device supports dynamic IP, static IP, PPPoE and SNAT forwarding. You can use the default configuration, or change the WAN port and LAN port configurations as needed.

## Use the default configuration { .section}

If your local clients directly access Alibaba Cloud through Smart Access Gateway, you can directly connect the WAN port of the gateway device to the cable and connect the LAN port to the local clients requiring communication after the gateway device is powered on. You do not need to change the WAN port and LAN port configurations of the gateway device.

By default, the WAN port uses an IP address allocated from the Internet router through DHCP to access the Internet. If the LAN port of the Smart Access Gateway device uses the dynamic IP mode and DHCP is enabled on the client, the IP address that the local client used is allocated from the first specified CIDR block.

## Log on to the web configuration page {#section_h1s_zrt_j2b .section}

Make sure the following conditions are met before you log on to the web configuration page of the gateway device for the first time:

-   The Smart Access Gateway device has been started and any LAN port of the device is connected to the local client.
-   The local client has enabled DNS to automatically obtain the IP address. Take the Windows system as an example:
    1.  Open the local network connection, and then click **Properties**.
    2.  Select **Internet Protocol Version 4 \(TCP/IPv4\)**, and then click **Properties**.
    3.  Select **Automatically obtain the IP address** and **Automatically obtain the DNS server address**, and click **Confirm**.

Complete these steps to log on to the web configuration page of the gateway device:

1.  Open the browser and enter `192.168.0.1` in the address bar.

    192.168.0.1 is the default address used for local network configuration. Note:

    -   If you have configured the LAN port, the web configuration address of the gateway device is the static IP address configured for the LAN port.
    -   If you haven't configured a static IP address for the LAN port, but have configured the private CIDR block for the local clients on the console, the web configuration address is the first IP address of the first private CIDR block. For example, if the first CIDR block is 192.168.0.0/16, the IP address for web configuration is 192.168.0.0.
2.  Enter the initial password.
3.  Enter the set password and log on to the web configuration page.

## WAN configuration {#section_gyh_4st_j2b .section}

The WAN mode of Smart Access Gateway is used for configuring Internet access and supports dynamic IP, static IP and PPPoE connection.

Complete these steps to configure the WAN port:

1.  Log on to the web configuration page of the Smart Access Gateway device.
2.  Click **Next** to configure the WAN port.
3.  Select whether to enable SNAT forwarding.

    Once SNAT forwarding is enabled, packets sent from Local Area Network to Wide Area Network are subjected to NAT forwarding by default.

4.  Select a connection mode:
    -   Dynamic IP:

        To use an IP address allocated by a DHCP server from an Internet router to access the Internet, select this mode.

    -   Static IP:

        To use a specified IP address to access the Internet, select this mode. If this mode is selected, you must configure the static IP, the subnet mask and the gateway.

        **Note:** Make sure that the specified static IP address and the uplink router device are in the same CIDR block.

    -   PPPoE: If you want to access the Internet through dialing, select this mode. Then enter the PPPoE account and password provided by the operator.

## LAN configuration {#section_fj3_zst_j2b .section}

The LAN port is used for accessing the local client.

Complete these steps to configure the LAN port:

1.  Log on to the web configuration page of the Smart Access Gateway device.
2.  Click **Next** to configure the WAN port.
3.  Click **Next** to configure the LAN port and select a connection mode:
    -   Dynamic IP:

        The IP addresses used by the LAN ports are allocated from the first CIDR block configured on Alibaba Cloud console.

        If your local clients directly access Alibaba Cloud through Smart Access Gateway as shown in the following figure, use the default configuration.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15409/15342540496822_en-US.png)

    -   Static IP:

        If the IP addresses of the local clients have been configured through a local switch as shown in the following figure, use a static IP.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15409/15342540496823_en-US.png)

        When static IP is selected, you must configure the static IP address and route:

        -   Static IP: The forwarding address of the Smart Access Gateway device.

            If the specified static IP address and the IP address of the switch are in the same IP address range, we recommend that you set the gateway address of the switch to the specified static IP address. Therefore, you do not need to configure the route.

            **Note:** Make sure the static IP address does not conflict with any network to connect.

        -   Route configuration: You must add a route for the Smart Access Gateway device and the switch respectively.
            -   Route configuration for the device: On the LAN configuration page, click **Route Configuration**, and then add a route of which the destination CIDR block is the IP address of the local client and the next hop is the IP address of the switch.

                If you have multiple clients, you must configure a route for each client.

            -   Route configuration for the switch: Add a route of which the destination CIDR block is the CIDR block of the VPC to connect, the private CIDR block of the local data center to connect, or the private CIDR block of the Smart Access Gateway device, and the next hop is the static IP of the LAN port.
