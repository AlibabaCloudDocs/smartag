# Set up network connections

After you purchase a Smart Access Gateway \(SAG\) APP instance, you must set up network connections between the SAG APP instance and Alibaba Cloud resources to enable clients to access resources on Alibaba Cloud.

1.  Log on to the [SAG console](https://smartag.console.aliyun.com).

2.  In the left-side navigation pane, click **Smart Access Gateway APP**.

3.  In the top menu bar, select the region.

4.  On the Smart Access Gateway APP page, find the instance and click **Network Configuration** in the **Actions** column.

5.  Set the following parameters:

    |Parameter|Description|
    |---------|-----------|
    |**Instance Name/ID**|Displays the name and ID of the SAG APP instance.|
    |**CCN**|Select a Cloud Connect Network \(CCN\) instance to be associated with the SAG instance. CCN is an important component of SAG. After an SAG APP instance is associated with a CCN instance, all clients associated with the SAG APP instance can communicate with gateway devices associated with the CCN instance. For more information about CCN, see [Introduction to CCN](/intl.en-US/Configuration Guide/Cloud Connect Network/Introduction to CCN.md). Use one of the following methods to associate the SAG instance with a CCN instance:

    -   **Existing CCN**: If you have already created CCN instances in the current area, you can select an existing CCN instance from the drop-down list.
    -   **Create CCN**: If you have not created a CCN instance, enter an instance name. The system then creates a CCN instance and automatically associates it with the SAG APP instance.

The name must be 2 to 100 characters in length, and can contain digits, underscores \(\_\), and hyphens \(-\). The name must start with a letter. |
    |**Standby and Active DNS**|Optional. You can specify custom active and standby DNS servers that the clients use to connect to the private network through the SAG app.Before you specify custom DNS servers, take note of the following items:

    -   After you configure the DNS servers, the system automatically synchronizes the DNS settings to the clients. All traffic transmitted through your clients is resolved by the specified DNS servers. If your clients require access to the Internet, make sure that the specified DNS servers can resolve public addresses.
    -   If the clients use PrivateZone to connect to Alibaba Cloud, set the DNS server addresses to 100.100.2.136 and 100.100.2.138. For more information about PrivateZone, see[What is PrivateZone](https://www.alibabacloud.com/help/zh/doc-detail/64611.htm?spm=a2c63.p38356.b99.2.31581896N9XFtE).
    -   For Android and macOS operating systems, you must use the SAG app 2.1.1 or later versions to configure DNS. For more information about clients, see [Install the SAG app](/intl.en-US/Smart Access Gateway APP/User guide for end users/Install the SAG app.md).
**Note:** If your client runs in iOS 13 or later, the specified custom DNS servers may not take effect after you configure DNS. In this case, restart the client and reconnect to Alibaba Cloud. |
    |**Private CIDR Block**|Specify the private CIDR blocks used to connect to Alibaba Cloud. When the client is connecting to Alibaba Cloud, an idle IP address that falls within the private CIDR blocks is automatically assigned to the client. Make sure that the private CIDR blocks do not overlap with each other.

You can click **Add Private CIDR Block** to add more private CIDR blocks. You can add at most five private CIDR blocks. |

6.  Click **OK**.


