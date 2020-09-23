# Deploy an SAG device in one-arm mode and enable dynamic routing

This topic describes how to deploy a Smart Access Gateway \(SAG\) device in one-arm mode and enable static routing to connect the private networks of headquarters or office branches to Alibaba Cloud.

-   A Virtual Private Cloud \(VPC\) network is created. For more information, see [Create a VPC](/intl.en-US/VPCs and VSwitches/VPC management/Create a VPC.md).
-   A Cloud Enterprise Network \(CEN\) instance is created and associated with the VPC network. For more information, see [Create a CEN instance]().

In this example, a company has created a VPC network in the China \(Beijing\) region and deployed services in the VPC network. The company needs to connect its private network to Alibaba Cloud to access resources on Alibaba Cloud. An SAG-1000 device is deployed in the private network in one-arm mode. This deployment mode does not change the existing network topology.

![Architecture](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9355670061/p132809.png)

## Subnetting

The following CIDR blocks are used in this example. When you allocate CIDR blocks based on your actual requirements, make sure that the CIDR blocks do not overlap with each other.

|Node|Subnetting|
|----|----------|
|Private networks|Workloads: 172.16.0.0/12.|
|WAN port \(port 5\) of the SAG device: 192.168.100.1/30. IP address of the gateway: 192.168.100.2.|
|Port G11 of the Layer 3 switch: 192.168.100.2/30.|
|Port G1 of the Internet-facing router: 192.168.80.1/30. Port G2 of the Layer 3 switch: 192.168.80.2/30. |
|VPC network in the China \(Beijing\) region|10.0.0.0/16|

## Procedure

![Procedure](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9355670061/p146825.png)

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

![The order status](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/5323660061/p101651.png)

## Step 2: Activate the SAG devices

After you receive the SAG device, check whether you have received all the accessories. For more information, see [Descriptions of an SAG-1000 device](/intl.en-US/Smart Access Gateway/SAG-1000 configurations/Descriptions of an SAG-1000 device.md).

1.  Log on to the [SAG console](https://smartag.console.aliyun.com/).

2.  In the top navigation bar, select the area of the SAG device.

3.  On the Smart Access Gateway page, find the SAG instance created for the SAG device.

4.  In the **Actions** column, click **Activate**.

5.  In the Activate dialog box, click **OK**.

6.  After the SAG device is activated, connect it to the private network based on the preceding network topology.

    Use a network cable to connect the WAN port \(port 5\) of the SAG device to port G11 of the Layer 3 switch.

7.  If the SAG device was purchased from a third-party vendor, you must manually associate the SAG device with the SAG instance. For more information, see [Add a device](/intl.en-US/Configuration Guide/Manage devices/Associate SAG devices with SAG instances/Add a device.md).


## Step 3: Configure the SAG device

After you connect the SAG device, you can configure the ports and routing for the SAG device in the SAG console.

Before you begin, make sure that the device is activated, the 4G network works as expected, and the device is connected to Alibaba Cloud.

1.  Configure the WAN port.

    1.  On the Smart Access Gateway page, click the ID of the SAG instance that is associated with the SAG device.

    2.  On the instance details page, click the **Device Management** tab.

    3.  In the left-side navigation tree, click **Manage WAN Ports**.

    4.  In the WAN \(Port 5\) section, click **Edit**.

    5.  In the Configure WAN \(Port 5\) dialog box, set the following parameters and click **OK**.

        ![WAN (Port 5)](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/2172240061/p77418.png)

        -   **Connection Type**: Select **Static IP**.
        -   **Priority**: **1** is selected by default.
        -   **IP Address**: Enter the IP address of the WAN port. 192.168.100.1 is used in this example.
        -   **Subnet Mask**: Enter the subnet mask of the WAN port IP address. 255.255.255.252 is entered in this example.
        -   **Gateway**: Enter the IP address of the gateway. 192.168.100.2 is entered in this example.

            **Note:** After the gateway is configured, the SAG device automatically adds a default route.

2.  Advertise routes to Alibaba Cloud

    After you configure the WAN and LAN ports of the SAG device, you must also configure the routing method that synchronizes on-premises routes with Alibaba Cloud.

    1.  On the instance details page, click the **Network Configuration** tab.

    2.  In the left-side navigation tree, click **Methods to Synchronize with On-premises Routes**.

    3.  Select **Static Routing**, click **Add Static Route** to add a CIDR block, and then click **OK**.

        Enter the CIDR block used to route network traffic from Alibaba Cloud to the private network. 172.16.0.0/12 is used in this example.

        ![On-premises route 2](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/2172240061/p77167.png)


## Step 4: Configure switches and Internet-facing routers

In this step, you must configure the peer switch and Internet-facing router for the SAG device. Switches and routers used in this example may be different from yours. For more information, see the manuals issued by your providers.

1.  Configure routes for the Layer 3 switch.

    ```
    
    interface GigabitEthernet 0/11
    no switchport
    ip address 192.168.100.2 255.255.255.252 #The IP address of the peer switch of the SAG device  
    
    
    ip route 10.0.0.0 255.255.0.0 192.168.100.1 #The route to the VPC network in the China (Beijing) region
     
    ip route 0.0.0.0 0.0.0.0 192.168.80.1 #The route to the Internet       
    
                    
    ```

2.  Configure routes for the Internet-facing router.

    ```
    
    ip route 192.168.100.0 255.255.255.252 192.168.80.2 #The route to the SAG device
    
                    
    ```


## Step 5: Set up network connections

After you configure the SAG device, you must set up network connections to connect the private network to Alibaba Cloud.

1.  Create a Cloud Connect Network \(CCN\) instance.

    1.  Log on to the [SAG console](https://smartag.console.aliyun.com).

    2.  In the top navigation bar, select **Mainland China**.

        The area of the CCN instance must be the same as that of the SAG device.

    3.  In the left-side navigation pane, click **CCN**.

    4.  On the CCN page, click **Create CCN Instance**.

    5.  In the Create CCN Instance pane, specify a name for the CCN instance and click **OK**.

        The name must be 2 to 100 characters in length, and can contain digits, underscores \(\_\), and hyphens \(-\). It must start with a letter or a Chinese character.

        ![Create a CCN instance](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/6323660061/p76961.png)

2.  Associate the SAG instance with the CCN instance.

    1.  In the left-side navigation pane, click **Smart Access Gateway**.

    2.  On the Smart Access Gateway page, find the SAG instance that you want to manage and click **Network Configuration** in the **Actions** column.

    3.  In the left-side navigation tree, click **Network Instance Details**.

    4.  On the Network Instance Details tab, click **Attach Network**, select the CCN instance, and then click **OK**.

        ![Attach a network](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/6323660061/p132840.png)

3.  Associate the CCN instance with a CEN instance.

    After the CCN instance is associated with a CEN instance, SAG devices associated with the CCN instance can communicate with VPC networks associated with the CEN instance.

    1.  In the left-side navigation pane, click **CCN**.

    2.  Find the CCN instance and click **Bind CEN Instance** in the **Actions** column.

    3.  In the Bind CEN Instance pane, select **Existing CEN**, select the CEN instance that you want to associate with the CCN instance, and then click **OK**.

        ![Associate with a CEN instance](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/6323660061/p63012.png)

4.  Create a security group rule.

    You must create a security group rule for the Elastic Compute Service \(ECS\) instance in the VPC network to allow clients in the CIDR block 172.16.0.0/12 of the private network to access resources deployed on the ECS instance. For more information, see [Add security group rules](/intl.en-US/Security/Security groups/Add security group rules.md).


## Step 6: Test the connectivity

After you complete the configurations in the preceding steps, access cloud resources deployed in the VPC network from a client in your private network to test the connectivity.

