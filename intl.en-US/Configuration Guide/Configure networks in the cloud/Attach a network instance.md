# Attach a network instance

Smart Access Gateway \(SAG\) allows you to connect a private network to Alibaba Cloud through a leased line, Internet connection, or both. If you choose to use a leased line, you must associate the SAG instance with a virtual border router \(VBR\). If you choose to use an Internet connection, you must associate the SAG instance with a Cloud Connect Network \(CCN\) instance.

-   Before you connect your private network to Alibaba Cloud over the Internet, make sure that a CCN instance is created. For more information, see [Create a CCN instance](/intl.en-US/Configuration Guide/Cloud Connect Network/Create a CCN instance.md).
-   If you choose to use a leased line, make sure that the leased line is deployed in your private network and a VBR is created. For more information, see [What is Express Connect?](/intl.en-US/Product Introduction/What is Express Connect?.md).

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com).

2.  In the top menu bar, select the region.

3.  On the Smart Access Gateway page, use one of the following methods to open the Network Configuration tab.

    -   Click the ID of the SAG instance. On the instance details page, click the **Network Configuration** tab.
    -   Find the SAG instance and click **Network Configuration** in the **Actions** column.
4.  In the left-side navigation tree, click Network Instance Details.

5.  In the **Associated Instances Under Current Account** section, click **Attach Network**.

    ![Attach a network](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/0935325061/p132246.png)

6.  In the Attach Network dialog box, set the following parameters.

    ![Attach a network under the current account](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/0935325061/p132247.png)

    |Parameter|Description|
    |---------|-----------|
    |**Network Type**|Select the type of the network instance that you want to attach.     -   **Cloud Connect Network**: Connect the private network to Alibaba Cloud over the Internet.
    -   **Virtual Border Router**: Connect the private network to Alibaba Cloud through a leased line. |
    |**Region**|If you choose to attach a VBR, you must select the region where the VBR is deployed.|
    |**Network Instance**|Select the network instance.|

7.  Click **OK**.


