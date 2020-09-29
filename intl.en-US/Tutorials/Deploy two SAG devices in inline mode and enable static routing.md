# Deploy two SAG devices in inline mode and enable static routing

This topic describes how to deploy two Smart Access Gateway \(SAG\) devices in inline mode and enable static routing to connect a private network to Alibaba Cloud. This deployment mode improves network availability.

The following figure shows the topology of the private network. A Layer 3 switch is connected to two Layer 2 switches. Local clients and servers are connected to the Layer 2 switches. Two SAG devices are connected to the Layer 3 switch in inline mode to establish network connections between the private network and Alibaba Cloud. The two SAG devices serve as a standby device for each other.

![Device-based HA](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9351731061/p101679.png)

## Prerequisites

-   A Virtual Private Cloud \(VPC\) network is created in the China \(Beijing\) region. For more information, see [Create a VPC](/intl.en-US/VPCs and VSwitches/VPC management/Create a VPC.md).
-   A Cloud Enterprise Network \(CEN\) instance is created and associated with the VPC network in the China \(Beijing\) region. For more information, see [Create a CEN instance]().

## Subnetting

The following CIDR blocks are used in this example. When you allocate CIDR blocks based on your actual requirements, make sure that the CIDR blocks do not overlap with each other.

|Object|IP Address|
|------|----------|
|VPC network in the China \(Beijing\) region|10.0.0.0/16|
|Internet-facing router|Port G1: 192.168.100.2/30.|
|Port G2: 192.168.200.2/30.|
|SAG Device 1|-   WAN port \(port 5\): 192.168.100.1/30. Next hop: 192.168.100.2.
-   LAN port \(port 4\): 192.168.50.1/24. High availability \(HA\) is enabled and the virtual IP address is 192.168.50.254. |
|SAG Device 2|-   WAN port \(port 5\): 192.168.200.1/30. Next hop: 192.168.200.2.
-   LAN port \(port 4\): 192.168.50.3/24. HA is enabled and the virtual IP address is 192.168.50.254. |
|Layer 3 switch|-   Port G11: assigned to VLAN 10.
-   Port G12: assigned to VLAN 10.
-   VLAN 10: 192.168.50.2/24. |
|Private network|172.16.0.0/12.|

## Step 1: Purchase SAG devices

After you purchase SAG devices in the SAG console, Alibaba Cloud delivers the devices to the specified address and creates an SAG instance to help you facilitate network management.

1.  Log on to the [SAG console](https://smartag.console.aliyun.com).

2.  Set the following parameters.

    -   **Area**: Select the area where the SAG devices will be deployed. **Mainland China** is selected in this example.
    -   **Device Spec**: Select the type of the SAG device. **SAG-1000** is selected in this example.
    -   **Have SAG Devices Already**: Select whether you already have SAG devices. **No** is selected in this example.
    -   **Quantity**: Select the number of SAG devices that you want to purchase. **2** is selected in this example.
    -   **Area**: Select the area where the SAG bandwidth will be used. This area must be the same as that of the SAG devices and cannot be modified.
    -   **Instance Name**: Specify a name for the SAG instance.

        The name must be 2 to 128 characters in length and can contain digits, periods \(.\), hyphens \(-\), and underscores \(\_\). It must start with a letter or Chinese character.

    -   **Peak Bandwidth**: Select the maximum bandwidth for network connections. **30Mbps** is selected in this example.
    -   **Subscription Duration**: Select the duration of the subscription.
3.  After you set the preceding parameters, click **Buy Now**.

4.  Confirm the order information and click **Confirm Purchase**.

5.  In the Shipping Address dialog box that appears, enter the recipient address and then click **Buy Now**.

6.  On the Pay page that appears, click **Pay**.


You can check whether the order has been placed on the Smart Access Gateway page. The SAG devices will be shipped within two business days. If the order is not shipped within two business days, [submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.15120809.nav-right.dticket.130266ebEB92in#/ticket/add/?productId=1308) to query the shipping status.

![Query the shipping status](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/5323660061/p101651.png)

## Step 2: Activate the SAG devices

After you receive the SAG devices, check whether you have received all the accessories. For more information, see [Descriptions of an SAG-1000 device](/intl.en-US/Smart Access Gateway/SAG-1000 configurations/Descriptions of an SAG-1000 device.md).

1.  Log on to the [SAG console](https://smartag.console.aliyun.com/).

2.  On the Smart Access Gateway page, find the target SAG instance.

3.  In the **Actions** column, click **Activate**.

4.  Click the ID of the target SAG instance. On the instance details page, click the **Device Management** tab and enter the serial number of the device.

    ![Add the device](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/0779631061/p101760.png)

5.  Click **Add Device**.

6.  Repeat this step to associate the other SAG device with the SAG instance.


## Step 3: Connect the SAG devices to your private network

After you activate the SAG devices and associate them with the SAG instance, you must connect the devices to your private network.

Before you begin, make sure that the devices are activated, the 4G networks work as expected, and the devices are connected to Alibaba Cloud. Device 1 is used in this example. Repeat this step to connect Device 2 to your private network.

1.  Log on to the [SAG console](https://smartag.console.aliyun.com/).

2.  On the Smart Access Gateway page, find and click the target SAG instance.

3.  On the instance details page, click the **Device Management** tab.

4.  In the left-side navigation tree, click **Assign Port Roles**.

5.  In the Assign Port Roles section, find the target port and click **Edit** in the **Actions** column. Assign a role to the port and click **OK**.

    The WAN port \(port 5\) and LAN port \(port 4\) are used in this example. For more information about ports, see [Assign a role to a port](/intl.en-US/Configuration Guide/Manage devices/Manage devices/Assign a role to a port.md).

6.  Use a network cable to connect the WAN port \(port 5\) of the SAG device to port G1 of the Internet-facing router.

7.  Use a network cable to connect the LAN port \(port 4\) of the SAG device to port G11 of the Layer 3 switch.


## Step 4: Configure ports

After the SAG devices are connected to your private network, you can configure the device ports in the SAG console.

Device 1 is used in this example. Repeat this step to configure the ports of Device 2.

1.  Log on to the [SAG console](https://smartag.console.aliyun.com/).

2.  On the Smart Access Gateway page, click the ID of the target SAG instance.

3.  On the instance details page, click the **Device Management** tab.

4.  In the left-side navigation tree, click **Manage LAN Ports**.

5.  In the LAN \(Port 4\) section, click**Edit**.

6.  In the Configure LAN \(Port 4\) dialog box that appears, set the following parameters and click**OK**.

    Device 1:

    -   **Connection Type**: Select **Static IP**.
    -   **Port Address**: Enter the IP address of the LAN port. 192.168.50.1 is used in this example.
    -   **Subnet Mask**: Enter the subnet mask of the LAN port IP address. 255.255.255.0 is used in this example.
    Device 2:

    -   **Connection Type**: Select **Static IP**.
    -   **Port Address**: Enter the IP address of the LAN port. 192.168.50.3 is used in this example.
    -   **Subnet Mask**: Enter the subnet mask of the LAN port IP address. 255.255.255.0 is used in this example.
7.  In the left-side navigation tree, click **Manage WAN Ports**.

8.  In the WAN \(Port 5\) section, click**Edit**.

9.  In the Configure WAN \(Port 5\) dialog box that appears, set the following parameters and click**OK**.

    Device 1:

    -   **Connection Type**: Select **Static IP**.
    -   **IP Address**: Enter the IP address of the WAN port. 192.168.100.1 is used in this example.
    -   **Subnet Mask**: Enter the subnet mask of the WAN port IP address. 255.255.255.252 is used in this example.
    -   **Gateway**: Enter the IP address of the gateway. 192.168.100.2 is used in this example.
    Device 2:

    -   **Connection Type**: Select **Static IP**.
    -   **IP Address**: Enter the IP address of the WAN port. 192.168.200.1 is used in this example.
    -   **Subnet Mask**: Enter the subnet mask of the WAN port IP address. 255.255.255.252 is used in this example.
    -   **Gateway**: Enter the IP address of the gateway. 192.168.100.2 is used in this example.
    **Note:** After you configure the gateway, the SAG device generates a default route.


## Step 5: Configure routing methods

After you configure the WAN and LAN ports of the SAG devices, you must also configure the routing method that synchronizes local routes with Alibaba Cloud and specify static routes to route traffic from Alibaba Cloud to the private network.

Device 1 is used in this example. Repeat this step to configure a routing method for Device 2.

1.  On the Smart Access Gateway page, click the ID of the target SAG instance.

2.  On the instance details page, click the **Network Configuration** tab.

3.  In the left-side navigation tree, click **Methods to Synchronize with On-premises Routes**.

4.  Select **Static Routing**, click**Add Static Route** to add a CIDR block, and then click**OK**.

    Enter the CIDR block used to router network traffic from Alibaba Cloud to the private network. 172.16.0.0/12 is used in this example.

    ![Local route 2](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/2172240061/p77167.png)

5.  On the Instance Details page, click the**Device Management** tab.

6.  In the left-side navigation tree, click **Manage Routes** and then click**Add Static Route**.

7.  In the Add Static Route dialog box that appears, add a static route that routes traffic from Alibaba Cloud to the private network.

    |Parameter|Description|
    |---------|-----------|
    |Destination CIDR Block|Device 1: 172.16.0.0/12.

Device 2: 172.16.0.0/12. |
    |Next Hop|Device 1: 192.168.50.2.

Device 2: 192.168.50.2. |
    |Port|Select Port 4 \(LAN\) for both Device 1 and Device 2.|

    ![Add a static route](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/7181731061/p101763.png)


## Step 6: Configure HA

The HA feature is used in this example to address single point of failures \(SPOFs\).

Device 1 is used in this example. Repeat this step to configure HA for Device 2.

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com).

2.  Use either of the following method to go to the Device Management tab.

    -   Click the ID of the target SAG instance. On the instance details page, click the **Device Management** tab.
    -   Find the target SAG instance and choose **![The More icon](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/1975819951/p60575.png)** \> **Device Management** in the **Actions** column.
3.  On the Device Management tab, select the target device and click **Manage HA**.

4.  In the **HA Information** section, click ![The Edit icon](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/8181731061/p101779.png).

5.  In the Configure HA dialog box that appears, select an HA mode.

    The following table describes the parameters.

    |Parameter|Description|
    |---------|-----------|
    |**HA Mode**|Select **Static** for both Device 1 and Device 2.|
    |**Port**|Select LAN 4 for both Device 1 and Device 2.|
    |**Virtual IP**|Enter a virtual IP address for the SAG devices. 192.168.50.254 is used for both Device 1 and Device 2 in this example.|

6.  Click **Save**.


## Step 7: Configure the Layer 3 switch and Internet-facing router

The commands used to configure switches vary depending on the switch provider. For more information, see the manuals issued by your providers. A switch and router provided by Cisco are used in this example.

-   The Layer 3 switch

    **Note:** For each SAG device, the network type of ports using the OSPF protocol must be set to peer-to-peer \(P2P\). Otherwise, the SAG device cannot calculate routes correctly.

    ```
    Configure IP addresses for the ports:
    
    
    interface GigabitEthernet 0/12
    switchport access vlan 10                 Assign the LAN port of Device 1 to VLAN 10
    
    
    interface GigabitEthernet 0/14
    switchport access vlan 10                Assign the LAN port of Device 2 to VLAN 10
    
    interface  vlan 10
    ip address 192.168.50.2 255.255.255.0    The gateway IP address of the client
    
    ip route 0.0.0.0 0.0.0.0 192.168.50.254         The route to the Internet
                        
    ```

-   The Internet-facing router

    ```
    Configure static routes
    
    ip route 192.168.100.0 255.255.255.252  192.168.100.2 The route to Device 1.
    ip route 192.168.200.0 255.255.255.252  192.168.200.2 The route to Device 2.
                        
    ```


## Step 8: Set up network connections

After you configure the SAG devices, you must set up network connections to connect the private network to Alibaba Cloud.

1.  Create a Cloud Connect Network \(CCN\) instance.

    1.  Log on to the [SAG console](https://smartag.console.aliyun.com).

    2.  In the left-side navigation pane, click **CCN**.

    3.  On the CCN page, click **Create CCN Instance**.

    4.  In the Create CCN Instance pane that appears, specify a name for the CCN instance and click **OK**.

        The name must be 2 to 100 characters in length and can contain digits, underscores \(\_\), and hyphens \(-\). It must start with a letter or Chinese character.

        ![Create a CCN instance](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/6323660061/p76961.png)

2.  Set up network connections.

    1.  Log on to the [SAG console](https://smartag.console.aliyun.com).

    2.  On the Smart Access Gateway page, click the ID of the target SAG instance or click **Network Configuration** in the **Actions** column.

    3.  On the Network Instance Details tab, click **Attach Network**, select the CCN instance, and then click **OK**.

        ![Select the CCN instance](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/6910843951/p63008.png)

3.  Associate the CCN instance with a CEN instance.

    1.  Log on to the [SAG console](https://smartag.console.aliyun.com).

    2.  In the left-side navigation pane, click **CCN**.

    3.  Find the target CCN instance and click **Bind CEN Instance** in the **Actions** column.

    4.  In the Bind CEN Instance pane that appears, select the target CEN instance and click **OK**.

        After the CCN instance is associated with the CEN instance, SAG devices in the CCN can communicate with networks such as VPC networks and virtual border routers \(VBRs\) associated with the CEN.

        ![Associate with a CEN instance](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/6323660061/p63012.png)

4.  Configure a security group.

    1.  Log on to the [Elastic Compute Service \(ECS\) console](https://ecs.console.aliyun.com).

    2.  In the left-side navigation pane, click **Instances**.

    3.  Find the ECS instance deployed in the target VPC network and choose **More** \> **Network and Security Group** \> **Configure Security Group**.

    4.  Click **Add Rules** and then click **Add Security Group Rule**.

    5.  Create a security group rule that allows access from the private network to the VPC network.

        The following figure shows how to configure a security group rule. Set Authorization Object to the CIDR block of the private network.

        ![Security group](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/1779631061/p77754.png)


## Step 9: Test the connectivity

After you complete the configurations in the preceding steps, access cloud resources deployed in the VPC network from a client in your private network to test the connectivity.

