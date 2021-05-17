# Advertise routes to Alibaba Cloud

A routing method specifies how a Smart Access Gateway \(SAG\) device learns the private CIDR block of the on-premises network. After you configure the routing method, SAG devices can automatically advertise the learned private CIDR block of the on-premises network to Alibaba Cloud.

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com).

2.  In the left-side navigation pane, click **Smart Access Gateway**.

3.  In the top menu bar, select the region.

4.  On the Smart Access Gateway page, find the SAG instance.

5.  Use one of the following methods to open the Network Configuration tab.

    -   Click the ID of the SAG instance. On the instance details page, click the **Network Configuration** tab.
    -   Find the SAG instance. In the **Actions** column, click **Network Configuration**.
6.  Click the **Method to Synchronize with On-premises Routes** tab.

7.  Select a routing method

    -   **Static Routing**: Default value. It indicates that the SAG device does not automatically learn the private CIDR block of the on-premises network. You must specify the private CIDR block of the on-premises network. Then, the specified CIDR block will be advertised to Cloud Connect Network \(CCN\).
        1.  Click **Add Static Route**.
        2.  In the Add Static Route dialog box, specify the private CIDR block to be advertised to Alibaba Cloud.

            The subnet mask of the CIDR block must be 8 to 32 bits in length, which is based on the private CIDR block that the private network falls within. For example, if the IP address of an on-premises terminal is 192.168.0.100 and the subnet mask is 255.255.0.0, the CIDR block is 192.168.0.0/16.

            **Note:** By default, you can add five private CIDR blocks to an SAG device. You can [submit](https://workorder-intl.console.aliyun.com/?spm=5176.15120809.nav-right.dticket.130266ebEB92in#/ticket/add/?productId=1308) a ticket to increase the quota to at most 50.

        3.  Click **OK**.
    -   **Dynamic Routing**: indicates that the SAG device uses dynamic routing to learn and advertise the private CIDR block of the on-premises network to CCN. In the case of dynamic routing, a dynamic routing protocol, such as BGP and OSPF, is used between the SAG device and the on-premises device \(a switch or Internet-facing router\). For more information about how to configure a dynamic routing protocol for an SAG device, see [Configure BGP routing](/intl.en-US/Configuration Guide/Manage devices/Manage devices/Manage routes/Configure BGP routing.md) and [Configure OSPF routing](/intl.en-US/Configuration Guide/Manage devices/Manage devices/Manage routes/Configure OSPF routing.md).

**Related topics**  


[ModifySmartAccessGateway](/intl.en-US/API Reference/SAG instances/ModifySmartAccessGateway.md)

