# Configure SAG-100WM in the web console

When you use a Smart Access Gateway \(SAG\) device to connect private networks to Alibaba Cloud, you can configure the device in the SAG console. Alternatively, you can log on to the on-premises SAG web console to configure the device. This topic describes how to configure an SAG-100WM device in the web console.

-   SAG-100WM devices are supported by version 1.0.x and 2.0.x. For more information about features supported by each version, see [Features of Smart Access Gateway devices](/intl.en-US/Smart Access Gateway/Features of Smart Access Gateway devices.md). The following example uses version 2.0.3 to describe the web console of SAG-100WM devices.

    If you are using version 1.0.x, we recommend that you upgrade the system to 2.0.x. To upgrade the system,[submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.15120809.nav-right.dticket.130266ebEB92in#/ticket/add/?productId=1308).

-   To avoid incompatibility issues, we recommend that you use the Google Chrome or Firefox browser to log on to the web console. For more information about browser compatibility, see [Supported browsers for using the SAG web console](/intl.en-US/Smart Access Gateway/Supported browsers for using the SAG web console.md).

## Step 1: Configure the on-premises client

Before you configure an SAG-100WM device in the on-premises web console, you must enable Dynamic Host Configuration Protocol \(DHCP\) for the on-premises client to access the web console.

-   Windows: Configure a dynamic IP address for the Windows client. Windows 10 is used in the following example.
    1.  In the lower-right corner, right-click the network connection icon, and then click **Network and Internet**.
    2.  In the right-side panel, click **Change adapter settings**.
    3.  Right-click the connected network, and then click **Properties**.
    4.  Double-click **Internet Protocol Version 4 \(TCP/IPv4\)**.

        ![TCP/IPv4](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/7550287951/p21208.png)

    5.  Select **Obtain an IP address automatically** and **Obtain DNS server address automatically**.

        ![DNS](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/7550287951/p21209.png)

    6.  Click **OK**.
-   Mac: Configure a dynamic IP address for the Mac client.
    1.  On the desktop, click **System Preferences**, and then click **Network** in the Internet & Network section.
    2.  Click the connected network, and then click **Advanced**.
    3.  On the Ethernet page, click the **TCP/IP** tab.
    4.  From the **Configure IPv4** drop-down list, select **Using DHCP**.

        ![DHCP](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/8550287951/p21226.png)


## Step 2: Set the password

If this is your first time logging on to the web console, you must set the logon password.

**Note:** Before you log on to the web console, make sure that the following requirements are met:

-   The SAG device is powered on.
-   DHCP is enabled on the on-premises client. For more information, see [Step 1: Configure the on-premises client](#section_ja0_y8g_0bz).

1.  A LAN port of the SAG device is connected to the on-premises computer.

2.  Open the browser on the connected on-premises computer and enter `192.168.88.1` in the address bar.

    **Note:**

    -   If the LAN port uses a static IP address, enter the static IP address in the address bar.
    -   If the LAN port uses a dynamic IP address, you have configured CIDR blocks in the SAG console, the WAN port has enabled DHCP, and the CLOUD indicator is on when the network cable is connected, enter the first IP address of the first CIDR block configured in the SAG console.

        For example, if the first CIDR block you specified is 172.16.0.0/16, enter 172.16.0.1 in the address bar.

    -   If neither the LAN port nor the console is configured, you can enter the default address to log on to the web console.
        -   If you are using version 1.0.x, enter `192.168.0.1`.
        -   If you are using version 2.0.x, enter `192.168.88.1`.
3.  If this is your first time logging on to the web console, you must set the logon password.

    Keep your password confidential. If you forget your password, press the reset button on your device to clear the password.

4.  Log on to the web console.


## Step 3: Configure the SAG-1000 device

After you log on to the web console of the SAG-1000 device, you can configure the device. SAG-100WM devices provide multiple features to meet your requirements in different deployment scenarios. For more information about how to connect private networks to Alibaba Cloud through SAG-100WM devices, see [Deploy an SAG-100WM device](/intl.en-US/Configuration Guide/Deploy an SAG-100WM device.md).

1.  Configure a WAN port.

    1.  In the top navigation bar of the web console, click **Setting**.

    2.  Click **WAN** to configure a WAN port.

        By default, the connection type of the WAN port on an SAG-100WM device is **Dynamic IP**. The IP address of a WAN port is automatically obtained by the device that is connected to the WAN port.

        **Note:** You can configure a WAN port as needed. For more information about the parameters of the WAN port, see [Configure a WAN port](/intl.en-US/Configuration Guide/Manage devices/Manage devices/Configure a WAN port.md).

2.  Configure a LAN port.

    1.  In the top navigation bar of the web console, click **Setting**.

    2.  Click **LAN** to configure a LAN port.

        -   Wired network configurations.

            By default, the connection type of the LAN port on an SAG-100WM device is **Dynamic IP**. The IP address of a device connected to the LAN port is automatically obtained by DHCP. You can configure a LAN port as needed. For more information about the parameters of the LAN port, see [Configure a LAN port](/intl.en-US/Configuration Guide/Manage devices/Manage devices/Configure a LAN port.md).

            When you configure the LAN ports in the web console, if the connection type of the LAN port is **Dynamic IP**, the SAG device allows you to enter custom private CIDR blocks.

            -   **Unselected**: allows you to enter a custom IP address for the port and set a custom Dynamic Host Configuration Protocol \(DHCP\) address pool.
            -   **Custom Segment**: allows you to enter custom CIDR blocks. The system automatically allocates an IP address and DHCP address pool for the LAN port. You can manually modify the allocated IP address.
            -   If you have configured on-premises routes in the SAG console, the CIDR blocks are automatically displayed. You can allocate IP addresses as needed.
        -   Wireless LAN configurations.

            By default, the wireless LAN feature is disabled. For more information about how to enable the wireless LAN feature, see [Enable wireless connections](/intl.en-US/Configuration Guide/Manage devices/Manage devices/Manage routes/Enable wireless connections.md).

3.  Configure the routes.

    1.  In the top navigation bar of the web console, click **Setting**.

    2.  Click **Route** to configure the static routes.

        For more information about how to configure routes, see [Add a static route](/intl.en-US/Configuration Guide/Manage devices/Manage devices/Manage routes/Add a static route.md), [Configure OSPF routing](/intl.en-US/Configuration Guide/Manage devices/Manage devices/Manage routes/Configure OSPF routing.md), and [Configure BGP routing](/intl.en-US/Configuration Guide/Manage devices/Manage devices/Manage routes/Configure BGP routing.md).

        **Note:** SAG-100WM devices of version 2.0.x allow you to configure OSPF and BGP dynamic routing only in the web console instead of the Alibaba Cloud Management console.


## Optional. Step 4: High availability \(HA\) configurations

SAG-100WM devices support HA.

1.  In the top navigation bar of the web console, click **Setting**.

2.  Click **HA** to configure HA.

    SAG-100WM devices support high availability to continue to provide services when the active SAG device fails to work. For more information about the parameters, see [Configure HA for SAG devices](/intl.en-US/Configuration Guide/Manage devices/Manage devices/Configure HA for SAG devices.md).


