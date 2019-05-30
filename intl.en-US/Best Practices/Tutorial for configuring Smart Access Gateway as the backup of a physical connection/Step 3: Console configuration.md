# Step 3: Console configuration {#concept_wct_lyy_mfb .concept}

After you have configured the gateway device, you need to activate it on the console and attach the Cloud Connect Network \(CCN\) instance where the gateway belongs to the Cloud Enterprise Network \(CEN\) instance where the physical connection belongs.

## Step 1: Activate the gateway {#section_kcg_ysw_rfb .section}

To activate the gateway, follow these steps:

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com/).
2.  On the SmartAG page, find the target gateway instance.
3.  Click **Activate** in the **Actions** column.

## Step 2: Configure active/standby links {#section_i23_ysw_rfb .section}

To configure active/standby links, follow these steps:

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com/).
2.  On the SAG page, find the target gateway instance.
3.  Click the ID of the target instance, and then in the **High-Availability Configurations** area, enable link-level backup.

    ![](images/21679_en-US.png)

4.  Complete the following configurations, and then click **OK**:
    -   **High Availability Mode**: Select **Channel**.
    -   **Main Channel**: Select the established physical connection.

        **Note:** Make sure the selected physical connection does not use Express Connect to establish a peering connection and that the corresponding Virtual Border Router \(VBR\) has configured Border Gateway Protocol \(BGP\) routing. If the physical connection is used to synchronize BGP routes for the VBR, check that the routes do not conflict with the CIDR block used by Smart Access Gateway to communicate with the switch.


## Step 3: Configure the network connection {#section_dtn_xbk_l2b .section}

After activating the gateway device, you must attach the gateway instance to the CCN and attach the CCN to the CEN where the target VPC belongs.

**Note:** Make sure that the Smart Access Gateway instance and the VBR to which the physical connection belongs are in the same CEN instance.

To configure the network, follow these steps:

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com/).
2.  On the SAG page, find the target gateway instance.
3.  Click **Configure Network** in the **Actions** column.
4.  On the Configure Network page, follow these steps:
    1.  **Private CIDR Block**: Configure the private CIDR blocks used by the local clients to access Alibaba Cloud. Make sure all private CIDR blocks do not conflict with each another.

        In this tutorial, enter 192.168.3.0/24.

    2.  **CCN Instance ID/Name**: Add the gateway instance to the CCN instance. Then gateway devices in the CCN instance can communicate with one another.

        In this tutorial, the default CCN is used. For more information, see [Cloud Connect Network](../intl.en-US/User Guide/CCN/Cloud Connect Network.md#).

5.  **Bind CEN Instance**: Select the CEN instance to attach. After the CCN instance is attached to the CEN instance, gateway devices in the CCN instance can communicate with networks \(VPCs and VBRs\) attached to the CEN instance.
6.  Click **OK**.

## Step 4: Configure an ACL {#section_bgj_2ww_dhb .section}

To configure an access control list \(ACL\), follow these steps:

1.  Log on to the [SAG console](https://smartag.console.aliyun.com/).
2.  Click **ACL** and configure an ACL rule for the SAG device. For more information, see [Configure an ACL](../intl.en-US/User Guide/Access control list (ACL)/Configure an access control list.md#).

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/23988/155923034141205_en-US.png)


## Step 5: Configure a security group {#section_srm_v5d_p2b .section}

Configure a security group to allow the local branches to access VPC.

To configure the security group, follow these steps:

1.  Log on to the [ECS Console](https://ecs.console.aliyun.com).
2.  In the left-side navigation pane, click **Instances**.
3.  Locate the ECS instance in the target VPC, and then click **More** \> **Network and Security Group** \> **Configure Security Group**.
4.  Click **Add Rules** and click **Add Security Group Rule**.
5.  Configure a security group rule that allows access from local branches.

    You must enter the private CIDR blocks of local branches as the authorization objects \(which in this case is 192.168.3.0/24\).


