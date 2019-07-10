# Configure the network {#task_xhm_wjb_mfb .task}

After you activate a Smart Access Gateway \(SAG\) device, you must configure the private IP addresses of the local branches and configure the CCN instance to attach in the console so that local clients can connect to Alibaba Cloud.

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com/).
2.  In the left-side navigation pane, click **Smart Access Gateway** and then click the ID of the target instance.
3.  Click **Configure Network** in the **Actions** column.
4.  Complete network configurations according to the following information. 

    |Configuration|Description|
    |:------------|:----------|
    |**Name/ID**|Displays the name and ID of the SAG instance.|
    |**Private CIDR Block**|Configure the CIDR blocks used by the local gateway device to access Alibaba Cloud. Click **Add Private CIDR Block** to add more CIDR blocks. Up to five CIDR blocks can be added. The LAN port configuration of the local gateway device determines which private IP address is used:

    -   If the LAN ports of the SAG device uses a dynamic IP address and DHCP is enabled on the client, the IP address used by the local client is allocated from the first CIDR block specified by you.
    -   If the LAN ports of the SAG device uses a static IP address, the static IP address must be in the specified CIDR block.
 **Note:** 

    -   The private CIDR blocks of the SAG instance must belong to the CIDR block of the CCN instance.
    -   Configuring a CIDR block with a 32-bit mask is not supported.
 |
    |**CCN Instance ID/Name**|Select the CCN instance to attach. You can use the default CCN instance or a created CCN instance. CCN is a device access matrix composed of Alibaba Cloud distributed access gateways. After an SAG device is attached to a CCN instance, the SAG device can communicate with other gateway devices attached to the CCN instance.

**Note:** Make sure that the CCN instance and the SAG instance are in the same area.

 |
    |**Enable SNAT**|     -   Disable SNAT: Networks attached to the CCN instance can directly communicate with each other. Make sure that the CIDR blocks of the networks do not conflict with one another.
    -   Enable SNAT: The SNAT function is enabled to hide internal addresses and resolve private address conflict. Local sites can only initiate access and cannot be accessed.
        -   **Public IP Address**: An IP address in the SNAT CIDR block of the CCN instance. If you leave this option blank, the system automatically allocates an available IP address from the SNAT CIDR block of the CCN instance.
        -   **Internal IP Address**: The private CIDR blocks used by local terminals to access Alibaba Cloud. Make sure that the private CIDR blocks do not conflict with one another.
 |

    When you do not need the SAG instance to be attached to a CCN instance, you can detach it from the CCN instance. On the Smart Access Gateway page, click **Unbind** in the **Actions** column of the target SAG instance. After the SAG instance is detached from the CCN instance, local branches connected to the SAG instance cannot access Alibaba Cloud.


