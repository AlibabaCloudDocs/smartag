# Configure AnyTunnel

Smart Access Gateway \(SAG\) can access cloud services deployed in Virtual Private Cloud \(VPC\) networks through Cloud Enterprise Network \(CEN\). This topic describes how to configure AnyTunnel in the CEN console.

-   A CEN instance is created and VPC networks connected to the cloud services that you want to access are attached to the CEN instance. For more information, see [Create a CEN instance]().
-   The Cloud Connect Network \(CCN\) instance connected to your private network is associated with the CEN instance. For more information, see [Attach networks]().

Cloud services refer to Alibaba Cloud services, such as Object Storage Service \(OSS\), Log Service, and Data Transmission Service \(DTS\), that use the CIDR block 100.64.0.0/10 to provide services. To enable on-premises clients to access cloud services deployed in VPC networks, you can connect your private network to Alibaba Cloud through SAG. Then, attach the CCN instance associated with the SAG instance to a CEN instance.

![Configure AnyTunnel](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/2553631061/p165751.png)

1.  Log on to the [CEN console](https://cen.console.aliyun.com/cen/list).

2.  On the Instances page, click the ID of the CEN instance that you want to manage.

3.  On the instance details page, click the AnyTunnel tab and then click **SetAnyTunnelService**.

    ![AnyTunnel](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/0360201061/p96967.png)

4.  In the SetAnyTunnelService pane, set the following parameters:

    -   **Service IP address**: Enter an IP address or CIDR block used by the cloud service. This IP address or CIDR block must fall into 100.64.0.0/10. For example, you can enter 100.118.28.52/32.
    -   **Host Region**: Select the region where the cloud service is deployed.

        **Note:** Make sure that at least one VPC network in the selected region is attached to the CEN instance.

    -   **Host VPC**: From the drop-down list, select the VPC network that is attached to the CEN instance.

        After you select a VPC network, networks attached to the CCN instance can access the cloud service through the VPC network.

    -   **Access Region**: Select the CCN instance that is associated with the CEN instance.

        **Note:** Make sure that the selected CCN instance is associated with the CEN instance.

    -   **Description**: Enter a description for the cloud service. This parameter is optional.

        The description is optional. If you enter one, it must be 2 to 256 characters in length, and can contain digits, hyphens \(-\), underscore \(\_\), and periods \(.\). It must start with a letter or a Chinese character and cannot start with `http://` or `https://`.

    ![AnyTunnel](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/4560201061/p166053.png)

5.  Click **OK**.

    **Note:** Typically, a cloud service uses multiple IP addresses. Repeat the preceding steps to add routes to all the IP addresses of the cloud service.


**Related topics**  


[t1949768.md\#]()

