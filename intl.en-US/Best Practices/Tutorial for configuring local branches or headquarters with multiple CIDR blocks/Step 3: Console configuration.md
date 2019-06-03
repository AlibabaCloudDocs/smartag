# Step 3: Console configuration {#concept_wct_lyy_mfb .concept}

After you have configured the gateway device, you need to activate the gateway device on the console and attach the CCN instance where the gateway belongs to the CEN instance where the physical connection belongs to access cloud services.

## Step 1: Activate the gateway {#section_kcg_ysw_rfb .section}

To activate the gateway, follow these steps:

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com/).
2.  On the SmartAG page, find the target gateway instance.
3.  Click **Activate** in the **Actions** column.

## Step 2: Configure the network connection {#section_dtn_xbk_l2b .section}

After activating the gateway device, you must attach the gateway instance to the CCN instance and then attach the CCN instance to the CEN instance where the target VPC belongs.

To configure the network, follow these steps:

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com/).
2.  On the SAG page, find the target gateway instance.
3.  Click **Configure Network** in the **Actions** column.
4.  On the Configure Network page, follow these steps:
    1.  **Private CIDR Block**: Configure the private CIDR blocks used by the local gateway device to access Alibaba Cloud. Make sure all private CIDR blocks do not conflict with one other. In this tutorial, the following three private CIDR blocks are added:

        -   10.0.13.0/24
        -   10.0.10.0/24
        -   10.0.20.0/24
        **Note:** Configuring a CIDR block with a 32-bit mask is not supported.

        Because the static IP address of the LAN port of the Smart Access Gateway is 10.0.13.1, 10.0.13.0/24 is added as the first private CIDR block in this tutorial.

        -   If the LAN port of the Smart Access Gateway device uses a dynamic IP address and DHCP is enabled on the client, the IP address used by the local client is allocated from the first private CIDR block specified by you.
        -   If the LAN port of the Smart Access Gateway device uses a static IP address, the static IP address must be in the specified private CIDR block.
    2.  **CCN Instance ID/Name**: Add the gateway instance to the CCN instance. Then gateway devices in the CCN instance can communicate with one another.

        In this tutorial, the default CCN is used. For more information, see [Cloud Connect Network](../intl.en-US/User Guide/CCN/Cloud Connect Network.md#).

5.  **Bind CEN Instance**: Select the CEN instance to attach. After the CCN instance is attached to the CEN instance, gateway devices in the CCN instance can communicate with networks \(VPCs and VBRs\) attached to the CEN instance.
6.  Click **OK**.

## Step 3: Configure an ACL {#section_bgj_2ww_dhb .section}

To configure an access control list \(ACL\), follow these steps:

1.  Log on to the [SAG console](https://smartag.console.aliyun.com/).
2.  Click **ACL** and configure an ACL rule for the SAG device. For more information, see [Configure an ACL](../intl.en-US/User Guide/Access control list (ACL)/Configure an access control list.md#).

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/23988/155953303341205_en-US.png)


## Step 4: Configure a security group {#section_srm_v5d_p2b .section}

Configure a security group to allow the local branches to access VPC.

To configure the security group, follow these steps:

1.  Log on to the [ECS Console](https://ecs.console.aliyun.com).
2.  In the left-side navigation pane, click **Instances**.
3.  Locate the target ECS instance in the target VPC, and then click **More** \> **Network and Security Group** \> **Configure Security Group**.
4.  Click **Add Rules** and click **Add Security Group Rule**.
5.  Configure a security group rule that allows access from local branches.

    Enter the private CIDR blocks of local branches as the authorization objects, that is, 10.0.13.0/24, 10.0.10.0/24, and 10.0.20.0/24.


