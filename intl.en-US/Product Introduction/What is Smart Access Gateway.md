# What is Smart Access Gateway {#concept_i2w_zgs_j2b .concept}

Smart Access Gateway \(SmartAG\) is a one-stop solution for connecting local branches to the Alibaba Cloud. With Smart Access Gateway, enterprises can access Alibaba cloud through the Internet in an encrypted way, and get a more intelligent, more reliable, and more secure experience in accessing the Alibaba Cloud.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15401/6804_en-US.png)

## Components {#section_fdf_cls_j2b .section}

-   Smart Access Gateway device

    A Smart Access Gateway is a hardware gateway device that is used for the network access of clients in local sites. You can purchase a gateway device by creating a Smart Access Gateway instance on the Alibaba Cloud console and Alibaba Cloud delivers the device to you according to the address you provided. Additionally, you can manage and view the delivery status through the console.

    The Smart Access Gateway device provides the following functions:

    -   WAN port: Used for accessing the Internet and supports DHCP client and static IP.
    -   LAN port: Used for local device access and supports DHCP server and static IP.
    -   Specification: Smart Access Gateway has three specifications. You can select the specification according to your business needs.
    -   Unified management: You can manage and maintain Smart Access Gateway devices on the console or through APIs.
-   Cloud Connection Network

    Cloud Connection Network \(CCN\) is another important component of the Smart Access Gateway. It is a device access matrix composed of Alibaba Cloud Distributed Access Gateways.

    You can add multiple Smart Access Gateway devices to a CCN instance and then attach the CCN instance to a Cloud Enterprise Network \(CEN\) instance to connect the local branches to the Alibaba Cloud.

    The area of the CCN instance and the Smart Access Gateway instances to add must be the same. A local branch can access to the Alibaba Cloud without any other configurations if the CCN areas and CEN areas are the same. 


## Benefits {#section_htw_gms_j2b .section}

Smart Access Gateway has the following benefits:

-   Intelligent

    Highly automatic and out-of-the-box configuration. Smart Access Gateway automatically adapts the network node changes and automatically switches to the backup node when the master node fails.

-   Reliable

    Nearby access through the Internet is implemented to achieve access from within a city, and multiple local branches can access to the Alibaba Cloud using the Smart Access Gateway devices with master-slave links.

-   Secure

    The local branches and the Alibaba Cloud are connected through an encrypted private network and encryption authentication is implemented during the Internet transmission.

-   Centralized management

    The Alibaba Cloud console provides a central platform for managing and configuring Smart Access Gateway.


