# Deploy two SAG devices in inline mode and enable DHCP on LAN ports

This topic describes how to deploy two Smart Access Gateway \(SAG\) devices in inline mode and enable Dynamic Host Configuration Protocol \(DHCP\) on the LAN ports. This way, you can connect private networks to Alibaba Cloud and improve the availability of your networks.

-   A Virtual Private Cloud \(VPC\) network is created. For more information, see [Create a VPC](/intl.en-US/VPCs and VSwitches/VPC management/Create a VPC.md).
-   A Cloud Enterprise Network \(CEN\) instance is created and associated with the VPC network. For more information, see [Create a CEN instance]().

In this example, an enterprise has created a VPC network in China \(Beijing\) and has deployed services in the VPC network. The enterprise wants to connect private networks to Alibaba Cloud through SAG devices. The enterprise wants to deploy two SAG-1000 devices in inline mode. The enterprise also wants to enable DHCP on the LAN ports of the SAG devices. This way, the enterprise can manage and dynamically assign IP addresses to the client side, and operations and maintenance \(O&M\) workloads are reduced. The enterprise also wants to enable the DHCP failover and high availability \(HA\) features of the SAG devices. This allows the enterprise to switch over to the standby device when the active device is faulty, which improves the network availability.

![Architecture](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/8997631061/p101679.png)

## Subnetting

The following table describes the IP addresses and CIDR blocks in this example. If you want to use your own IP addresses and CIDR blocks, make sure that the IP addresses or CIDR blocks do not overlap with each other.

|Item|Subnetting|
|----|----------|
|VPC network in China \(Beijing\)|Private CIDR block: 10.0.0.0/16|
|Internet-facing router|Port G1: 192.168.100.2/30|
|Port G2: 192.168.200.2/30|
|Active SAG device|-   WAN port 5: uses a static IP address
    -   Port IP address: 192.168.100.1/30
    -   Gateway: 192.168.100.2
-   LAN port 4: uses a dynamic IP address
    -   Port IP address: 192.168.50.1/24
    -   DHCP IP address pool: 192.168.50.3 to 192.168.50.253
    -   DHCP failover is enabled
    -   HA is enabled: The virtual IP address is 192.168.50.254 |
|Standby SAG device|-   WAN port 5: uses a static IP address
    -   Port IP address: 192.168.200.1/30
    -   Gateway: 192.168.200.2
-   LAN port 4: uses a dynamic IP address
    -   Port IP address: 192.168.50.2/24
    -   DHCP IP address pool: 192.168.50.3 to 192.168.50.253
    -   DHCP failover is enabled
    -   HA is enabled: The virtual IP address is 192.168.50.254 |
|Layer 2 switch|-   Connect port G11 to LAN port 4 of the active SAG device
-   Connect port G12 to LAN port 4 of the standby SAG device |
|Private networks|Private CIDR block: 192.168.50.0/24|

## Configuration procedure

![Configuration procedure](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9997631061/p162736.png)

## Step 1: Purchase SAG devices

After you purchase SAG devices in the SAG console, Alibaba Cloud delivers the devices to the specified address and creates SAG instances to help you facilitate network management.

**Note:** To use SAG devices outside mainland China, you must purchase SAG devices from third-party vendors. For more information, see [Purchase an SAG device](/intl.en-US/Pricing/Purchase an SAG device.md).

1.  Log on to the [SAG console](https://smartag.console.aliyun.com).

2.  On the Smart Access Gateway page, click **Purchase SAG**.

3.  Select **SAG \(CPE\)**.

4.  Set the following parameters and click **Buy Now**.

    -   **Area**: Select the area where the SAG device will be deployed. **Mainland China** is selected in this example.
    -   **Device Spec**: Select the type of the SAG device. **SAG-1000** is selected in this example.
    -   **Have SAG Devices Already**: Select whether you already have SAG devices. **No** is selected in this example.
    -   **Edition**: Select the edition of the SAG device. **Standard** is selected in this example.
    -   **Quantity**: Select the number of SAG devices that you want to purchase. **2** is selected in this example.
    -   **Area**: Select the area where the SAG bandwidth will be used. This area must be the same as that of the SAG devices and cannot be modified.
    -   **Instance Name**: Specify a name for the SAG instance.

        The name must be 2 to 128 characters in length, and can contain digits, periods \(.\), hyphens \(-\), and underscores \(\_\). It must start with a letter or a Chinese character.

    -   **Peak Bandwidth**: Select the maximum bandwidth for network connections. **50 Mbps** is selected in this example.
    -   **Subscription Duration**: Select the duration of the subscription.
5.  Confirm the order information and click **Confirm Purchase**.

6.  In the Address dialog box, enter the recipient address and click **Order Now**.

7.  On the Pay page, select a payment method and complete the payment.


You can check whether the order has been placed on the Smart Access Gateway page. The SAG devices will be shipped within two business days. If the shipping is overdue, you can[submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.15120809.nav-right.dticket.130266ebEB92in#/ticket/add/?productId=1308)to view the shipping status.

![View the status](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/5323660061/p101651.png)

## Step 2: Activate the SAG devices

After you receive the SAG devices, check whether you have received all the accessories. For more information, see [Descriptions of an SAG-1000 device](/intl.en-US/Smart Access Gateway/SAG-1000 configurations/Descriptions of an SAG-1000 device.md).

1.  Log on to the [SAG console](https://smartag.console.aliyun.com/).

2.  In the top navigation bar, select the region where the SAG instance is deployed.

3.  On the Smart Access Gateway page, find the SAG instance.

4.  In the **Actions** column, click **Activate**.

5.  In the Activate dialog box, click **OK**.

6.  Click the instance ID to go to the details page where you can view the serial number of the SAG device.

    **Note:**

    -   The SAG device with a larger serial number is the active device and the other is the standby device. For more information, log on to the SAG console.
    -   If you purchase the SAG devices from a third-party vendor, you must manually associate the SAG devices with the SAG instances. For more information, see [Add a device](/intl.en-US/Configuration Guide/Manage devices/Associate SAG devices with SAG instances/Add a device.md). When you manually associate the SAG devices with the SAG instances, the first associated SAG device is the active device by default.
7.  After you activate the SAG devices, you must connect them to your private network based on the following topology:

    For the active SAG device:

    -   Use a network cable to connect WAN port 5 of the SAG device to port G1 of the Internet-facing router.
    -   Use a network cable to connect LAN port 4 of the SAG device to port G11 of the Layer 2 switch.
    For the standby SAG device:

    -   Use a network cable to connect WAN port 5 of the SAG device to port G2 of the Internet-facing router.
    -   Use a network cable to connect LAN port 4 of the SAG device to port G12 of the Layer 2 switch.

## Step 3: Configure the SAG devices

You must log on to the web console to configure the SAG devices. Before you begin, make sure that the devices are started, the 4G networks work as expected, and the devices are connected to Alibaba Cloud.

1.  You can use a network cable to connect port 2 of the active SAG device to your computer and log on to the web console. For more information, see [Step 1: Configure the local client](/intl.en-US/Smart Access Gateway/SAG-1000 configurations/Web configurations for SAG-1000 devices.md) and [Step 2: Set the password](/intl.en-US/Smart Access Gateway/SAG-1000 configurations/Web configurations for SAG-1000 devices.md).

2.  Assign port roles

    **Note:** By default, port 5 is the WAN port and port 4 is the LAN port. If your system uses the default settings, you can skip this step. If the settings are modified, you must perform the following steps to reassign the roles.

    1.  In the web console, click **Settings**.

    2.  In the left-side navigation pane, click **Port Alloc**.

    3.  On the Port Alloc page, find the port and select a role.

        ![Assign port roles](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/6537811061/p162661.png)

        -   **Port 5**: Select **WAN**.
        -   **Port 4**: Select **LAN**.
    4.  Click **OK**.

3.  Configure the WAN port.

    1.  In the left-side navigation pane, click **WAN**.

    2.  On the WAN page, click **Port 5 \(WAN\)**.

        ![Configure the WAN port](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/6537811061/p162314.png)

        -   **Link Type**: Select **Static**.
        -   **IP**: Enter the IP address of the WAN port. 192.168.100.1 is used in this example.
        -   **Mask**: Enter the subnet mask of the WAN port IP address. 255.255.255.252 is used in this example.
        -   **Gateway**: Enter the IP address of the gateway. 192.168.100.2 is used in this example.

            **Note:** After the parameter is set, a default route is added to the SAG device.

    3.  Click **OK**.

4.  Configure the LAN port.

    1.  In the left-side navigation pane, click **LAN**.

    2.  On the LAN page, click **Port 4 \(LAN\)**.

        ![Configure the LAN port](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/6537811061/p162320.png)

        -   **Link Type**: Select **Dynamic IP**.
        -   **Private Segment**: Select **Custom Segment** and enter 192.168.50.0/24.
        -   **Interface IP**: Enter the IP address of the LAN port. 192.168.50.1 is used in this example.
        -   **DHCP Start IP**: 192.168.50.3 is used in this example.
        -   **DHCP End IP**: 192.168.50.253 is used in this example.
        -   **Address ExpireIn**: 48 hours.
        -   **DHCP Failover**: enabled.

            **Note:** To use the DHCP failover feature, you must also enable the HA feature. The HA virtual IP address functions as the IP address of the gateway and is automatically advertised to the client side. After you enable the DHCP failover and HA features for both the active and standby devices, you can switch over to the standby device when the active device is faulty. This enables the availability of your networks.

    3.  Click **OK**.

5.  Enable the HA feature.

    1.  In the left-side navigation pane, click **HA**.

    2.  On the HA page, select **Static HA**.

        ![Configure HA](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/6537811061/p162323.png)

        -   **Port**: **Port 4 \(LAN\)** is used in this example.
        -   **Virtual IP**: the virtual IP address. 192.168.50.254 is used in this example.
    3.  Click **OK**.

6.  Configure the standby SAG device.

    Refer to the logon configurations of the active SAG device and configure the standby SAG device based on the following information:

    -   Configure WAN port 5:
        -   **Link Type**: Select **Static**.
        -   **IP**: The IP address of the WAN port. 192.168.200.1 is used in this example.
        -   **Subnet Mask**: Enter the subnet mask of the WAN port IP address. 255.255.255.252 is used in this example.
        -   **Gateway**: Enter the IP address of the gateway. 192.168.200.2 is used in this example.

            **Note:** After the parameter is set, a default route is added to the SAG device.

    -   Configure LAN port 4:
        -   **Connection Type**: Select **Static IP**.
        -   **Private Segment**: Select **Custom Segment** and enter 192.168.50.0/24.
        -   **Interface IP**: the IP address of the LAN port. 192.168.50.2 is used in this example.
        -   **DHCP Start IP**: 192.168.50.3 is used in this example.
        -   **DHCP End IP**: 192.168.50.253 is used in this example.
        -   **Address ExpireIn**: 48 hours.
        -   **DHCP Failover**: enabled.
    -   Configure HA: Select **Static HA**.
        -   **Port**: **Port 4 \(LAN\)** is used in this example.
        -   **Virtual IP**: the virtual IP address. 192.168.50.254 is used in this example.

## Step 4: Advertise routes to Alibaba Cloud

To connect private networks to Alibaba Cloud, you must advertise routes to Alibaba Cloud.

1.  Log on to the [SAG console](https://smartag.console.aliyun.com/).

2.  In the top navigation bar, select the region.

3.  On the Smart Access Gateway page, click the ID of the SAG instance.

4.  On the page that appears, click the **Network Configuration** tab.

5.  In the left-side navigation tree, click **Methods to Synchronize with On-premises Routes**.

6.  Select **Static Routing**, click **Add Static Route** to add a CIDR block, and then click **OK**.

    192.168.50.0/24 is used in this example.

    ![Advertise routes to Alibaba Cloud](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/7537811061/p162311.png)


## Step 5: Set up network connections in the console

After you complete the preceding steps, you must set up network connections in the cloud.

1.  Create a Cloud Connect Network \(CCN\) instance.

    1.  Log on to the [SAG console](https://smartag.console.aliyun.com).

    2.  In the top navigation bar, select **Mainland China**.

        The CCN instance and SAG instance must be deployed in the same region.

    3.  In the left-side navigation pane, click **CCN**.

    4.  On the CCN page, click **Create CCN Instance**.

    5.  In the Create CCN Instance pane, specify a name for the CCN instance and click **OK**.

        The name must be 2 to 100 characters in length and can contain digits, underscores \(\_\), and hyphens \(-\). It must start with a letter or a Chinese character.

        ![Create a CCN instance](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/6323660061/p76961.png)

2.  Associate the SAG instance with a CCN instance.

    1.  In the left-side navigation pane, click **Smart Access Gateway**.

    2.  On the Smart Access Gateway page, find the SAG instance and click **Network Configuration** in the **Actions** column.

    3.  In the left-side navigation tree, click **Network Instance Details**.

    4.  On the Network Instance Details tab, click **Attach Network**, select the CCN instance you created, and then click **OK**.

        ![The Attach Network tab](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/6323660061/p132840.png)

3.  Associate the CCN instance with a CEN instance.

    After the CCN instance is associated with the CEN instance, SAG devices associated with the CCN instance can communicate with VPC networks associated with the CEN instance.

    1.  In the left-side navigation pane, click **CCN**.

    2.  Find the CCN instance and click **Bind CEN Instance** in the **Actions** column.

    3.  In the Bind CEN Instance pane, select **Existing CEN**, select the CCN instance from the drop-down list, and then click **OK**.

        ![Select a CEN instance](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/6323660061/p63012.png)

4.  Create a security group rule.

    You must create a security group rule for the Elastic Compute Service \(ECS\) instance to allow the private CIDR block 192.168.50.0/24 to access resources on the CES instance. For more information, see [Add security group rules](/intl.en-US/Security/Security groups/Add security group rules.md).


## Step 6: Test the connectivity

After you complete the preceding steps, you can test the connectivity between the VPC network and your private networks.

1.  Before you test the connectivity, you must configure the network interface controller \(NIC\) of your on-premises computer to automatically obtain an IP address. For more information, see the system manuals of your on-premises computer. The Windows operating system is used in the following example.

    ![Automatically obtain an IP address](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/7537811061/p162415.png)

2.  Select Automatically obtain an IP address. Then, the SAG device automatically assigns an IP address to your on-premises computer. After the SAG device assigns an IP address to your on-premises computer, you can test the connectivity between the VPC network and your private networks.


