# Configure PrivateZone

Alibaba Cloud DNS PrivateZone \(PrivateZone\) is a VPC-based resolution and management service for private domain names. You can use Smart Access Gateway \(SAG\) to access PrivateZone through Cloud Enterprise Network \(CEN\). This topic describes how to configure PrivateZone in the CEN console.

-   PrivateZone is activated. For more information, see [Subscribe Service](https://www.alibabacloud.com/help/zh/doc-detail/64627.htm?spm=a2c63.p38356.b99.13.29d1631aAid33A).
-   A CEN instance is created and a virtual private cloud \(VPC\) is attached to the CEN instance. Make sure that the VPC and PrivateZone are deployed in the same region. For more information, see [Create a CEN instance]().
-   The Cloud Connect Network \(CCN\) instance connected to your on-premises network is attached to the CEN instance. For more information, see [Attach networks]().

PrivateZone is a VPC-based resolution and management service for private domain names. You can use PrivateZone to resolve private domain names to IP addresses in one or multiple specific VPCs.

PrivateZone allows you to access Elastic Compute Service \(ECS\) instances, Server Load Balancer \(SLB\) instances, Object Storage Service \(OSS\) buckets, and other Alibaba Cloud resources by using private domain names. The private domain names are invalid outside VPCs. You can connect your on-premise network to a VPC through SAG and CEN. You can configure PrivateZone in the CEN console to allow the on-premises network and VPC to access each other through private domain names.

![Architecture](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6318325061/p172779.png)

1.  Log on to the [CEN console](https://cen.console.aliyun.com/cen/list).

2.  Click the ID of the CEN instance.

3.  Click the Private Zone tab, and then click **Authorization**.

    **Note:** You need to confirm the authorization only when it is your first time configuring PrivateZone.

4.  On the Cloud Resource Access Authorization page, click **Confirm Authorization Policy** to allow the on-premises network to access PrivateZone. Make sure that the on-premises network is associated with the CCN instance that is attached to the CEN instance.

5.  Click **Set Private Zone**. In the Set Private Zone pane, set the following parameters:

    ![Configure PrivateZone](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8787705061/p172717.png)

    1.  **Host Region**: Select the region of the VPC for which PrivateZone is enabled.

    2.  **Host VPC**: Select the VPC for which PrivateZone is enabled.

        PrivateZone can be accessed only over the specified VPC.

    3.  **Access Region**: Select the region where access is initiated.

        **Note:**

        -   Set Access Region to the CCN instance that is deployed in the same region as that of PrivateZone. Make sure that the specified CCN instance is attached to the CEN instance.
        -   If the CCN instance, CEN instance, and VPC are under different Alibaba Cloud accounts, you must acquire permissions from the peer accounts. For more information, see [Authorize CCN instances to use the PrivateZone service]().
    4.  Click **OK**.


