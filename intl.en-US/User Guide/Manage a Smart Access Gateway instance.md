# Manage a Smart Access Gateway instance {#concept_vy1_gjs_j2b .concept}

After purchasing a Smart Access Gateway device, you can use the corresponding Smart Access Gateway instance to activate or lock the device, or add it to CCN.

## Activate the gateway device {#section_n5p_bc2_l2b .section}

After receiving the gateway device, you need to activate it on the console. Billing starts right after the device is activated.

**Note:** If the device is not manually activated, the system automatically activates the gateway device and billing starts 15 days after the device is received by default.

To activate the Smart Access Gateway device, complete these steps:

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com/).
2.  On the SmartAG page, find the target gateway instance.
3.  Click **Activate** in the **Actions** column.

## Attach to CCN {#section_vpv_pd2_l2b .section}

After activating the Smart Access Gateway device, you also need to attach it to CCN and then attach the CCN instance to a CEN instance, so that on-premises branches can be connected to Alibaba Cloud.

To configure the network, complete these steps:

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com/).
2.  On the SmartAG page, find the target gateway instance.
3.  Click **Configure Network** in the **Actions** column.
4.  Complete network configurations according to the following information.

    |Configuration|Description|
    |:------------|:----------|
    |**Name/ID**|Displays the name and ID of the Smart Access Gateway instance.|
    |**Private CIDR Block**|Configure the private CIDR blocks used by the local clients to access Alibaba Cloud.  Make sure all private CIDR blocks do not conflict with each other. Click **Add Private CIDR Block** to add more CIDR blocks. Up to five private CIDR blocks can be configured.The LAN port configuration of the local gateway device determines which private IP address is used:

    -   If the LAN port of the Smart Access Gateway device uses the dynamic IP mode and DHCP is enabled on the client, the IP address that the local client uses for communication are allocated from the first specified private CIDR block.
    -   If the LAN port of the Smart Access Gateway device is in static IP mode, the static IP must be in the specified private CIDR block.
|
    |**CCN Instance ID/Name**|Select the CCN instance to attach. You can use the default CCN instance or a created CCN instance.CCN is a device access matrix composed of Alibaba Cloud distributed access gateways. After a Smart Access Gateway device is attached to a CCN instance, the gateway device can communicate with other gateway devices attached to the CCN instance.

**Note:** Make sure that the CCN instance and Smart Access Gateway instances attached to it are in the same area.

|
    |**Bind CEN Instance**| Select the CEN instance to attach.

 After the CCN instance is attached to the CEN instance, all networks \(VPCs and VBRs\) attached to the CEN instance can communicate with the CCN instance.

**Note:** Make sure that the CCN instance and the CEN instance are in the same area. For more information, see [CCN areas](reseller.en-US/User Guide/Cloud Connect Network.md#section_sb4_vqf_l2b).

 |


## Enable locking {#section_zrb_55t_j2b .section}

When the gateway device is offline, you can lock the gateway device and then the device cannot be used any more.

To lock a Smart Access Gateway instance, follow these steps:

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com/).
2.  On the SmartAG page, find the target gateway instance.
3.  On the Instance Details page, click the **Enable** option for **Offline Lock**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15410/15516127197050_en-US.png)

4.  Enter a threshold \(in seconds\) for the locked status and click **OK**.

    If, for example, 3600 is entered, the gateway device becomes locked after 60 minutes.


## Disable locking {#section_ivc_w5t_j2b .section}

To disable the locked status of the gateway device, follow these steps:

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com/).
2.  On the SmartAG page, click the ID of the target gateway instance.
3.  On the Instance Details page, click the **Disable** option for **Offline Lock**.

## Modify the bandwidth {#section_s1w_rbg_l2b .section}

To disable the bandwidth of the gateway device, follow these steps:

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com/).
2.  On the SmartAG page, find the target gateway instance.
3.  On the Instance Details page, click the **Upgrade** or **Downgrade** option for **Peak Bandwidth**.
4.  On the Update page, adjust the bandwidth and complete the payment.

## Renew an instance {#section_vfw_lcg_l2b .section}

To renew an instance and avoid service interruption, follow these steps:

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com/).
2.  On the SmartAG page, find the target instance.
3.  Click **More** \> **Renew**.
4.  Select the renewal duration and complete the payment.

