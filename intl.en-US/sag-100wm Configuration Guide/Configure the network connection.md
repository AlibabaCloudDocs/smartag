# Configure the network connection {#task_qzw_mlh_qfb .task}

After you activate the Smart Access Gateway device, you must attach it to a Cloud Connect Network \(CCN\) instance and then attach the CCN instance to a Cloud Enterprise Network \(CEN\) instance, so that local branches can be connected to Alibaba Cloud.

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com/). 
2.  On the SAG page, find the target gateway instance. 
3.  Click **Configure Network** in the **Actions** column. 
4.  Complete network configurations according to the following information. 

    |Configuration|Description|
    |:------------|:----------|
    |**Name/ID**|Displays the name and ID of the Smart Access Gateway instance.|
    |**Private CIDR Block**|Configure the CIDR blocks used by the local gateway device to access Alibaba Cloud. Make sure all private CIDR blocks do not conflict with one another. Click **Add Private CIDR Block** to add more CIDR blocks. Up to five CIDR blocks can be added.The LAN port configuration of the local gateway device determines which private IP address is used:

    -   If the LAN port of the Smart Access Gateway device uses a dynamic IP address and DHCP is enabled on the client, the IP address used by the local client is allocated from the first CIDR block you specified.
    -   If the LAN port of the Smart Access Gateway device uses a static IP, the static IP must be in the specified CIDR block.
**Note:** CIDR blocks with a 32-bit mask are not supported.

|
    |**CCN Instance ID/Name**|Select the CCN instance to attach. You can use the default CCN instance or a created CCN instance.Cloud Connect Network \(CCN\) is a device access matrix composed of Alibaba Cloud distributed access gateways. After a Smart Access Gateway device is attached to a CCN instance, the gateway device can communicate with other gateway devices attached to the CCN instance.

**Note:** Make sure that the CCN instance and the Smart Access Gateway instance are in the same area.

|
    |**Bind CEN Instance**| Select the CEN instance to attach.

 After the CCN instance is attached to the CEN instance, all networks \(VPCs and VBRs\) attached to the CEN instance can communicate with the CCN instance.

**Note:** Make sure that the CCN instance and the CEN instance are in the same area. For more information, see [Cloud Connect Network](../../../../intl.en-US/User Guide/CCN/Cloud Connect Network.md#).

 |

    When you no longer require the Smart Access Gateway instance to be attached to a CCN instance, you can detach it from the CCN instance. On the SAG page, click **Unbind** in the actions column of the target gateway instance. After the gateway instance is detached from the CCN instance, local branches connected to the gateway instance cannot access Alibaba Cloud.


