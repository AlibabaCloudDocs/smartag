# Connect local branches to VPCs {#concept_hxx_njz_k2b .concept}

This tutorial explains how to connect two local branches to VPCs hosted in other locations of the same area using Smart Access Gateway. Clients of the local branches can then directly access the VPCs through Smart Access Gateway.

## Scenario {#section_xc3_bkz_k2b .section}

In this tutorial, a company wants to connect local branches in Hangzhou and Ningbo to VPCs hosted in Shanghai and Beijing. Since the branches and VPCs are all in the same Smart Access Gateway area, you only need to attach the CCN instance associated with the Smart Access Gateway instances to the CEN instance in the same area.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15407/15349539136809_en-US.png)

## Step 1. Buy a Smart Access Gateway device {#section_onw_h5c_l2b .section}

After you buy a Smart Access Gateway device on the console, Alibaba Cloud delivers the device to you and creates a Smart Access Gateway instance for you to manage the network.

To buy a Smart Access Gateway device, complete these steps:

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com).
2.  Click **Create SmartAG**.
3.  Configure the Smart Access Gateway device according to the following information and click **Buy Now**.

    |Configuration|Description|
    |:------------|:----------|
    |**Region**|Select the area of the Smart Access Gateway. The delivery address of the gateway device must be in the selected area.Each Smart Access Gateway area corresponds to a country. Currently, only the Mainland China area is supported.

|
    |**Instance**|Enter an instance name.The name can contain 2 to 128 characters and must start with an English letter. It can contain numbers and the following special characters:

. \_-

In this tutorial, enter **Hangzhou branch**.

|
    |**Hardware Specification**|Select the hardware specification for the gateway device.The configurations of gateways with different specifications are also different. For more information, see [Specifications of Smart Access Gateway device](../intl.en-US/User Guide/Manage a Smart Access Gateway device/Gateway device description.md#section_gdf_25s_j2b).

In this tutorial, select **Standard edition**.

|
    |**Peak Bandwidth**|Select the bandwidth of the Smart Access Gateway device.In this tutorial, select **2 Mpbs**.

|
    |**Procedure **|Currently, only the single-device mode is supported, and so a local branch can only buy one Smart Access Gateway device for accessing Alibaba Cloud.|
    |**Subscription Duration**|Select the purchase duration.In this tutorial, select **1 month**.

|

4.  Confirm the order information, and then click **Buy Now**.
5.  In the Delivery address dialog box, enter the delivery address of the gateway device and click **Place an Order**.

    You can check whether the order is successfully placed on the status page of Smart Access Gateway instances. The system will deliver the device within two days of the order being placed. If you do not receive the device within two days, you can submit a ticket to check the delivery status.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15407/15349539137051_en-US.png)

6.  Repeat the preceding steps to buy a Smart Access Gateway device for the Ningbo branch.

## Step 2. Connect the gateway device {#section_xjs_lrj_l2b .section}

After you receive the gateway device, check you have all of the items listed in the [Gateway device description](../intl.en-US/User Guide/Manage a Smart Access Gateway device/Gateway device description.md#). After you start the gateway device, connect the WAN port to the network cable and connect the LAN ports to local clients.

In this tutorial, the gateway device can be directly connected to the clients in the Hangzhou and Ningbo branches, so you can use the default gateway configuration. If you need to configure the WAN port and LAN ports, see [Configure a Smart Access Gateway device](../intl.en-US/User Guide/Manage a Smart Access Gateway device/Configure a Smart Access Gateway device.md#).

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15407/15349539137076_en-US.png)

## Step 3. Activate the gateway {#section_lyw_rbk_l2b .section}

After receiving the gateway device, you need to activate it.

To activate the gateway device, complete these steps:

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com/).
2.  On the SmartAG page, find the target gateway instance.
3.  Click **Activate** in the **Actions** column.

## Step 4. Configure the network connection {#section_dtn_xbk_l2b .section}

After activating the Smart Access Gateway device, you then need to attach it to a CCN instance and then attach the CCN instance to a CEN instance, so that local branches can connect to Alibaba Cloud.

To configure the network, complete these steps:

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com/).
2.  On the SmartAG page, find the target gateway instance.
3.  Click **Configure Network** in the **Actions** column.
4.  On the Configure Network page, complete these steps:
    1.  **Private CIDR Block**: Configure the private CIDR blocks used by the local clients to access Alibaba Cloud. Make sure none of the private CIDR blocks conflict with each other.

        In this tutorial, enter 172.16.0.0/12. Also use the default gateway configuration, so the IP address used by the local client to access Alibaba Cloud is allocated from the CIDR block 172.16.0.0/12. For more information, see [Network configuration](../intl.en-US/User Guide/Manage a Smart Access Gateway instance.md#table_xrf_xd2_l2b).

    2.  **CCN Instance ID/Name**: Add the gateway instance to the CCN instance. Gateway devices can then communicate with one another.

        In this tutorial, select the default CCN instance. For more information, see [Cloud Connect Network](../intl.en-US/User Guide/Cloud Connect Network.md#).

5.  **Bind CEN Instance**: Select the CEN instance to attach. After the CCN instance is attached to the CEN instance, all networks \(VPCs and VBRs\) attached to the CEN instance can communicate with gateway devices in the CCN instance.

    In this tutorial, the CEN instance associated with the Shanghai VPC and Beijing VPC is selected.

    **Note:** Make sure that the CCN instance and the CEN instance are in the same area. For more information, see [CCN areas](../intl.en-US/User Guide/Cloud Connect Network.md#section_sb4_vqf_l2b).

6.  Click **OK**.
7.  Repeat the preceding steps to configure network for the gateway instance of the other branch office.

    Make sure the two gateway instances are bound to the same CCN instance and the same CEN instance.


## Step 5. Configure security groups {#section_srm_v5d_p2b .section}

Configure security groups to allow local branches to access VPCs.

To configure the security groups, complete these steps:

1.  Log on to the [ECS console](https://ecs.console.aliyun.com).
2.  In the left-side navigation pane, click **Instances**.
3.  Locate the ECS instance in the target VPC, and then click **More** \> **Network and Security Group** \> **Security Group Configuration**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15407/15349539147646_en-US.png)

4.  Click **Security Groups** and click **Add Rules**.
5.  Configure a security group rule that allows access from offline branches.

    The following figure shows the security group configurations involved. You need set the authorization object as the private CIDR block of the local branch.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15407/15349539147648_en-US.png)


## Step 6. Test access {#section_hzm_tdk_l2b .section}

After completing the preceding configurations, you can use local clients to access cloud resources deployed in the connected VPCs to check if the new configurations take effect.

