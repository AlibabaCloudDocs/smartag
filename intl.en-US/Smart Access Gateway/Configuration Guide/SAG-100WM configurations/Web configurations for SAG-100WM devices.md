# Web configurations for SAG-100WM devices {#task_1340440 .task}

This topic describes the steps that you must follow to complete Web configurations for SAG-100WM devices. Before you access Alibaba Cloud through Smart Access Gateway \(SAG\) devices, you must complete Web configurations for the SAG devices.

## Step 1: Configure the local client {#section_ja0_y8g_0bz .section}

Before performing the Web configuration for the SAG-100WM device, you must enable DHCP on local clients so that the clients can connect to the device.

-   Windows client configuration
    1.  In the lower-right corner, right-click the network connection icon and then click **Open Network and Sharing Center**.
    2.  In the left-side panel, click **Change Adapter Settings**.
    3.  Right-click the connected network, and then click **Properties**.
    4.  Double-click **Internet Protocol Version 4 \(TCP/IPv4\)**.

        ![TCP/IPv4](images/21208_en-US.png)

    5.  Select **Obtain an IP Address Automatically** and **Obtain DNS Server Address Automatically**.

        ![DNS](images/21209_en-US.png)

    6.  Click **OK**.
-   Mac client configuration
    1.  On the desktop, click the **System Preferences** icon, and then click **Network** in the Internet and Network section.
    2.  Click the connected network and then click **Advanced**.
    3.  On the Ethernet configuration page, click the **TCP/IP** tab.
    4.  From the **Configure IPv4** drop-down list, select **Using DHCP**.

        ![DHCP](images/21226_en-US.png)


## Step 2: Set the password upon your first logon {#section_a8o_atv_nph .section}

After you power on the SAG device for the first time, you must go to the Web console to set the logon password.

Before you log on to the Web console, make sure that:

-   The SAG device is powered on.
-   A LAN port of the SAG device is connected to the local client.
-   The local client has DNS enabled to automatically obtain an IP address.

1.  Open the browser on the connected local PC and enter `192.168.0.1` in the address bar. 

    `192.168.0.1` is the default Web configuration address of the SAG device.

    **Note:** 

    -   If the LAN port uses a static IP address that you configured, log on by using that IP address.
    -   If the LAN port uses a dynamic IP address \(that is, you have configured CIDR blocks in the console, the WAN port has DHCP enabled, and the CLOUD status indicator light turns on when the network cable is connected\), log on by using the first IP address in the first CIDR block configured in the console.

        For example, if the first CIDR block you specified is 192.168.0.0/16, the Web configuration address is 192.168.0.1.

    -   If neither the LAN port nor the console is configured, the default address is `192.168.0.1`.
2.  Set the logon password. 

    ![Web console password](images/21180_en-US.png)

3.  Click **OK**, enter the new password, and log on to the Web console. Keep your logon password securely. If you forget your password, press and hold the RESET button on your device for two seconds and then log on to the Web console to reset the password.

    **Note:** 

    -   To clear all configurations of the SAG device, power the device on and press and hold the RESET button for five seconds until the CLOUD indicator light starts to flicker.
    -   To restore the SAG device to its default configurations, power off the device, and then press and hold the RESET button while powering the device back on. When the CLOUD indicator light is on, which means the device is restoring, release the RESET button.

        After two to three minutes, the CLOUD indicator light goes off, which means the default configurations are restored.


## Step 3: Configure the WAN ports {#section_skx_psp_zfv .section}

The WAN ports of the Smart Access Gateway \(SAG\) device are used for configuring Internet access and support dynamic IP addresses, static IP addresses, and PPPoE connections.

1.  Log on to the Web configuration page of the SAG device.
2.  Enter the logon password and click **OK**.
3.  Click **WAN Port Management**. On the WAN Port Management page, configure the WAN ports.
4.  Select whether to enable SNAT forwarding. If SNAT forwarding is enabled, packets sent to the WAN from the LAN are forwarded by using NAT by default. 

    Select a connection mode:

    -   Dynamic IP:

        Select this mode to allow access to the Internet by using an IP address allocated by a DHCP server from a router.

    -   Static IP:

        Select this mode to allow access to the Internet by using a specified IP address. If this mode is selected, you must configure the subnet mask and gateway in addition to the Static IP address.

        **Note:** The specified static IP address and the uplink router device must be in the same CIDR block.

    -   PPPoE: Select this mode if you want to access the Internet by using dial-up. You need to enter the PPPoE account name and password provided by the service provider.

        ![WAN port management](images/41150_en-US.png)

5.  Click **OK**.

## Step 4: Configure the LAN ports {#section_ttc_j0r_3tc .section}

The LAN ports are used for connecting the local clients.

1.  Log on to the Web configuration page of the SAG device.
2.  After the WAN ports are configured, click **LAN Port Management**.
3.  On the LAN Port Management page, configure the LAN ports. 
    -   Wireless mode

        The LAN ports are used for connecting local clients. If you enable the Wi-Fi function, configure the LAN ports according to the following information.

        |Configuration|Description|
        |:------------|:----------|
        |**SSID**|The name of the LAN. It is used to differentiate networks and can be customized.|
        |**SSID broadcast**|Wi-Fi devices can search out the Wi-Fi signal of the SSID only after SSID broadcast is enabled.|
        |**Wireless Security**|If you enable Wi-Fi security, you can set a password. If you disable Wi-Fi security, no password is set and the Wi-Fi can be accessed by any device.

 |
        |**Authentication Method**|WPA-PSK authentication and WPA2-PSK authentication are supported. WPA2-PSK authentication features higher security.|
        |**Encryption Algorithm**|         -   TKIP is a temporal key integrity protocol and is not secure. We do not recommend this encryption algorithm.
        -   AES is an efficient encryption standard for Wi-Fi authorization.
 |
        |**Password**|Set the Wi-Fi password.|

        ![Wireless mode](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/40492/156680600441292_en-US.png)

    -   Ethernet mode

        The LAN ports are used for connecting local clients. If you use network cables to connect the LAN ports, select a connection mode:

        -   Dynamic IP address:

            The IP addresses used by the LAN ports are allocated from the first CIDR block configured in Alibaba Cloud console.

            If your local clients directly access Alibaba Cloud by using an SAG device as shown in the following figure, use the default configurations.

            ![Access Alibaba Cloud by using SAG devices](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15409/15668060056822_en-US.png)

        -   Static IP address:

            If the IP address of the local client has been configured through the switch as shown in the following figure, use a static IP address.

            ![Static IP address](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/40492/156680600521798_en-US.png)

            To use a static IP address, you must configure the static IP address and routes:

            -   Static IP address: the IP address of the SAG device.

                **Note:** Make sure the static IP address does not conflict with any network connected to the SAG device.

            -   If the LAN ports are connected through **static IP**, you need to add a route to the SAG device and the switch separately.
                -   Route configuration for the SAG device

                    On the LAN configuration page, select **Configure routes**, and then add a route. Set the IP address of the local client as the destination CIDR block and set the IP address of the switch as the next hop.

                    If you have multiple clients, you must configure a route for each client.

                -   Route configuration for the switch
                    -   If local clients are to communicate with a VPC, add a route to the switch. The destination CIDR block is the CIDR block of the VPC, and the next hop is the static IP address of the LAN ports.
                    -   If local branches want to connect with each other through SAG devices, add the respective routes to the switch. The destination CIDR block of each route is the IP address of each local branch, and the next hop of each route is the static IP address of each LAN port.

