# Create a CCN instance {#task_ykl_fmb_mfb .task}

To connect local branches attached to a Smart Access Gateway device to Alibaba Cloud, you must first create a CCN instance, attach the gateway instance to the CCN instance, and then attach the CCN instance to the CEN instance.

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com/).
2.  In the left-side navigation pane, click **CCN**.
3.  Click **Create CCN Instance**.
4.  On the Create CCN Instance page, configure the CCN instance according to the configuration items described in the following table. 

    |Parameter|Description|
    |---------|-----------|
    |**Name**|The name of the CCN instance. It must be 2 to 128 characters in length and can contain letters, numbers, underscores \(\_\), and hyphens \(-\). It must begin with a letter.

 |
    |**Description**|The description of the CCN instance. It must be 2 to 128 characters in length and can contain letters, numbers, underscores \(\_\), and hyphens \(-\). It must begin with a letter.

 |
    |**Private CIDR Block**|The private CIDR blocks used by the CCN instance to access Alibaba Cloud. Click **Add Private CIDR Block** to add more. You can click Add Private CIDR Block to add up to CIDR blocks as needed. **Note:** 

    -   The private CIDR blocks of the CCN instance are the collections of the IP address ranges of attached Smart Access Gateway instances. Make sure that the specified private CIDR blocks do not conflict with the CIDR block of the VPC to connect.
    -   We recommend that you use RFC private CIDR blocks 10.0.0.0/8, 172.16.0.0/12, and 192.168.0.0/16. By default, the CIDR block 192.168.0.0/16 is used if you leave the option blank.

By default, the mask is /8 to /24 in length. To use other masks, [open a ticket](https://selfservice.console.aliyun.com/ticket/category/smartag/today).

 |
    |**SNAT CIDR Block**|A CIDR block that belongs to the private CIDR blocks of the CCN instance. The mask is /8 to /30 in length. **Note:** You can use the SNAT function to resolve IP address conflicts or hide intranet IP addresses. The SNAT CIDR block is a subset of the private CIDR blocks of the CCN instance. When you configure the SNAT rule, you can use an IP address in the SNAT CIDR block as the public IP address.

 |

5.  Click **OK**.

