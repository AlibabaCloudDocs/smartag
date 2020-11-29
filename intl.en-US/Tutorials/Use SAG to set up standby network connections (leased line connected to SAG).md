# Use SAG to set up standby network connections \(leased line connected to SAG\)

This topic describes how to deploy a Smart Access Gateway \(SAG\) device to set up standby network connections between an on-premises network and Alibaba Cloud. In this scenario, a leased line provides the active connection. This helps you build a high availability \(HA\) hybrid cloud.

-   A virtual private cloud \(VPC\) is created in the China \(Beijing\) region. For more information, see [Create a VPC](/intl.en-US/VPCs and VSwitches/VPC management/Create a VPC.md).
-   A Cloud Enterprise Network \(CEN\) instance is created and associated with the VPC in the China \(Beijing\) region. For more information, see [Create a CEN instance]().
-   A leased line is connected to the on-premises network in the China \(Beijing\) region and a virtual border router \(VBR\) is created. For more information, see [Create a dedicated physical connection](/intl.en-US/Physical Connection/Dedicated physical connection/Create a dedicated physical connection.md) or [Establish a shared physical connection](/intl.en-US/Physical Connection/Establish a shared physical connection.md).

The following figure shows the network topology used in this topic. For example, an enterprise has created a VPC in the China \(Beijing\) region and deployed services in the VPC. To establish HA connections between the on-premises network and cloud resources, the enterprise plans to use an SAG device to provide standby connections, while a leased line provides active connections.

-   To avoid changes in the network topology, an SAG-1000 device is deployed in one-arm mode to connect the on-premises network to Alibaba Cloud. Only the SAG-1000 device model supports leased lines.
-   The leased line is connected to the leased line port of the SAG device. The SAG device uses the leased line and CCN to connect the on-premises network to Alibaba Cloud. In this scenario, the CCN connection is established over the Internet. When either the leased line connection or the CCN connection is malfunctioning, the other connection takes over.
-   The SAG device and VBR use BGP to learn and advertise routes. This facilitates network management and operations and maintenance \(O&M\).
-   The SAG instance is associated with a CCN instance and the VBR. The VBR and CCN instance are associated with the same CEN instance. The SAG device is connected to the VPC through the CEN instance.
-   In this example, network traffic is transmitted in the following directions:

    When the SAG device is associated with the CCN instance and VBR, CEN chooses the leased line by default. By default, the CEN instance learns and advertises routes through the leased line. When the leased line is malfunctioning, the CCN instance takes over. Specifically, outbound and inbound traffic are transmitted through the leased line by default. When the leased line is malfunctioning, outbound and inbound traffic are transmitted through the CCN instance.


![Best practices](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7243666061/p101686.png)

## Configuration procedure

![Procedure](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7892666061/p170866.png)

## Subnetting

The following table describes the subnetting in this example. We recommend that you plan the subnetting based on your business requirements and ensure that the CIDR blocks do not overlap with each other.

|Item|Subnetting|
|----|----------|
|On-premises network|Private CIDR block: 172.16.0.0/12.|
|-   Port G11 of the Layer 3 switch: 192.168.100.2/30.
-   Port G2 of the Layer 3 switch: 192.168.80.2/30. |
|Port G1 of the Internet-facing router: 192.168.80.1/30.|
|SAG device|-   WAN port \(port 5\): 192.168.100.1/30. IP address of the gateway: 192.168.100.2.
-   Leased line port \(port 1\): 192.168.110.1/30. VLAN ID: 0. |
|BGP:-   Autonomous system \(AS\) number: 65435
-   Router ID: 192.168.2.2
-   Keepalive time: 60 seconds
-   Hold Time: 180 seconds
-   BGP-enabled port: leased line port |
|VBR|-   Alibaba Cloud-side IP address: 192.168.110.2/30
-   Client-side IP address \(Layer 3 switch-side in this example\): 192.168.110.1/30
-   VLAN: 0 |
|VPC in the China \(Beijing\) region|VPC CIDR block: 10.0.0.0/16|

## Step 1: Purchase an SAG device

After you place an order in the SAG console, Alibaba Cloud delivers the SAG device to the specified address and creates an SAG instance to facilitate the management of the device.

**Note:** If the area where the SAG device is used is outside mainland China, you must purchase the device from a third-party vendor that is authorized by Alibaba Cloud. For more information, see [Purchase an SAG device](/intl.en-US/Pricing/Purchase an SAG device.md).

1.  Log on to the [SAG console](https://smartag.console.aliyun.com).

2.  On the Smart Access Gateway page, click **Purchase SAG**.

3.  Select **Create SAG \(CPE\)**.

4.  Set the following parameters and click **Buy Now**:

    -   **Area**: Select the area where the SAG devices will be deployed. **Mainland China** is selected in this example.
    -   **Device Spec**: Select the model of the SAG device. **SAG-1000** is selected in this example.
    -   **Have SAG Devices Already**: Select whether you already have an SAG device. **No** is selected in this example.
    -   **Edition**: Select the edition of the SAG device. **Standard** is selected in this example by default.
    -   **Quantity**: Select the number of SAG devices that you want to purchase. **1** is selected in this example.
    -   **Area**: Select the area where the bandwidth will be used. The area is the same as that of the SAG device and cannot be changed.
    -   **Name**: Specify a name for the SAG instance.

        The name must be 2 to 128 characters in length, and can contain digits, periods \(.\), hyphens \(-\), and underscores \(\_\). It must start with a letter or a Chinese character.

    -   **Peak Bandwidth**: Specify the maximum bandwidth value. **50 Mbps** is specified in this example.
    -   **Subscription Duration**: Specify the subscription duration of the bandwidth resources.
5.  Confirm the order information and click **Confirm Purchase**.

6.  In the Shipping Address dialog box, enter the recipient address and click **Buy Now**.

7.  On the Pay page, select a payment method and complete the payment.


You can check whether the order has been placed on the Smart Access Gateway page. After the order is placed, it will be shipped within two business days. If your order is not shipped as expected, you can [submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.15120809.nav-right.dticket.130266ebEB92in#/ticket/add/?productId=1308) to query the shipping status.

![The order status](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5323660061/p101651.png)

## Step 2: Activate the SAG device

After you receive the SAG package, check whether you have received all the items. For more information, see [Descriptions of an SAG-1000 device](/intl.en-US/Smart Access Gateway/SAG-1000 usage instructions/Descriptions of an SAG-1000 device.md).

1.  Log on to the [SAG console](https://smartag.console.aliyun.com/).

2.  In the top menu bar, select the region.

3.  On the Smart Access Gateway page, find the SAG instance.

4.  In the **Actions** column, click **Activate**.

5.  In the Activate dialog box, click **OK**.

6.  After you activate the SAG device, connect it to the on-premises network based on the preceding network topology.

    -   Use a network cable to connect the WAN port \(port 5\) of the SAG device to port G11 of the Layer 3 switch.
    -   Connect the Express Connect leased line to the leased line port \(port 1\) of the SAG device.
7.  If the SAG device is purchased from a third-party vendor, you must manually associate the SAG device with the SAG instance. For more information, see [Add a device](/intl.en-US/Configuration Guide/Manage devices/Associate SAG devices with SAG instances/Add a device.md).


## Step 3: Configure the SAG device

After the SAG devices are connected to your on-premises network, you can configure the device ports in the SAG console.

Before you begin, make sure that the SAG device is started, the 4G network works as expected, and the SAG device is connected to Alibaba Cloud.

1.  Log on to the [SAG console](https://smartag.console.aliyun.com/).

2.  Assign port roles.

    By default, port 5 functions as the WAN port. You must assign a leased line port to the SAG device. For more information, see [Assign a role to a port](/intl.en-US/Configuration Guide/Manage devices/Manage devices/Assign a role to a port.md). In this example, port 1 is assigned as the leased line port.

3.  Configure the WAN port.

    1.  Log on to the [SAG console](https://smartag.console.aliyun.com/).

    2.  In the top menu bar, select the region.

    3.  On the Smart Access Gateway page, click the ID of the SAG instance.

    4.  On the instance details page, click the **Device Management** tab.

    5.  In the left-side navigation tree, click **Manage WAN Ports**.

    6.  In the WAN \(Port 5\) section, click **Edit**.

    7.  In the Configure WAN \(Port 5\) dialog box, set the following parameters and click **OK**.

        -   **Link Type**: Select **Static**.
        -   **IP**: The IP address of the WAN port. 192.168.100.1 is used in this example.
        -   **Subnet Mask**: Enter the subnet mask of the WAN port IP address. 255.255.255.252 is used in this example.
        -   **Gateway**: Enter the IP address of the gateway. 192.168.100.2 is used in this example.

            **Note:** After the parameter is set, a default route is added to the SAG device.

4.  Configure the leased line port

    1.  In the left-side navigation tree, click **Manage WAN Ports**.

    2.  On the Manage Leased Lines page. Click **Port1 \(Leased Line\)**.

    3.  On the page that appears, click **Edit**.

    4.  In the Modify dialog box, set the following parameters and click **OK**. For more information about leased lines, see [Configure a leased line port](/intl.en-US/Configuration Guide/Manage devices/Manage devices/Configure a leased line port.md).

        ![Configure the leased line port](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/1483094061/p101790.png)

        -   **IP**: Enter the IP address of the leased line port. 192.168.110.1 is used in this example.
        -   **Subnet Mask**: Enter the subnet mask of the IP address of the leased line port. 255.255.255.252 is used in this example.
        -   **Port**: **Port1 \(Leased Line\)** is selected by default.
        -   **VLAN**: Specify the VLAN number of the leased line port. 0 is used in this example. 0 indicates that the leased line port functions as a physical port instead of a virtual port.

            **Note:**

            The leased line port can work in one of the following modes:

            -   Physical mode: The leased line port functions as an independent port and the VLAN number is 0.
            -   Virtual mode: The leased line port functions as multiple sub ports. Each VLAN number indicates a sub port. If the VLAN number is not 0, the virtual mode is enabled. Valid values of the VLAN number: 1 to 4094.
            The VLAN number of the leased line port must be the same as that of the leased line peer.

5.  Configure BGP.

    1.  In the left-side navigation tree, click **Manage WAN Ports**.

    2.  In the **BGP Protocol Settings** section, click **Edit**.

    3.  In the Configure BGP Route Protocol dialog box, set the following parameters and click **OK**.

        -   **Local AS**: 65435 is used in this example.
        -   **Router ID**: 192.168.2.2 is used in this example.
        -   **Hold Time**: 180 is used in this example.
        -   **Keep Alive**: 60 is used in this example.
6.  Enable BGP for the WAN port.

    **Note:** You can enable BGP for the leased line port of an SAG device and configure BGP only in the SAG console, instead of the web console.

    1.  In the **Dynamic Routing Settings** section, select **Enable BGP Protocol**.

    2.  In the **Change Routing Protocol** message, click **OK**.

    3.  Find Port1 \(Leased Line\) in the**Leased Line Dynamic Routing Settings** section, and click **Edit** in the **Actions** column.

    4.  In the **Modify BGP Dynamic Routing Settings** dialog box, select **Enable BGP**, set the Peer IP and Peer AS, and then click **OK**.

        Set the Peer IP and Peer AS to the IP address of port G11 and the BGP AS number of the peer switch.

        -   **Peer AS**: 45104 is used in this example.
        -   **Peer IP**: 192.168.110.2 is used in this example.
    ![Configure BGP](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/1483094061/p170679.png)

7.  Advertise routes to Alibaba Cloud

    1.  On the SAG instance details page, click the **Network Configuration** tab.

    2.  In the left-side navigation tree, click **Methods to Synchronize with On-premises Routes**.

    3.  Select **Static Routing**, click **Add Static Route**, and then click **OK**.

        Enter the CIDR block used to route network traffic from Alibaba Cloud to the on-premises network. 172.16.0.0/12 is used in this example.

        ![On-premises route 2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2172240061/p77167.png)


## Step 4: Configure the VBR

You must configure the VBR in the Express Connect console to establish the BGP peer relationship between the VBR and the SAG device.

1.  Create a BGP group.

    1.  Log on to the [Express Connect console](https://expressconnectnext.console.aliyun.com).

    2.  In the top menu bar, select the region.

    3.  In the left-side navigation pane, choose **Virtual Border Routers \(VBRs\)** \> **Virtual Border Routers \(VBRs\)**.

    4.  On the Virtual Border Routers \(VBRs\) page, click the ID of the VBR.

    5.  On the details page, click the **BGP Groups** tab.

    6.  On the **BGP Groups** tab, click **Create BGP Group** and set the following parameters:

        -   **Name**: Enter a name for the BGP group. test is used in this example.
        -   **Peer ASN**: Enter the AS number of the SAG device. 65435 is used in this example.
        -   **BGP Key**: Enter the key of the BGP group. This parameter is not set in this example.
        -   **Description**: Enter the description of the BGP group. SAGtest is used in this example.
    7.  Click **OK**.

2.  Configure the BGP neighbor.

    1.  On the VBR details page, click the **BGP Peers** tab.

    2.  On the **BGP Peers** tab, click **Create BGP Peer**.

    3.  In the **Create BGP Peer** dialog box, set the following parameters and click **OK**.

        -   **BGP Group**: Specify the BGP group to which you want to add the VBR and SAG device. The BGP group test is used in this example.
        -   **BGP peer IP address**: Enter the IP address of the BGP peer. The IP address of the leased line port of the SAG device. 192.168.110.1 is used in this example.
    ![Create a BGP neighbor](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2483094061/p170796.png)


## Step 5: Configure the switch and router

In this step, you must configure the peer switch and Internet-facing router for the SAG device. Switches and routers used in this example may be different from yours. For more information, see the manuals issued by your providers.

1.  Configure routes for the Layer 3 switch.

    ```
    interface GigabitEthernet 0/11
    no switchport
    ip address 192.168.100.2 255.255.255.252      #The IP address of the peer switch of the SAG device
    
    ip route 10.0.0.0 255.255.0.0 192.168.100.1  #The route to the VPC in the China (Beijing) region
     
    ip route 0.0.0.0 0.0.0.0 192.168.80.1        #The route to the Internet               
    ```

2.  Configure routes for the Internet-facing router.

    ```
    ip route 192.168.100.0 255.255.255.252 192.168.80.2 #The route to the SAG device          
    ```


## Step 6: Set up network connections

After you configure the SAG device, you must set up network connections to connect the on-premises network to Alibaba Cloud.

1.  Create a CCN instance.

    1.  Log on to the [SAG console](https://smartag.console.aliyun.com).

    2.  In the top menu bar, select **Mainland China**.

        The CCN instance and SAG instance must be deployed in the same region.

    3.  In the left-side navigation pane, click **CCN**.

    4.  On the CCN page, click **Create CCN Instance**.

    5.  In the Create CCN Instance pane, specify a name for the CCN instance and click **OK**.

        The name must be 2 to 100 characters in length, and can contain digits, underscores \(\_\), and hyphens \(-\). It must start with a letter.

        ![Create a CCN instance](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6323660061/p76961.png)

2.  Associate the SAG instance with a CCN instance.

    1.  In the left-side navigation pane, click **Smart Access Gateway**.

    2.  On the Smart Access Gateway page, find the SAG instance and click **Network Configuration** in the **Actions** column.

    3.  In the left-side navigation tree, click **Network Instance Details**.

    4.  On the Network Instance Details tab, click **Attach Network**, select the CCN instance you created, and then click **OK**.

        ![The Attach Network tab](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6323660061/p132840.png)

    5.  Repeat the preceding steps to associate the VBR with the SAG instance. For more information, see [Attach a network instance](/intl.en-US/Configuration Guide/Configure networks in the cloud/Attach a network instance.md).

        If the SAG instance is associated with the CCN instance and the VBR, the on-premises network is connected to the Alibaba Cloud through the leased line by default. When the leased line is malfunctioning, the on-premises network is connected to Alibaba Cloud through CCN. In this case, the connection is encrypted and established over the Internet.

3.  Attach the CCN instance and VBR to the CEN instance. For more information, see [Attach networks]().

    Then, the on-premises network that is connected to the SAG device can communicate with the VPC that is attached to the CEN instance.

    **Note:** If the on-premises network, VBR, and VPC are not in the same region, you must purchase a bandwidth plan for the CEN instance and set cross-region bandwidth. This way, the on-premises network, VBR, and VPC can communicate with each other. For more information, see [Purchase a bandwidth package]() and [Configure a cross-region connection bandwidth]().

4.  Create a security group rule.

    You must create a security group rule for the ECS instance in the VPC to allow the private CIDR block 172.16.0.0/12 to access resources deployed on the ECS instance. For more information, see [Add security group rules](/intl.en-US/Security/Security groups/Add security group rules.md).


## Step 7: Test the connectivity

1.  After you complete the preceding steps, you can log on to the CEN console and view the route to the on-premises network from the VPC. For more information, see [View CEN routes in the CEN console]().

2.  You can use the on-premises client to access the cloud resources in the connected VPC to test the connectivity.


