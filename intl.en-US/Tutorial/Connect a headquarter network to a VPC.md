# Connect a headquarter network to a VPC {#concept_hxx_njz_k2b .concept}

This tutorial takes a company as an example to show how to use Smart Access Gateway in the single-arm bypass mode to quickly connect a headquarters network to a VPC without changing the existing network. The clients of the company are configured with switches.

## Scenario {#section_xc3_bkz_k2b .section}

The headquarters network needs to communicate with the business system on the cloud through the carrier broadband, so that the headquarters can perform Operations and Maintenance management on cloud resources and the local data can be synchronized with the data on the cloud.

The network configurations in this tutorial are as follows:

-   A VPC has been created in Alibaba Cloud and ECS instances have been created in the VPC and are configured. The CIDR block of the VPC is 192.168.0.0/24.
-   An egress router/firewall and a core switch are deployed in the headquarters network. The CIDR block of the local server is 192.168.5.0/24, 172.16.1.0/24, 10.1.1.0/24, and 10.1.20.0/24.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16771/15342544127657_en-US.png)


## Network architecture {#section_vhm_y32_p2b .section}

By configuring Smart Access Gateway, the headquarters network can rapidly access Alibaba Cloud, as shown in [Figure 1](#fig_eny_fcj_p2b). In this networking mode, the egress router or firewall device must have SNAT enabled and Smart Access Gateway must have SNAT disabled.

**Note:** If you use the common bypass routing mode as shown in [Figure 2](#fig_yvt_5cj_p2b), you can enable the SNAT function of Smart Access Gateway.

![](images/7658_en-US.png "Single-arm bypass routing mode")

![](images/7700_en-US.png "Common bypass routing mode")

## Step 1 Buy a Smart Access Gateway device {#section_onw_h5c_l2b .section}

After you buy a Smart Access Gateway device on the console, Alibaba Cloud delivers the device to you and create a Smart Access Gateway instance for you to manage the network configuration.

To buy a Smart Access Gateway device, complete these steps:

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com).
2.  Click **Create SmartAG**.
3.  Configure the Smart Access Gateway device according to the following information and click **Buy Now**.

    |Configuration|Description|
    |:------------|:----------|
    |**Area**|Select the area of the Smart Access Gateway. The delivery address of the gateway device must be in the selected area.Each Smart Access Gateway area corresponds to a country. Currently only the Mainland China area is supported.

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
    |**Use Method**|Currently only the single-device mode is supported, that is, an on-premises organization can only buy one Smart Access Gateway device to access Alibaba Cloud.|
    |**Subscription Duration**|Select the purchase duration.In this tutorial, select **1 month**.

|

4.  Confirm the order information, and then click **Buy Now**.
5.  On the Delivery address dialog box, enter the delivery address of the gateway device and click **Place an Order**.

    You can check whether the order is successfully placed on the page of Smart Access Gateway instances. The system will deliver the device within two days after the order is placed. If no device is received within two days, you can submit a ticket to check the logistics status.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15407/15342544127051_en-US.png)


## Step 2 Configure the network connection {#section_dtn_xbk_l2b .section}

After activating the Smart Access Gateway device, you also need to attach it to CCN and then attach the CCN instance to a CEN instance, so that on-premises branches can be connected to Alibaba Cloud.

To configure the network, complete these steps:

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com/).
2.  On the SmartAG page, find the target gateway instance.
3.  Click **Configure Network** in the **Actions** column.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16771/15342544127659_en-US.png)

4.  On the Configure Network page, complete these steps:
    1.  **Private CIDR Block**: Configure the private CIDR blocks used by the local clients to access Alibaba Cloud. Make sure all private CIDR blocks do not conflict with each other.

        In this tutorial, enter 172.16.1.0/24, 192.168.5.0/24, 10.1.10.0/24, and 10.1.20.0/24. For more information, see [Network configuration](../intl.en-US/User Guide/Manage a Smart Access Gateway instance.md#table_xrf_xd2_l2b).

    2.  **CCN Instance ID/Name**: Add the gateway instance to the CCN instance. After being added to the CCN instance, gateway devices can communicate with one another.

        In this tutorial, select the default CCN instance. For more information, see [Cloud Connect Network](../intl.en-US/User Guide/Cloud Connect Network.md#).

5.  **Bind CEN Instance**: Select the CEN instance to attach. After the CCN instance is attached to the CEN instance, all networks \(VPCs and VBRs\) attached to the CEN instance can communicate with gateway devices in the CCN instance.

    In this tutorial, select the CEN instance associated with the VPC.

    **Note:** Make sure that the CCN instance and the CEN instance are in the same area. For more information, see [CCN areas](../intl.en-US/User Guide/Cloud Connect Network.md#section_sb4_vqf_l2b).

6.  Click **OK**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16771/15342544127662_en-US.png)


## Step 3 Connect and activate the gateway device {#section_xjs_lrj_l2b .section}

After you receive the gateway device, check the accessories according to [Gateway device description](../intl.en-US/User Guide/Manage a Smart Access Gateway device/Gateway device description.md#).

After receiving the gateway device, you need to activate it.

To activate the gateway, complete these steps:

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com/).
2.  On the SmartAG page, find the target gateway instance.
3.  Click **Activate** in the **Actions** column.

## Step 4 Configure the gateway device {#section_lyw_rbk_l2b .section}

After you start the gateway device, connect the WAN port to the network cable and connect the LAN ports to a local client.

**Note:** You cannot log on to the web configuration page through the WAN port from Smart Access Gateway. To modify configurations such as the public IP of Smart Access Gateway, connect the local client to a LAN port of the gateway device to log on the web configuration page.

To configure the gateway device, complete these steps:

1.  Enter https://192.168.0.1 in the browser of the local client and set the initial password.

    By default, the local client can obtain addresses in the CIDR block 192.168.0.0/24.

2.  Configure the WAN port. The WAN port configurations in this tutorial are as follows.

    The gateway address is the IP address of the peer port on the core switch. Disable the SNAT function to enable SNAT on the egress router/firewall.

3.  Configure the LAN ports. The LAN port configurations in this tutorial are as follows.
4.  After completing the network configuration of the gateway device, Connect the WAN port of the Smart Access Gateway device to G 0/5 of the core switch to connect local clients with the core switch. The NIC of the local client uses a static IP address and the core switch serves as the gateway, as shown in the following figure.

## Step 5 Configure the core switch and the egress router {#section_ejf_xl2_p2b .section}

To configure the core switch, complete these steps:

1.  Configure the interface connected to the Smart Access Gateway device and configure the IP address:

    ```
    interface GigabitEthernet 0/5———//In the bypass mode, connect it to the WAN port of Smart Access Gateway
    no switchport
    ip address 192.168.50.1 255.255.255.0
    ```

2.  Configure the route to forward traffic from the headquarters to Alibaba Cloud:

    ```
    ip route 192.168.0.0 255.255.255.0 192.168.50.2———// Route traffic from local clients to Smart Access Gateway
    ```

3.  Configure a route pointing to Smart Access Gateway in the egress router

    ```
    ip route 192.168.50.0 255.255.255.0 192.168.100.101——// Forward traffic from Alibaba Cloud to the core switch
    
    ```


## Step 6 Configure security groups  {#section_irj_zl2_p2b .section}

Configure security groups to allow branch organizations to access VPC.

To configure security groups, complete these steps:

1.  Log on to the [ECS console](https://ecs.console.aliyun.com).
2.  In the left-side navigation pane, click **Instances**.
3.  Find the ECS instance in the target VPC, and click **More** \> **Network and Security Group** \> **Security Group Configuration**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15407/15342544127646_en-US.png)

4.  Click **Add Rules** and then click **Add Security Group Rule**.
5.  Configure a security group rule that allows the access of offline branches.

    The following figure shows the security group configuration in this tutorial. You need to configure the authorization object to the private CIDR block of the local branch.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15407/15342544127648_en-US.png)


## Step 7 Test the access {#section_hzm_tdk_l2b .section}

After completing the preceding configurations, you can access cloud resources deployed in the connected VPC from local clients to check if the configurations take effect.

