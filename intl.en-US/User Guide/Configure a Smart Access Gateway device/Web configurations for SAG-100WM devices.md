# Web configurations for SAG-100WM devices {#concept_w1f_ns2_lfb .concept}

SAG-100WM Smart Access Gateway \(SAG\) devices supports dynamic and static IP addresses, PPPoE connections, and SNAT forwarding. You can modify the WAN port and LAN port configurations as needed, or keep the default configurations.

## Default configurations {#section_defaultconfig .section}

After you power on your SAG device, you need to connect the WAN and LAN ports of the device to allow your local clients to access Alibaba Cloud. To do so, we recommend that you perform the following actions: Connect the WAN port of the SAG device to your network cable, and then connect the LAN ports to the local clients that require communication. You do not need to modify the WAN port and LAN port configurations for the SAG device.

By default, the WAN port accesses the Internet by using an IP address allocated from the router by the DHCP server. If the LAN port of the SAG device uses a dynamic IP address and DHCP is enabled on the client, the IP address used by the local client is allocated from the first CIDR block that you specified.

## Configure the WAN port {#section_dtr_dt2_lfb .section}

The WAN mode of an SAG device is used for configuring Internet access and supports dynamic IP addresses, static IP addresses and PPPoE connection.

To configure the WAN port, follow these steps:

1.  Log on to the web configuration page of the SAG device.
2.  Click **Next** to configure the WAN port.
3.  Select whether to enable SNAT forwarding.

    Once SNAT forwarding is enabled, packets sent from Local Area Network to Wide Area Network are subjected to NAT forwarding by default.

4.  Select a connection mode:
    -   Dynamic IP address:

        To use an IP address allocated by a DHCP server from an Internet router to access the Internet, select this mode.

    -   Static IP address:

        To use a specified IP address to access the Internet, select this mode. If this mode is selected, you must configure the static IP address, the subnet mask and the gateway.

        **Note:** Make sure that the specified static IP address and the uplink router device are in the same CIDR block.

    -   PPPoE: If you want to access the Internet through dialing, select this mode. Then enter the PPPoE account and password provided by the service provider.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15409/15627396636821_en-US.png)


## LAN configurations \(wireless mode\) {#section_fj3_zst_j2b .section}

LAN ports are used to connect local clients. If you select to enable Wi-Fi, configure LAN ports according to the following information.

|Configuration|Description|
|:------------|:----------|
|**SSID**|The name of the LAN. It is used to differentiate networks and can be customized.|
|**SSID broadcasting**|You need to enable SSID broadcast for Wi-Fi devices to detect the Wi-Fi network.|
|**Authentication method**|WPA-PSK and WPA2-PSK authentication are supported. The WPA2-PSK authentication features higher security.|
|**Encryption algorithm**| -   TKIP is a temporal key integrity protocol and is not secure. We do not recommend using it.
-   AES is an efficient encryption standard for Wi-Fi authorization.

 |
|**Password**|Set the Wi-Fi password.|

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/23646/156273966313651_en-US.png)

## LAN configurations \(Ethernet mode\) {#section_y31_aek_k58 .section}

LAN ports on the SAG device are used to connect local clients to Alibaba Cloud. If you connect LAN ports of the SAG device to local clients by using network cables, you need to select the method for IP address allocation:

-   Dynamic IP:

    The IP addresses used by the LAN ports are allocated from the first CIDR block configured on Alibaba Cloud console.

    If your local clients directly access Alibaba Cloud by using an SAG device as shown in the following figure, use the default configurations.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15409/15627396646822_en-US.png)

-   Static IP:

    If the IP address of the local client has been configured through the switch as shown in the following figure, use a static IP address.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15409/15627396646823_en-US.png)

    To use a static IP address, you must configure the static IP address and routes:

    -   Static IP address: The forwarding address of the SAG device.

        If the specified static IP address and the IP address of the switch are in the same CIDR block, we recommend that you set the gateway address of the switch to the specified static IP address so that no route configuration is required.

        **Note:** Make sure the static IP address does not conflict with any network to which the SAG device will connect in the future.


## Route configurations {#section_kv1_jpv_mfb .section}

If you use **static IP** as the method for IP address allocation for the LAN ports on the SAG device, you must add routes for the SAG device and to the switch.

-   Route configuration for the device

    On the LAN Ports page, click **Configure routes**, and then add a route. Set the IP address of the local client as the destination CIDR block and set the IP address of the switch as the next hop.

    If you have multiple clients, you must configure a route for each client.

-   Route configuration for the switch

    -   If local clients are to communicate with a VPC, add a route to the switch. The destination CIDR block is the CIDR block of the VPC, and the next hop is the static IP address of the LAN ports.
    -   If local branches want to connect with each other through SAG devices, add the respective routes to the switch. The destination CIDR block of each route is the IP address of each local branch, and the next hop of each route is the static IP address of each LAN port.
    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/23646/156273966439824_en-US.png)


