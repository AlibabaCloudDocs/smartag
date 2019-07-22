# Cross-region access to VPC {#concept_hxx_njz_k2b .concept}

This tutorial takes a Beijing branch as an example of how to connect local branches to VPCs in Hangzhou and US \(Silicon Valley\) through Smart Access Gateway \(SAG\). Then, clients of the local branches can directly access the VPCs through SAG.

## Scenario {#section_xc3_bkz_k2b .section}

For access of local branches in the Mainland China area, you only need to attach the CCN associated with the SAG device to the CEN in the same area and configure the region connection between the Hangzhou VPC and the US \(Silicon Valley\) VPC.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/23732/156376392113795_en-US.png)

To do so, complete the following tasks:

1.  Purchase an SAG device.
2.  Connect the SAG device.
3.  Activate the SAG device.
4.  Configure the network connection.
5.  Configure the CEN.
6.  Configure a security group.
7.  Perform an access test.

## Prerequisites {#section_vk5_441_mfb .section}

-   a CEN instance is created.
-   A VPC in the Hangzhou region and a VPC in the US \(Silicon Valley\) region are created and are added to the same CEN instance.
    1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com).
    2.  Choose **Quick Links** \> **VPC**.
    3.  Select the **China \(Hangzhou\)** region and click the ID of the VPC in Hangzhou.
    4.  On the VPC Details page, click **Attach to CEN**, and then select the target CEN instance.
    5.  Repeat the preceding steps to add the VPC in US \(Silicon Valley\) to the same CEN instance.
-   A CCN instance is created. For more information, see [Create a CCN instance](../intl.en-US/Cloud Connect Network/Create a CCN instance.md#).

## Step 1: Buy an SAG device {#section_onw_h5c_l2b .section}

After you buy an SAG device on the console, Alibaba Cloud delivers the device to you and creates a Smart Access Gateway instance for you to manage.

To buy an SAG device, follow these steps:

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com).
2.  Click **Create SmartAG**.
3.  Configure the SAG device and click **Buy Now**.

    For more information, see [Buy a Smart Access Gateway](../intl.en-US/Pricing/Buy a Smart Access Gateway.md#).

    **Note:** In this tutorial, the **SAG-100WM** specification and the **Stand-alone** usage method are selected.

4.  Confirm the order information, and then click **Buy Now**.
5.  On the displayed Address dialog box, enter the shipping address of the gateway device and click **Order Now**.

    You can check whether the order is successfully placed on the SAG page. The system will deliver the device within 48 hours after the order is placed. If you do not receive the device within 48 hours, you can open a ticket to check the delivery status.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/23799/156376392121242_en-US.png)


## Step 2: Connect the SAG device {#section_xjs_lrj_l2b .section}

After you receive the SAG device, check if all accessories are provided according to [SAG-100WM overview](../intl.en-US//SAG-100WM overview.md#). After you start the gateway device, connect the WAN port to the network cable and connect the LAN ports to local clients.

In this tutorial, the clients in the Hangzhou and US \(Silicon Valley\) branches can be directly connected to Alibaba Cloud through the SAG devices, so you can use the default gateway configurations. If you need to configure the WAN port and LAN ports, see [Step 3: Configure the WAN ports](../intl.en-US//Step 3: Configure the WAN ports.md#).

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/23682/156376392213738_en-US.png)

## Step 3: Activate the SAG device {#section_lyw_rbk_l2b .section}

After receiving an SAG device, you must activate it.

To activate the gateway device, follow these steps:

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com/).
2.  On the SmartAG page, find the target gateway instance.
3.  Click **Activate** in the **Actions** column.

## Step 4: Configure the network connection {#section_dtn_xbk_l2b .section}

After activating the SAG device, you need to attach it to a CCN instance and then attach the CCN instance to a CEN instance, so that local branches can be connected to Alibaba Cloud.

Complete these steps to configure the network:

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com/).
2.  On the SAG page, find the target gateway instance.
3.  Click **Configure Network** in the **Actions** column.
4.  On the Configure Network page, follow these steps:
    1.  **Private CIDR Block**: Configure the private CIDR blocks used by the local clients to access Alibaba Cloud. Make sure all private CIDR blocks do not conflict with one another.

        In this tutorial, enter 172.16.0.0/12. Because each local branch uses the default gateway configuration, the IP address used by the local client to access Alibaba Cloud is allocated from the 172.16.0.0/12 CIDR block. For more information, see [Configure the network](../intl.en-US/Cloud Connect Network/Smart Access Gateway/Configure the network.md#).

        **Note:** Configuring a 32-bit mask is not supported.

    2.  **CCN Instance ID/Name**: Add the gateway instance to the CCN instance. Then SAG devices in the CCN instance can communicate with one another.

        In this tutorial, select the default CCN instance. For more information, see [Cloud Connect Network](../intl.en-US/Cloud Connect Network/Cloud Connect Network.md#).

5.  **Bind CEN Instance**: Select the CEN instance to attach. After the CCN instance is attached to the CEN instance, SAG devices in the CCN instance can communicate with networks \(VPCs and VBRs\) attached to the CEN instance.

    In this tutorial, the CEN instance associated with the Hangzhou VPC and the US \(Silicon Valley\) VPC is selected.

    **Note:** Make sure that the CCN instance and the CEN instance are in the same area. For more information, see [Cloud Connect Network](../intl.en-US/Cloud Connect Network/Cloud Connect Network.md#).

6.  Click **OK**.

## Step 5: Configure the CEN {#section_b4k_bvh_mfb .section}

To connect networks in different regions, you must buy a bandwidth package and set the region connection, namely the cross-region interconnection bandwidth.

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com/).
2.  In the left-hand navigation pane, choose **Quick Links** \> **CEN**.
3.  On the CEN page, click the **Networks** tab page to view whether the Hangzhou VPC, the US \(Silicon Valley\) VPC and the CCN are attached to the CEN.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/23732/156376392214285_en-US.png)

4.  Click the **Bandwidth Packages** tab page and click **Buy Bandwidth Package \(Pay-As-You-Go\)** to buy a Pay-As-You-Go Bandwidth package.
5.  On the CEN \(Pay-As-You-Go page, configure the bandwidth package.

    -   **Cloud Enterprise Network**: Select the CEN associated with the VPCs and the CCN.
    -   **Area A** and **Area B**: Select the areas of the VPCs to communicate with each other.

        Here, **Mainland China** and **North America** are selected.

    -   **Bandwidth**: Select the bandwidth of the region connection according to your needs.
    -   **Bandwidth Package Name**: Enter the name of the bandwidth package.
    ![](images/14286_en-US.png)

6.  Click **Buy Now** to buy a bandwidth package.
7.  Click the **Region Connections** tab page and then click **Set Region Connection**.
8.  Set the region connection. The sum of all region connections under a bandwidth package cannot be greater than the bandwidth of the bandwidth package.

    -   **Bandwidth Packages**: Select the bandwidth package that is used by the CEN instance. Here, select **Mainland China ⇋ North American**.
    -   **Connected Regions**: Select the regions to be connected. Here, select **China \(Hangzhou\)** and **US \(Silicon Valley\)**, as well as **Mainland China** and **US \(Silicon Valley\)**.
    -   **Bandwidth**: Enter the bandwidth according to your needs.

        **Note:** The sum of all region connections under a bandwidth package cannot be greater than the bandwidth of the bandwidth package.

    ![](images/14284_en-US.png "Region connection 1")

    ![](images/38592_en-US.png "Region connection 2")


## Step 6: Configure a security group {#section_srm_v5d_p2b .section}

Configure a security group to allow local branches to access the VPC.

To configure the security groups, complete these steps:

1.  Log on to the [ECS Console](https://ecs.console.aliyun.com).
2.  In the left-side navigation pane, click **Instances**.
3.  Find the target ECS instance in the target VPC, and then choose **More** \> **Network and Security Group** \> **Configure Security Group**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15407/15637639227646_en-US.png)

4.  Click **Add Rules** and click **Add Security Group Rule**.
5.  Configure a security group rule that allows access from local branches.

    The following figure shows the security group configurations in this tutorial. You must enter the private CIDR blocks of the local branches as the authorization objects.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15407/15637639227648_en-US.png)


## Step 7: Test the access {#section_hzm_tdk_l2b .section}

After completing the preceding configurations, check that you can access cloud resources deployed in the connected VPCs from local clients to verify whether the new configurations take effect.

