# Configure the network connection {#task_qzw_mlh_qfb .task}

After activating the Smart Access Gateway device, you must attach it to a CCN instance and then attach the CCN instance to a CEN instance, so that local branches can be connected to Alibaba Cloud.

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com/).
2.  On the SAG page, find the target gateway instance.
3.  Click **Configure Network** in the **Actions** column.
4.  Complete network configurations according to the following information. 

    |Configuration|Description|
    |:------------|:----------|
    |**Name/ID**|Displays the name and ID of the Smart Access Gateway instance.|
    |**CCN Instance ID/Name**|Select the CCN instance to attach. You can use the default CCN instance or a created CCN instance. CCN is a device access matrix composed of Alibaba Cloud distributed access gateways. After a Smart Access Gateway device is attached to a CCN instance, the gateway device can communicate with other gateway devices attached to the CCN instance.

**Note:** Make sure that the CCN instance and the Smart Access Gateway instance are in the same area.

 |
    |**Private CIDR Block**|Configure the CIDR blocks used by the local gateway device to access Alibaba Cloud. Make sure all CIDR blocks do not conflict with one another. Click **Add Private CIDR Block** to add more CIDR blocks. You can add up to five CIDR blocks. The LAN port configuration of the local gateway device determines which private IP address is used:

    -   If the LAN port of the Smart Access Gateway device uses a dynamic IP and DHCP is enabled on the client, the IP address used by the local client is allocated from the first CIDR block specified by you.
    -   If the LAN port of the Smart Access Gateway device uses a static IP, the static IP must be in the specified CIDR block.
 **Note:** 

    -   The priviate CIDR block of the Smart Access Gateway instance must belong to the CIDR block of the connected CCN instance.
    -   Configuring a CIDR block with a 32-bit mask is not supported.
 |
    |**Enable SNAT**|     -   Disable SNAT: Networks attached to the CCN instance can directly communicate with each other. Make sure that the CIDR blocks of the networks do not conflict with one another.
    -   Enable SNAT: The SNAT function is enabled to hide internal addresses and resolve private address conflict. Local sites can only initiate access and cannot be accessed.
        -   **Public IP Address**: An IP address in the SNAT CIDR block of the CCN instance. If you leave this option blank, the system automatically allocates an available IP address from the SNAT CIDR block of the CCN instance.
        -   **Internal CIDR Block**: The private CIDR blocks used by local terminals to access Alibaba Cloud. Make sure that the private CIDR blocks do not conflict with one another.
 |

    When you no longer need the Smart Access Gateway instance to be attached to a CCN instance, you can detach it from the CCN instance. On the SAG page, click **Unbind** in the actions column of the target gateway instance. After the gateway instance is detached from the CCN instance, local branches connected to the gateway instance cannot access Alibaba Cloud.


