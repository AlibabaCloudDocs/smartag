# Connect local branches to VPCs in the same area {#concept_hxx_njz_k2b .concept}

This tutorial takes Ningbo branch and Hangzhou branch as an example, illustrating how to connect these two branches to the VPCs in Shanghai and Beijing using Smart Access Gateway. Clients of the on-premises organizations directly access the VPCs through Smart Access Gateway.

## Scenarios {#section_xc3_bkz_k2b .section}

To connect local organizations to VPCs in the same area, you only need to attach the CCN instance associated with the Smart Access Gateway instances to the CEN instance in the same area.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15407/15342544506809_en-US.png)

## Step 1 Buy a Smart Access Gateway device {#section_onw_h5c_l2b .section}

After you buy a Smart Access Gateway device on the console, Alibaba Cloud delivers the device to you and create a Smart Access Gateway instance for you to manage the network configuration.

To buy a Smart Access Gateway device, complete these steps:

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com).
2.  Click **Create SmartAG**.
3.  Configure the Smart Access Gateway device according to the following information and click **Buy Now**.

    |Configuration|Description|
    |:------------|:----------|
    |**Region**|Select the area of the Smart Access Gateway. The delivery address of the gateway device must be in the selected area.Each Smart Access Gateway area corresponds to a country. Currently only the Mainland China area is supported.

|
    |**Instance**|Enter an instance name.The name can contain 2 to 128 characters and must start with an English letter. It can contain numbers and the following special characters:

. \_-

In this tutorial, enter **Hangzhou branch**.

|
    |**Hardware Specification**|Select the hardware specification for the gateway device.The configurations of gateways with different specifications are also different. For more information, see [Specifications of Smart Access Gateway device](../intl.en-US/User Guide/Manage a Smart Access Gateway device/Gateway device description.md#section_gdf_25s_j2b).

In this tutorial, select **Standard edition**.

|
    |**Peak Bandwidth**|Select the bandwidth of the Smart Access Gateway device.In this tutorial, select **2Mpbs**.

|
    |**Procedure **|Currently only the single-device mode is supported, that is, an on-premises organization can only buy one Smart Access Gateway device to access Alibaba Cloud.|
    |**Subscription Duration**|Select the purchase duration.In this tutorial, select **1 month**.

|

4.  Confirm the order information, and then click **Buy Now**.
5.  In the Delivery address dialog box, enter the delivery address of the gateway device and click **Place an Order**.

    You can check whether the order is successfully placed on the page of Smart Access Gateway instances. The system will deliver the device within two days after the order is placed. If no device is received within two days, you can submit a ticket to check the logistics status.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15407/15342544507051_en-US.png)

6.  Peat the preceding steps to buy a Smart Access Gateway device for the Ningbo branch.

## Step 2 Connect the gateway device {#section_xjs_lrj_l2b .section}

After you receive the gateway device, check the accessories according to [Gateway device description](../intl.en-US/User Guide/Manage a Smart Access Gateway device/Gateway device description.md#). After you start the gateway device, connect the WAN port to the network cable and connect the LAN ports to local clients.

In this tutorial, the gateway device can be directly connected to the clients in Hangzhou branch and Ningbo branch, so you can use the default gateway configuration. If you need to configure the WAN port and LAN ports, see [Configure a Smart Access Gateway device](../intl.en-US/User Guide/Manage a Smart Access Gateway device/Configure a Smart Access Gateway device.md#).

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15407/15342544517076_en-US.png)

## Step 3 Activate the gateway {#section_lyw_rbk_l2b .section}

After receiving the gateway device, you need to activate it.

To activate the gateway, complete these steps:

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com/).
2.  On the SmartAG page, find the target gateway instance.
3.  Click **Activate** in the **Actions** column.

## Step 4 Configure the network connection {#section_dtn_xbk_l2b .section}

After activating the Smart Access Gateway device, you also need to attach it to CCN and then attach the CCN instance to a CEN instance, so that on-premises branches can be connected to Alibaba Cloud.

To configure the network, complete these steps:

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com/).
2.  On the SmartAG page, find the target gateway instance.
3.  Click **Configure Network** in the **Actions** column.
4.  On the Configure Network page, complete these steps:
    1.  **Private CIDR Block**: Configure the private CIDR blocks used by the local clients to access Alibaba Cloud. Make sure all private CIDR blocks do not conflict with each other.

        In this tutorial, enter 172.16.0.0/12. In this tutorial, the local branch uses the default gateway configuration, so the IP address used by the local client to access Alibaba Cloud is allocated from the CIDR block 172.16.0.0/12. For more information, see [Network configuration](../intl.en-US/User Guide/Manage a Smart Access Gateway instance.md#table_xrf_xd2_l2b).

    2.  **CCN Instance ID/Name**: Add the gateway instance to the CCN instance. After being added to the CCN instance, gateway devices can communicate with one another.

        In this tutorial, select the default CCN instance. For more information, see [Cloud Connect Network](../intl.en-US/User Guide/Cloud Connect Network.md#).

5.  **Bind CEN Instance**: Select the CEN instance to attach. After the CCN instance is attached to the CEN instance, all networks \(VPCs and VBRs\) attached to the CEN instance can communicate with gateway devices in the CCN instance.

    In this tutorial, the CEN instance associated with the Shanghai VPC and Beijing VPC is selected.

    **Note:** Make sure that the CCN instance and the CEN instance are in the same area. For more information, see [CCN areas](../intl.en-US/User Guide/Cloud Connect Network.md#section_sb4_vqf_l2b).

6.  Click **OK**.
7.  Repeat the preceding steps to configure network for the gateway instance of the other branch organization.

    Make sure the two gateway instances are bound to the same CCN instance and the same CEN instance.


## Step 5 Configure security groups {#section_srm_v5d_p2b .section}

Configure security groups to allow branch organizations to access VPC.

To configure the security groups, complete these steps:

1.  Log on to the [ECS console](https://ecs.console.aliyun.com).
2.  In the left-side navigation pane, click **Instances**.
3.  Locate the ECS instance in the target VPC, and then click **More** \> **Network and Security Group** \> **Security Group Configuration**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15407/15342544517646_en-US.png)

4.  Click **Security Groups** and click **Add Rules**.
5.  Configure a security group rule that allows the access of offline branches.

    The following figure shows the security group configuration in this operation. You need to configure the authorization object to the private CIDR block of the local branch.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15407/15342544517648_en-US.png)


## Step 6 Test the access {#section_hzm_tdk_l2b .section}

After completing the preceding configurations, you can access cloud resources deployed in the connected VPCs from local clients to check if the configurations take effect.

