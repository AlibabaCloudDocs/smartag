# Synchronize the routes between an SAG instance and the corresponding on-premises SAG device {#task_995149 .task}

This topic describes how to synchronize the routes between a Smart Access Gateway \(SAG\) instance and the corresponding on-premises SAG device.

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com).
2.  In the left-side navigation pane, click **Smart Access Gateway**, and then click the target instance ID or click **Configure Network** in the **Actions** column.
3.  On the SAG instance details page, click **Method to Synchronize with On-premises Routes**.
4.  Select the method to synchronize the SAG instance routes with the on-premises device routes. The following two methods are available:

    -   Static Routing: The SAG instance and the on-premises SAG device are interconnected through static routing. After you add the on-premises static routes, they are automatically published to the CEN.
        1.  Click **Add Static Routing**.
        2.  In the Add Static Routing dialog box, set the private CIDR block that is used by the on-premises SAG device to access Alibaba Cloud.

            **Note:** By default, up to five static routing CIDR blocks can be configured. However, you can open a ticket to increase the quota to 20.

        3.  Click **OK**.
    -   Dynamic Routing: The SAG instance and the on-premises SAG device are interconnected through dynamic routing. After you add the on-premises dynamic routes, the BGP or OSPF protocol is run to automatically learn the on-premises routes.
    ![Add static routing](images/51648_en-US.png)


