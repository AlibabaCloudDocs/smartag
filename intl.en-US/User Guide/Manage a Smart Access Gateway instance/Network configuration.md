# Network configuration {#task_xhm_wjb_mfb .task}

After you activate the gateway device, you must configure the private IP addresses of the local branches and the CCN instance to attach in the console so that local clients can connect to Alibaba Cloud.

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com/). 
2.  On the SAG page, find the target gateway instance. 
3.  Click **Configure Network** in the **Actions** column. 
4.  Complete network configurations according to the following information. 

    |Configuration|Description|
    |:------------|:----------|
    |**Name/ID**|Displays the name and ID of the Smart Access Gateway instance.|
    |**Private CIDR Block**|Configure the CIDR blocks used by the local gateway device to access Alibaba Cloud. Make sure all CIDR blocks do not conflict with one another. Click **Add Private CIDR Block** to add more CIDR blocks. Up to five CIDR blocks can be added.The LAN port configuration of the local gateway device determines which private IP address is used:

    -   If the LAN port of the Smart Access Gateway device uses a dynamic IP and DHCP is enabled on the client, the IP address used by the local client is allocated from the first CIDR block specified by you.
    -   If the LAN port of the Smart Access Gateway device uses a static IP, the static IP must be in the specified CIDR block.
**Note:** Configuring a CIDR block with a 32-bit mask is not supported.

|
    |**CCN Instance ID/Name**|Select the CCN instance to attach. You can use the default CCN instance or a created CCN instance.CCN is a device access matrix composed of Alibaba Cloud distributed access gateways. After a Smart Access Gateway device is attached to a CCN instance, the gateway device can communicate with other gateway devices attached to the CCN instance.

**Note:** Make sure that the CCN instance and the Smart Access Gateway instance are in the same area.

|
    |**Bind CEN Instance**| Select the CEN instance to attach.

 After the CCN instance is attached to the CEN instance, all networks \(VPCs and VBRs\) attached to the CEN instance can communicate with the CCN instance.

**Note:** Make sure that the CCN instance and the CEN instance are in the same area. For more information, see [CCN areas](intl.en-US/User Guide/Cloud Connect Network.md#section_sb4_vqf_l2b).

 |

    When you do not need the Smart Access Gateway instance to be bound to a CCN instance, you can detach it from the CCN instance. On the SAG page, click **Unbind** in the actions column of the target gateway instance. After the gateway instance is detached from the CCN instance, local branches connected to the gateway instance cannot access Alibaba Cloud.


