# Configure the SAG-1000 device in the web console

When you use a Smart Access Gateway \(SAG\) device to connect private networks to Alibaba Cloud, you can configure the device in the SAG console. Alternatively, you can log on to the local SAG web console to configure the device. SAG version 2.0.3 is used in this example.

We recommend that you use the Chrome or Firefox browser due to browser incompatibility issues.

## Step 1: Configure the local client

Before you can configure the SAG-1000 device in the local web console, you must configure a static IP address for the local client.

-   Windows clients: Configure a static IP address for a Windows client. Windows 10 is used in the following example.
    1.  In the lower-right corner, right-click the network connection icon, and then click **Network and Internet**.
    2.  In the right-side panel, click **Change adapter settings**.
    3.  Right-click the connected network, and then click **Properties**.
    4.  Double-click **Internet Protocol Version 4 \(TCP/IPv4\)**.
    5.  Select **Use the following IP address**, and then enter the static IP address and subnet mask.

        **Note:** Make sure that the IP address you enter is falls into the management CIDR block of the SAG-1000 device \(the default CIDR block is 192.168.0.0/24\) and does not overlap with other IP addresses, such as 192.168.0.99. You do not need to configure the gateway or DNS settings.

        ![Configure a static IP address](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/3555485951/p59420.png)

    6.  Click **OK**.
-   Mac clients: Configure a static IP address for a Mac client.
    1.  On the desktop, click the **System Preferences** icon, and then click **Network** in the **Internet & Network** section.****
    2.  Click the connected network, and then click **Advanced**.
    3.  On the Ethernet page, click the **TCP/IP** tab.
    4.  In the **Configure IPv4** drop-down list, select **Manually** and enter the static IP address and subnet mask.

        **Note:** Make sure that the IP address you enter falls into the management CIDR block of the SAG-1000 device \(the default CIDR block is 192.168.0.0/24\) and does not overlap with other IP addresses, such as 192.168.0.99. You do not need to configure the router or DNS settings.

        ![Configure a static IP address for a Mac client](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/3555485951/p59421.png)


## Step 2: Set the password

If this is your first time logging on to the web console, you must set the logon password.

**Note:** Before you log on to the web console, make sure that you have met the following requirements:

-   The SAG-1000 device is powered on.
-   A static IP address is configured for the local client. For more information, see [Step 1: Configure the local client](#section_6xu_c2m_hlr).

1.  Port 2 of the SAG-1000 device has been connected to the local client.

2.  Open the browser on the connected local client and enter `192.168.0.1` in the address bar.

    `192.168.0.1` is the default web console address of the SAG-1000 device.

3.  If this is your first time logging on to the web console, you must set the logon password.

    Keep your password confidential. If you forget your password, press the reset button on your device to clear the password.

4.  Log on to the web console.


## Step 3: Configure the SAG-1000 device

After you log on to the web console of the SAG-1000 device, you can configure the device. SAG-1000 provides multiple features to meet your requirements in different deployment scenarios. For more information about how to connect private networks to Alibaba Cloud through SAG-1000, see [Deploy an SAG-1000 device](/intl.en-US/Configuration Guide/Deploy an SAG-1000 device.md).

1.  Assign port roles.

    1.  In the top navigation bar of the web console, click **Setting**.

    2.  To view port roles, click **Port Alloc** in the left-side navigation pane.

        Ports of SAG-1000 devices are assigned default roles. You can modify the port roles as needed. For more information about port roles, see [Assign a role to a port](/intl.en-US/Configuration Guide/Manage devices/Manage devices/Assign a role to a port.md).

    3.  Click ![The drop-down icon](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/0275341061/p102026.png) next to the target port, select the target port role, and then click **OK** to modify the port role.

        **Note:** When you modify a port role in the web console, the port settings of both the active and standby SAG devices are modified. After you modify the port role, restart both devices.

2.  Configure a WAN port.

    1.  In the top navigation bar of the web console, click **Setting**.

    2.  Click **WAN** to configure a WAN port.

        By default, the connection type of the WAN port on the SAG-1000 device is **Dynamic IP**. The IP address of a WAN port is automatically obtained by the device that is connected to the WAN port.

        **Note:** You can configure a WAN port as needed. For more information about the parameters of the WAN port, see [Configure a WAN port](/intl.en-US/Configuration Guide/Manage devices/Manage devices/Configure a WAN port.md).

3.  Configure a LAN port.

    1.  In the top navigation bar of the web console, click **Setting**.

    2.  Click **LAN** to configure a LAN port. You can configure a LAN port as needed. For more information about the parameters of the LAN port, see [Configure a LAN port](/intl.en-US/Configuration Guide/Manage devices/Manage devices/Configure a LAN port.md).

        When you configure a LAN port in the web console, if the connection type of the LAN port is **Dynamic IP**, the SAG device allows you to enter custom CIDR blocks.

        ![Configure a dynamic IP address for a LAN port.](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/0275341061/p102027.png)

        -   **Unselected**: allows you to enter a custom IP address for the port and set a custom Dynamic Host Configuration Protocol \(DHCP\) address pool.
        -   **Custom Segment**: allows you to enter custom CIDR blocks. The system automatically allocates an IP address and DHCP address pool for the LAN port. You can manually modify the allocated IP address.
        -   **Available CIDR block**: If you have configured local routes in the SAG console, the CIDR blocks are automatically displayed. You can allocate IP addresses as needed. For example, 192.XX.XX.XX in the preceding figure.
4.  Configure the management port.

    1.  In the top navigation bar of the web console, click **Setting**.

    2.  Click **Management** to configure the management port.

        By default, the management CIDR block of the SAG-1000 device is 192.168.0.0/24 and the IP address of the management port is 192.168.0.1. You can configure the management port as needed. For more information about the parameters, see [Configure the management port](/intl.en-US/Configuration Guide/Manage devices/Manage devices/Configure the management port.md).

5.  Configure the routes.

    1.  In the top navigation bar of the web console, click **Setting**.

    2.  Click **Route** to configure static routes, Border Gateway Protocol \(BGP\) dynamic routes, or Open Shortest Path First \(OSPF\) dynamic routes.

        For more information about how to configure the routes, see [Add a static route](/intl.en-US/Configuration Guide/Manage devices/Manage devices/Manage routes/Add a static route.md), [Configure OSPF routing](/intl.en-US/Configuration Guide/Manage devices/Manage devices/Manage routes/Configure OSPF routing.md), and [Configure BGP routing](/intl.en-US/Configuration Guide/Manage devices/Manage devices/Manage routes/Configure BGP routing.md).


## Optional. Step 4: Advanced configurations

The SAG-1000 device supports advanced configurations such as leased line ports and high availability \(HA\).

1.  Configure leased lines.

    1.  In the top navigation bar of the web console, click **Setting**.

    2.  Click **ECC** to configure leased line ports.

        The SAG-1000 device supports leased lines. Leased lines and SAG devices provide standby network connections for each other. For more information about how to configure leased lines, see [Configure a leased line port](/intl.en-US/Configuration Guide/Manage devices/Manage devices/Configure a leased line port.md).

        **Note:** If you need leased line ports, make sure that you have assigned a role to the leased line port. For more information, see [Assign a role to a port](/intl.en-US/Configuration Guide/Manage devices/Manage devices/Assign a role to a port.md).

2.  Configure HA.

    1.  In the top navigation bar of the web console, click **Setting**.

    2.  Click **HA** to configure HA.

        The SAG-1000 device supports HA configurations to continue to provide services when one SAG device fails to work. For more information about the parameters, see [Configure HA for SAG devices](/intl.en-US/Configuration Guide/Manage devices/Manage devices/Configure HA for SAG devices.md).


