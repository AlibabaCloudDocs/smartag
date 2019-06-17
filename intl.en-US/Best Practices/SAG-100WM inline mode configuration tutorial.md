# SAG-100WM inline mode configuration tutorial {#concept_hxx_njz_k2b .concept}

This tutorial uses a Ningbo branch and a Hangzhou branch as an example to describe how to use a Smart Access Gateway \(SAG\) device to connect two local branches to VPCs located in Shanghai and Beijing. The clients of the local branches as a result can directly access the VPCs through the SAG device.

## Scenarios {#section_xc3_bkz_k2b .section}

In this tutorial, a company wants to connect local branches in Hangzhou and Ningbo to VPCs hosted in Shanghai and Beijing. Given that the branches and VPCs are all in the same SAG area, you only need to attach the Cloud Connect Network \(CCN\) instance associated with the Smart Access Gateway instances to the Cloud Enterprise Network \(CEN\) instance.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/23682/156073807314251_en-US.png)

To connect the local branches to the VPCs, you need to complete the following tasks:

1.  Purchase an SAG device.
2.  Connect the SAG device.
3.  Activate the SAG device.
4.  Configure the network connection.
5.  Configure the security group.
6.  Perform an access test.

## Prerequisites {#section_vk5_441_mfb .section}

-   A CEN instance is created.
-   A VPC is created in Shanghai and another VPC is created in Beijing. In addition, the VPCs are added to the same CEN instance. If you have not completed this step, complete the following instructions:
    1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com).
    2.  Choose **Quick Links** \> **VPC**.
    3.  Select the **China \(Beijing\)** region and click the ID of the target VPC.
    4.  On the VPC Details page, click **Attach to CEN**, and then select the target CEN instance.
    5.  Repeat the preceding steps to add the VPC in Shanghai to the same CEN instance.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/23682/156073807313745_en-US.png)

-   A CCN instance is created. For more information, see [Create a CCN instance](../intl.en-US/User Guide/Cloud Connect Network/Create a CCN instance.md#).

## Step 1: Buy an SAG device {#section_onw_h5c_l2b .section}

After you buy an SAG device on the console, Alibaba Cloud delivers the device to you and creates a Smart Access Gateway instance for you to manage.

To buy an SAG device, follow these steps:

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com).
2.  Click **Create SmartAG**.
3.  Configure the SAG device and click **Buy Now**.

    For more information, see [Buy a Smart Access Gateway Hardware](../intl.en-US/Pricing/Buy a Smart Access Gateway Hardware.md#).

    **Note:** In this tutorial, the **SAG-100WM** specification and the **Stand-alone** usage method are selected.

4.  Confirm the order information, and then click **Buy Now**.
5.  On the displayed Address dialog box, enter the shipping address of the gateway device and click **Order Now**.

    You can check whether the order is successfully placed on the SAG page. The system will deliver the device within 48 hours after the order is placed. If you do not receive the device within 48 hours, you can open a ticket to check the delivery status.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/23799/156073807321242_en-US.png)


## Step 2: Connect the SAG device {#section_xjs_lrj_l2b .section}

After receiving an SAG device, follow [SAG-100WM user manual](../intl.en-US/Product Introduction/Smart Access Gateway device/SAG-100WM.md#) to check that all accessories are included, and then power on the device. After you start the SAG device, connect the WAN port to the network cable and connect the LAN ports to local clients.

In this tutorial, the clients in the Hangzhou and Ningbo branches can be directly connected to Alibaba Cloud through the SAG devices, so you can use the default gateway configuration. If you need to configure the WAN port and LAN ports, see [Configuration guide](../intl.en-US/SAG-100wm Configuration Guide/Configuration guide.md#).

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/23682/156073807313738_en-US.png)

## Step 3: Activate the SAG device {#section_lyw_rbk_l2b .section}

After receiving an SAG device, you must activate it.

To activate the SAG device, follow these steps:

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com/).
2.  On the SmartAG page, find the target gateway instance.
3.  Click **Activate** in the **Actions** column.

## Step 4: Configure the network connection {#section_dtn_xbk_l2b .section}

After activating the SAG device, you need to attach it to a CCN instance and then attach the CCN instance to a CEN instance, so that local branches can be connected to Alibaba Cloud.

To configure the network, follow these steps:

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com/).
2.  On the SAG page, find the target gateway instance.
3.  Click **Configure Network** in the **Actions** column.
4.  On the Configure Network page, follow these steps:
    1.  **Private CIDR Block**: Configure the private CIDR blocks used by the local clients to access Alibaba Cloud. Make sure all private CIDR blocks do not conflict with one another.

        In this tutorial, enter 172.16.0.0/12. In this tutorial, each local branch uses the default gateway configuration, so the IP address used by the local client to access Alibaba Cloud is allocated from the 10.10.0.0/12 CIDR block. For more information, see [Network configuration](../intl.en-US/User Guide/Manage a Smart Access Gateway instance.md#table_xrf_xd2_l2b).

        **Note:** Configuring a CIDR block with a 32-bit mask is not supported.

    2.  **CCN Instance ID/Name**: Add the gateway instance to the CCN instance. Then, SAG devices in the CCN instance can communicate with one another.

        In this tutorial, the default CCN is used. For more information, see [Cloud Connect Network](../intl.en-US/User Guide/Cloud Connect Network.md#).

5.  **Bind CEN Instance**: Select the CEN instance to attach. After the CCN instance is attached to the CEN instance, SAG devices in the CCN instance can communicate with networks \(VPCs and VBRs\) attached to the CEN instance.

    In this tutorial, the CEN instance associated with the Shanghai VPC and Beijing VPC is selected.

6.  Click **OK**.
7.  Repeat the preceding steps to configure the network for the gateway instance of the other branch.

    Make sure the two gateway instances are attached to the same CCN instance and the same CEN instance.


## Step 5: Configure a security group {#section_srm_v5d_p2b .section}

Configure a security group to allow the branches to access VPC.

To configure the security group, follow these steps:

1.  Log on to the [ECS Console](https://ecs.console.aliyun.com).
2.  In the left-side navigation pane, click **Instances**.
3.  Find the ECS instance in the target VPC, and then choose **More** \> **Network and Security Group** \> **Configure Security Group**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15407/15607380747646_en-US.png)

4.  Click **Add Rules** and click **Add Security Group Rule**.
5.  Configure a security group rule that allows access from local branches.

    The following figure shows the security group configurations in this tutorial. You must enter the private CIDR blocks of the local branches as the authorization objects.

    ![](images/38920_en-US.png)


## Step 6: Test the access {#section_hzm_tdk_l2b .section}

After completing the preceding configurations, you can use local clients to access cloud resources deployed in the connected VPCs to check if the configurations take effect.

