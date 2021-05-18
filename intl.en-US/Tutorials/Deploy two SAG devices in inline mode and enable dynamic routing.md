# Deploy two SAG devices in inline mode and enable dynamic routing

This topic describes how to deploy two Smart Access Gateway \(SAG\) devices in inline mode and enable Open Shortest Path First \(OSPF\)-based dynamic routing to connect a private network to Alibaba Cloud.

The following figure shows the topology of the private network. A Layer 3 switch is connected to two Layer 2 switches. Local clients and servers are connected to the Layer 2 switches. Two SAG devices are connected to the Layer 3 switch in inline mode to establish network connections between the private network and Alibaba Cloud. The two SAG devices serve as a standby device for each other.

![Deploy two SAG devices in inline mode](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/1440731061/p101680.png)

## Prerequisites

-   A Virtual Private Cloud \(VPC\) network is created in the China \(Beijing\) region. For more information, see [Work with VPCs](/intl.en-US/VPCs and vSwitchs/Work with VPCs.md).
-   A Cloud Enterprise Network \(CEN\) instance is created and associated with the VPC network in the China \(Beijing\) region. For more information, see [Create a CEN instance]().

## Subnetting

The following CIDR blocks are used in this example. When you allocate CIDR blocks based on your actual requirements, make sure that the CIDR blocks do not overlap with each other.

|Object|IP address|
|------|----------|
|VPC network in the China \(Beijing\) region|10.0.0.0/16.|
|Internet-facing router|Port G1: 192.168.100.2/30.|
|Port G2: 192.168.200.2/30.|
|SAG Device 1|-   WAN port \(port 5\): 192.168.100.1/30. Next hop: 192.168.100.2.
-   LAN port 4:192.168.50.1/30. |
|SAG Device 2|-   WAN port \(port 5\): 192.168.200.1/30. Next hop: 192.168.200.2.
-   LAN port 4:192.168.60.1/30. |
|Layer 3 switch|-   Port G11: 192.168.50.2/30.
-   Port G12: 192.168.60.2/30.
-   Loopback interface: 192.168.100.3/32. |
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

![Query the shipping status](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5323660061/p101651.png)

## Step 2: Activate the SAG devices

After you receive the SAG devices, check whether you have received all the accessories. For more information, see [Descriptions of an SAG-1000 device](/intl.en-US/Smart Access Gateway/SAG-1000 usage instructions/Descriptions of an SAG-1000 device.md).

1.  Log on to the [SAG console](https://smartag.console.aliyun.com/).

2.  On the Smart Access Gateway page, find the target SAG instance.

3.  In the **Actions** column, click **Activate**.

4.  Click the ID of the target SAG instance. On the instance details page, click the **Device Management** tab and enter the serial number of the device.

    ![Add the device](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/0779631061/p101760.png)

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

    -   **Connection Type**: Select **Static IP**.
    -   **Port Address**: Enter the IP address of the LAN port. 192.168.50.1 is used in this example.
    -   **Subnet Mask**: Enter the subnet mask of the LAN port IP address. 255.255.255.252 is used in this example.
7.  In the left-side navigation tree, click **Manage WAN Ports**.

8.  In the WAN \(Port 5\) section, click **Edit**.

9.  In the Configure WAN \(Port 5\) dialog box that appears, set the following parameters and click **OK**.

    -   **Connection Type**: Select **Static IP**.
    -   **IP Address**: Enter the IP address of the WAN port. 192.168.100.1 is used in this example.
    -   **Subnet Mask**: Enter the subnet mask of the WAN port IP address. 255.255.255.252 is used in this example.
    -   **Gateway**: Enter the IP address of the gateway. 192.168.100.2 is used in this example.

        **Note:** After you configure the gateway, the SAG device generates a default route.


## Step 5: Configure OSPF-based dynamic routing

You can configure OSPF-based dynamic routing for SAG devices in the SAG console.

Device 1 is used in this example. Repeat this step to configure OSPF-based dynamic routing for Device 2.

1.  Log on to the [SAG console](https://smartag.console.aliyun.com/).

2.  On the Smart Access Gateway page, click the ID of the target SAG instance.

3.  On the instance details page, click the **Device Management** tab.

4.  In the left-side navigation tree, click **Manage Routes**.

5.  In the OSPF Protocol Settings section, click **Edit**.

6.  In the Configure OSPF Protocol dialog box that appears, enter the information about the allocated IP address and click **OK**.

    |Parameter|Description|
    |:--------|:----------|
    |**Area ID**|Set area IDs as follows: Area ID of the active device: 1.

Area ID of the standby device: 1. |
    |**Hello Time**|Set the hello time to 3 seconds for both devices.|
    |**Dead Time**|Set the dead time to 10 seconds for both devices.|
    |**Authentication Type**|Select Disable Authentication for both devices.|
    |**Router ID**|Set router IDs as follows: Router ID of the active device: 192.168.100.1.

Router ID of the standby device: 192.168.200.1. |
    |**Area Type**|The area type is set to NSSA by default.|

7.  In the **Dynamic Routing Settings** section, select **Enable OSPF Protocol**.

8.  Find **Port 4 \(LAN\)**, click **Edit** in the **Actions** column, select Enable OSPF, and then click **OK**.


## Step 6: Configure the Layer 3 switch and Internet-facing router

The commands used to configure switches vary depending on the switch provider. For more information, see the manuals issued by your providers. A switch and router provided by Cisco are used in this example.

-   The Layer 3 switch
    -   Set the port IP addresses and OSPF parameters.

        **Note:** For each SAG device, the network type of ports using the OSPF protocol must be set to peer-to-peer \(P2P\). Otherwise, the SAG device cannot calculate routes correctly.

        ```
        
        interface GigabitEthernet 0/11
         no switchport
         ip ospf network point-to-point          Set the network type to P2P
         ip ospf hello-interval 3
         ip ospf dead-interval 10
         ip address 192.168.50.2 255.255.255.252 The port IP address of the peer switch of Device 1
        
        
        interface GigabitEthernet 0/12
         no switchport
         ip address 192.168.60.2 255.255.255.252    The port IP address of the peer switch of Device 2
         ip ospf network point-to-point    Set the network type to P2P
         ip ospf dead-interval 10
         ip ospf hello-interval 3
        
        !  
        
                                    
        ```

    -   Specify the loopback address and route advertisement information.

        **Note:** OSPF requires a not-so-stubby area \(NSSA\), automatically generates a default route, and advertises it to SAG.

        ```
        
        
        interface Loopback 0
        ip address 192.168.100.3 255.255.255.255                       The loopback address of the switch
        !
        
        router ospf 1
         router-id 192.168.100.3                                     The router ID of the switch
         network 172.16.0.0 0.15.255.255 area 0                        The CIDR block of the local server
         network 192.168.50.0 0.0.0.4 area 1                       The CIDR block of the switch port connected to Device 1
         network 192.168.100.3 0.0.0.0 area 0                        The loopback address of the switch                            
         network 192.168.60.0 0.0.0.4 area 1                       The CIDR block of the switch port connected to Device 2
         area 1 nssa default-information-originate no-summary
        
        !
        
                                    
        ```

-   The Internet-facing router

    ```
    Configure static routes
    
    ip route 192.168.100.0 255.255.255.252  192.168.100.2 The route to Device 1
    ip route 192.168.200.0 255.255.255.252  192.168.200.2 The route to Device 2
    ```


## Step 7: Set up network connections

After you configure the SAG devices, you must set up network connections to connect the private network to Alibaba Cloud.

1.  Create a Cloud Connect Network \(CCN\) instance.

    1.  Log on to the [SAG console](https://smartag.console.aliyun.com).

    2.  In the left-side navigation pane, click **CCN**.

    3.  On the CCN page, click **Create CCN Instance**.

    4.  In the Create CCN Instance pane that appears, specify a name for the CCN instance and click **OK**.

        The name must be 2 to 100 characters in length and can contain digits, underscores \(\_\), and hyphens \(-\). It must start with a letter or Chinese character.

        ![Create a CCN instance](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6323660061/p76961.png)

2.  Set up network connections.

    1.  Log on to the [SAG console](https://smartag.console.aliyun.com).

    2.  On the Smart Access Gateway page, click the ID of the target SAG instance or click **Network Configuration** in the **Actions** column.

    3.  On the Method to Synchronize with On-premises Routes tab, select **Dynamic Routing**.

    4.  On the Network Instance Details tab, click **Attach Network**, select the CCN instance, and then click **OK**.

        ![Select the CCN instance](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6910843951/p63008.png)

3.  Associate the CCN instance with a CEN instance.

    1.  Log on to the [SAG console](https://smartag.console.aliyun.com).

    2.  In the left-side navigation pane, click **CCN**.

    3.  Find the target CCN instance and click **Bind CEN Instance** in the **Actions** column.

    4.  In the Bind CEN Instance pane that appears, select the target CEN instance and click **OK**.

        After the CCN instance is associated with the CEN instance, SAG devices in the CCN can communicate with networks such as VPC networks and virtual border routers \(VBRs\) associated with the CEN.

        ![Associate with a CEN instance](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6323660061/p63012.png)

4.  Configure a security group.

    1.  Log on to the [Elastic Compute Service \(ECS\) console](https://ecs.console.aliyun.com).

    2.  In the left-side navigation pane, click **Instances**.

    3.  Find the ECS instance deployed in the target VPC network and choose **More** \> **Network and Security Group** \> **Configure Security Group**.

    4.  Click **Add Rules** and then click **Add Security Group Rule**.

    5.  Create a security group rule that allows access from the private network to the VPC network.

        The following figure shows how to configure a security group rule. Set Authorization Object to the CIDR block of the private network.

        ![Security group](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/1779631061/p77754.png)


## Step 8: Test the connectivity

After you complete the configurations in the preceding steps, access cloud resources deployed in the VPC network from a client in your private network to test the connectivity.

