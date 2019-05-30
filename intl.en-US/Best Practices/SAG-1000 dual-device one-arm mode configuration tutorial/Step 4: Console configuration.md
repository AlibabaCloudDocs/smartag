# Step 4: Console configuration {#concept_wct_lyy_mfb .concept}

After you have configured the Smart Access Gateway device \(SAG device\), you need to activate the SAG device on the Smart Access Gateway console and complete the network configurations.

## Step 1: Configure the network configuration {#section_dtn_xbk_l2b .section}

After activating the SAG device, you must attach the SAG instance to the CCN instance and attach the CCN instance to the CEN instance to which the target VPCs belong.

To configure the network, follow these steps:

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com/).
2.  On the SAG page, find the target gateway instance.
3.  Click **Configure Network** in the **Actions** column.
4.  On the Configure Network page, configure the following parameters:
    1.  **Private CIDR Block**: Configure the private CIDR blocks used by the local clients to access Alibaba Cloud. Make sure all private CIDR blocks do not conflict with one another.

        In this tutorial, enter 192.168.3.0/24. Configuring a CIDR block with a 32-bit mask is not supported.

    2.  **CCN Instance ID/Name**: Add the gateway instance to the CCN instance. Then gateway devices in the CCN instance can communicate with one another.

        In this tutorial, the default CCN is used. For more information, see [Cloud Connect Network](../intl.en-US/User Guide/CCN/Cloud Connect Network.md#).

5.  **Bind CEN Instance**: Select the CEN instance to attach. After the CCN instance is attached to the CEN instance, gateway devices in the CCN instance can communicate with networks \(VPCs and VBRs\) attached to the CEN instance.
6.  Click **OK**.

## Step 2: Activate the SAG device {#section_lyw_rbk_l2b .section}

After configuring the network connection, you must activate the SAG device:

To activate the SAG device, follow these steps:

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com/).
2.  On the SmartAG page, find the target gateway instance.
3.  Click **Activate** in the **Actions** column.

## Step 3: Configure an ACL {#section_bgj_2ww_dhb .section}

To configure an access control list \(ACL\), follow these steps:

1.  Log on to the [SAG console](https://smartag.console.aliyun.com/).
2.  Click **ACL** and configure an ACL rule for the SAG device. For more information, see [Configure an ACL rule](../intl.en-US/User Guide/Access control list (ACL)/Configure an access control list.md#).

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/23988/155923010141205_en-US.png)


## Step 4: Configure a security group {#section_srm_v5d_p2b .section}

Configure a security group to allow local branches to access the VPCs.

To configure the security group, follow these steps:

1.  Log on to the [ECS Console](https://ecs.console.aliyun.com).
2.  In the left-side navigation pane, click **Instances**.
3.  Locate the target ECS instance in the target VPC, and then click **More** \> **Network and Security Group** \> **Configure Security Group**.
4.  Click **Add Rules** and click **Add Security Group Rule**.
5.  Configure a security group rule that allows access from local branches.

    The following figure shows the security group configurations in this tutorial. You must enter the private CIDR blocks of the local branches as the authorization objects.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/23710/155923010113853_en-US.png)


