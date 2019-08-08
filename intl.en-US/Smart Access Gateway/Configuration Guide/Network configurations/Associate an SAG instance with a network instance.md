# Associate an SAG instance with a network instance {#task_995151 .task}

This topic describes how to associate a Smart Access Gateway \(SAG\) instance with a network instance. You must associate an SAG instance with a network instance if you want to connect the SAG to Alibaba Cloud. You can connect an SAG to Alibaba Cloud through a leased line, the Internet, or the active and standby links.

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com).
2.  In the left-side navigation pane, click **Smart Access Gateway**, and then click the target instance ID or click **Configure Network** in the **Actions** column.
3.  On the SAG instance details page, click **Network Instance Details**.
4.  Click **Add Network Instance**.
5.  In the Add Network Instance dialog box, configure the network instance to be associated with the SAG instance. 

    The parameters are described as follows:

    -   **Network Type**: the type of the network associated with the SAG instance.

        To connect the SAG to Alibaba Cloud through a leased line, associate the SAG with the VBR. To connect the SAG to Alibaba Cloud through the Internet, associate the SAG with a CCN instance.

        The CCN is a device access matrix that consists of Alibaba Cloud distributed access gateways. After an SAG instance is associated with a CCN instance, the SAG can communicate with other gateways associated with the CCN instance.

        **Note:** The CCN instance and the SAG instance must be in the same area.

    -   **Network Instance**: the network instance to be associated with.
    ![](images/50933_en-US.png)

6.  Click **OK**.

