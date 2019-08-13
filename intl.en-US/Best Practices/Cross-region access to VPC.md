# Cross-region access to VPC {#concept_hxx_njz_k2b .concept}

This tutorial uses a Beijing branch as an example to describe how to connect local branches to VPCs in Hangzhou and US \(Silicon Valley\) through a Smart Access Gateway \(SAG\). After you connect local branches to VPCs, clients of the local branches can directly access the VPCs through the SAG.

## Scenario {#section_xc3_bkz_k2b .section}

For access of local branches in Mainland China, you only need to attach the CCN associated with the SAG device to the CEN in the same area and configure the region connection between the Hangzhou VPC and the US \(Silicon Valley\) VPC.

![Networking solution](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/23732/156571085013795_en-US.png)

To do so, complete the following steps:

1.  Purchase an SAG device.
2.  Connect the SAG device.
3.  Activate the SAG device.
4.  Configure the network connection.
5.  Associate the CCN instance with a CEN instance.
6.  Configure the CEN.
7.  Configure a security group.
8.  Perform an access test.

## Prerequisites {#section_vk5_441_mfb .section}

-   A CEN instance is created.
-   A VPC in the Hangzhou region and a VPC in the US \(Silicon Valley\) region are created and are attached to the same CEN instance.
    1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com).
    2.  Choose **Quick Links** \> **VPC**.
    3.  Select the **China \(Hangzhou\)** region and click the ID of the target VPC instance in Hangzhou.
    4.  On the VPC Details page, click **Attach to CEN**, and then select the target CEN instance.
    5.  Repeat the preceding steps to add the VPC in US \(Silicon Valley\) to the same CEN instance.
-   A CCN instance is created. For more information, see [Create a CCN instance](../reseller.en-US/Cloud Connect Network/Create a CCN instance.md#).

## Step 1: Purchase an SAG device {#section_onw_h5c_l2b .section}

After you purchase an SAG device on the console, Alibaba Cloud delivers the device to you and creates an SAG instance for you.

To purchase an SAG device, follow these steps:

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com).
2.  Click **Create SmartAG**.
3.  Configure the SAG device and click **Buy Now**.

    For more information, see [Buy a Smart Access Gateway](../reseller.en-US/Pricing/Buy a Smart Access Gateway.md#).

    **Note:** In this tutorial, the **SAG-100WM** specification and the **Stand-alone** usage method are selected.

4.  Confirm the order information, and then click **Buy Now**.
5.  On the displayed Address dialog box, enter the shipping address of the gateway device and click **Order Now**.

    You can check whether the order is successfully placed on the SAG page. The system will deliver the device within 48 hours after the order is placed. If you do not receive the device within 48 hours, you can open a ticket to check the delivery status.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/23799/156571085021242_en-US.png)


## Step 2: Connect the SAG device {#section_xjs_lrj_l2b .section}

After you receive the SAG device, check whether all accessories are provided according to [SAG-100WM overview](../reseller.en-US/Smart Access Gateway/Configuration Guide/SAG-100WM configurations/SAG-100WM overview.md#). After you start the SAG device, connect the WAN port to the network cable and connect the LAN ports to local clients.

In this tutorial, the clients in the Hangzhou and US \(Silicon Valley\) branches can be directly connected to Alibaba Cloud through SAG devices, so you can use the default gateway configurations. If you need to configure the WAN port and LAN ports, see [Step 3: Configure the WAN ports](../reseller.en-US//Step 3: Configure the WAN ports.md#).

![Connect the SAG device](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/23682/156571085013738_en-US.png)

## Step 3: Activate the SAG device {#section_lyw_rbk_l2b .section}

Before you can use the SAG device, you must activate it.

To activate the SAG device, follow these steps:

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com/).
2.  On the SmartAG page, find the target gateway instance.
3.  Click **Activate** in the **Actions** column.

## Step 4: Configure the network connection {#section_ezf_5mp_20w .section}

After you activate and connect the SAG device, you also need to add the SAG device to a CCN.

To configure the network, follow these steps:

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com).
2.  In the left-side navigation pane, click **Smart Access Gateway**, and then click the target instance ID or click **Configure Network** in the **Actions** column.
3.  Configure the synchronization method for on-premises routes.
    1.  Click **Method to Synchronize with On-premises Routes**.
    2.  Select **Static Routing**, and then click **Add Static Routing**.

        In this example, enter 172.16.0.0/12.

    3.  Click **OK**.
4.  Associate the SAG instance with a CCN
    1.  Click **Network Instance Details**.
    2.  Click **Add Network Instance**, and then select the target CCN. The SAG instances in the CCN can communicate with each other.

        In this example, the default CCN is used. For more information, see [Cloud Connect Network](../reseller.en-US/Cloud Connect Network/Cloud Connect Network.md#).

    3.  Click **OK**.

## Step 5: Associate the CCN instance with a CEN instance {#section_170_p2v_jd4 .section}

To associate the CCN instance with a CEN instance, follow these steps:

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com).
2.  In the left-side navigation pane, click **CCN**.
3.  Find the target CCN instance, and then click **Bind CEN Instance** in the **Actions** column.
4.  On the Bind CEN instance page, select the target CEN instance. After the CCN instance is associated with the CEN instance, the SAG devices in the CCN instance can communicate with the network instances \(VPCs and VBRs\) attached to the CEN instance.

    ![Associate a CCN instance with a CEN instance](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/987728/156571085052171_en-US.png)


## Step 6: Configure the CEN {#section_b4k_bvh_mfb .section}

To connect networks in different regions, you must purchase a bandwidth package and set the cross-region interconnection bandwidth.

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com/).
2.  In the left-side navigation pane, choose **Quick Links** \> **CEN**.
3.  On the CEN page, click the **Networks** tab page to check whether the Hangzhou VPC, the US \(Silicon Valley\) VPC, and the CCN are attached to the CEN.

    ![Networks](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/23732/156571085014285_en-US.png)

4.  Click the **Bandwidth Packages** tab page and click **Buy Bandwidth Package \(Pay-As-You-Go\)** to purchase a Pay-As-You-Go Bandwidth package.
5.  On the CEN \(Pay-As-You-Go page, configure the bandwidth package.

    -   **Cloud Enterprise Network**: Select the CEN associated with the VPCs and the CCN.
    -   **Area A** and **Area B**: Select the areas of the VPCs that need to communicate with each other.

        In this example, **Mainland China** and **North America** are selected.

    -   **Bandwidth**: Select the bandwidth of the region connection as needed.
    -   **Bandwidth Package Name**: Enter the name of the bandwidth package.
    ![Purchase a bandwidth package](images/14286_en-US.png)

6.  Click **Buy Now** to purchase a bandwidth package.
7.  Click the **Region Connections** tab page and then click **Set Region Connection**.
8.  Set the region connection. The sum of all region connections under a bandwidth package cannot be greater than the bandwidth of the bandwidth package.

    -   **Bandwidth Packages**: Select the bandwidth package that is used by the CEN instance. In this example, select **Mainland China ⇋ North American**.
    -   **Connected Regions**: Select the regions to be connected. In this example, select **China \(Hangzhou\)** and **US \(Silicon Valley\)**, and also select **Mainland China** and **US \(Silicon Valley\)**.
    -   **Bandwidth**: Enter the bandwidth as needed.

        **Note:** The sum of all region connections under a bandwidth package cannot be greater than the bandwidth of the bandwidth package.

    ![Region connection 1](images/14284_en-US.png "Region connection 1")

    ![Region connection 2](images/38592_en-US.png "Region connection 2")


## Step 7: Configure a security group {#section_srm_v5d_p2b .section}

To allow local branches to access the VPC, you must configure a security group.

To configure a security group, follow these steps:

1.  Log on to the [ECS Console](https://ecs.console.aliyun.com).
2.  In the left-side navigation pane, click **Instances**.
3.  Find the target ECS instance in the target VPC, and then choose **More** \> **Network and Security Group** \> **Configure Security Group**.

    ![Configure a security group](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15407/15657108507646_en-US.png)

4.  Click **Add Rules** and click **Add Security Group Rule**.
5.  Configure a security group rule that allows access from local branches.

    The following figure shows the security group configurations in this tutorial. You must enter the private CIDR blocks of the local branches as the authorization objects.

    ![Security group rule](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15407/15657108507648_en-US.png)


## Step 8: Perform an access test {#section_hzm_tdk_l2b .section}

After you complete the preceding configurations, you can access cloud resources deployed in the connected VPCs from local clients to check whether the new configurations take effect.

