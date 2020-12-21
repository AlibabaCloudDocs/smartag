# What is Smart Access Gateway?

Smart Access Gateway \(SAG\) is a software-defined wide area network \(SD-WAN\) solution developed by Alibaba Cloud based on cloud-native technologies. SAG provides a more intelligent, reliable, and secure approach for enterprises to migrate their workloads to Alibaba Cloud.

## Product models

You can implement SAG by using one of the following methods:

-   **SAG devices**: client-premises equipment \(CPE\) devices that support site-to-site connections.

    You can deploy SAG devices in on-premises data centers, office branches, and stores to connect their private networks to Alibaba Cloud. SAG provides two device models: SAG-100WM and SAG-1000.

    -   **SAG-100WM devices** can be placed on desks and in extra-low voltage boxes. You can connect broadband and 4G networks to the WAN ports, and wired and Wi-Fi networks to the LAN ports. The maximum bandwidth of encrypted private networks supported by SAG-100WM devices is 50 Mbit/s \(the packet length in the performance test is 512 bytes\). SAG-100WM devices are suitable for quickly connecting small office branches and stores to Alibaba Cloud.
    -   **SAG-1000 devices** can be placed on server racks. You can connect a hybrid network that consists of leased lines, broadband networks, and 4G networks to the WAN ports, and wired networks to the LAN ports. The maximum bandwidth of encrypted private networks supported by SAG-1000 devices is 500 Mbit/s \(the packet length in the performance test is 512 bytes\). SAG-1000 devices are suitable for connecting on-premises data centers and large office branches to Alibaba Cloud.
-   **SAG vCPE**:
    -   **SAG vCPE**: supports site-to-site connections.

        SAG vCPE is an image that can be deployed on a cloud instance. You can deploy the SAG vCPE image on an Alibaba Cloud Edge Node Service \(ENS\) instance or an Amazon Web Services \(AWS\) instance. After you deploy the SAG vCPE image on a server, the server functions as a virtual CPE device. The bandwidth of private networks for encrypted connections can reach 300 Mbit/s and higher \(the packet length in the performance test is 1024 bytes\). This allows you to connect private networks to Alibaba Cloud in a more flexible way.

    -   **SAG APP**: supports point-to-site connections.

        You can install SAG APP in devices such as PCs and mobile phones. Supported operating systems include Windows \(7, XP, and 10\), macOS \(10.11.1 and later\), Android \(5.0 and later\), and iOS \(9.0 and later\).


## Framework

The following figure shows how you can use SAG devices to connect on-premises data centers, office branches, and stores to Alibaba Cloud. You can also use SAG APP to connect PCs and mobile phones to Alibaba Cloud. For other branches, you can connect them to Alibaba Cloud by using SAG vCPE. Cross-region Cloud Enterprise Network \(CEN\) instances allow your private networks, such as virtual private clouds \(VPCs\) that are deployed in different regions, on-premises data centers, office branches, and mobile devices, to communicate with each other.

![Architecture](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2528280061/p143348.png)

|Component|Description|
|---------|-----------|
|SAG devices|CPE devices.|
|SAG vCPE|Virtual CPE devices.|
|SAG APP|An application that can be installed on client devices.|
|CCN|A matrix of Alibaba Cloud distributed gateways.|
|CEN|Alibaba Cloud cross-region networks.|
|VPC|Private networks deployed in Alibaba Cloud regions.|

## Benefits

SAG is an SD-WAN architecture developed based on cloud-native technologies. Compared with legacy SD-WAN architectures, SAG offers the following benefits:

-   Zero touch provisioning \(ZTP\) and centralized management and maintenance

    SAG provides a control plane based on software-defined networking \(SDN\). Similar to managing VPCs and Elastic Compute Service \(ECS\) instances, you can manage SAG devices in the SAG and Cloud Monitor consoles, or by calling the SAG API.

-   Hybrid networks

    SAG provides a data plane based on private WANs on Alibaba Cloud. You can connect private networks to Alibaba Cloud through a hybrid network that consists of leased lines, broadband networks, and 4G networks. This increases the utilization of leased lines and improves network performance.

-   Integration of networks and cloud services

    An architecture that integrates the cloud, networks, and edge:

    -   Automatic protocol negotiation between local and cloud VPNs. No additional configuration is required.
    -   Quick access from private networks to Alibaba Cloud services
    -   End-to-end security policies for both local and cloud workloads

![Architecture](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/1188280061/p143345.png)

