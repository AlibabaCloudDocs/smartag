# What is Smart Access Gateway? {#concept_i2w_zgs_j2b .concept}

Smart Access Gateway \(SmartAG\) is a one-stop solution for connecting local branches to the Alibaba Cloud. With Smart Access Gateway, enterprises can securely access Alibaba Cloud over the Internet and enjoy a more intelligent and reliable connection.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15401/15349535136804_en-US.png)

## Components {#section_fdf_cls_j2b .section}

-   Smart Access Gateway device

    A hardware gateway device is provided with each Smart Access Gateway instance to allow a local branch to securely access Alibaba Cloud. You can purchase a gateway device by creating a Smart Access Gateway instance on the Alibaba Cloud console. Alibaba Cloud delivers the device to the address you provided when you purchase the instance Additionally, you can view the delivery status and configure the Smart Access Gateway device on the console. For more information, see [Configure a Smart Access Gateway device](../../../../intl.en-US/User Guide/Manage a Smart Access Gateway device/Configure a Smart Access Gateway device.md#). 

    Smart Access Gateway devices have the following features:

    -   WAN port: Used for accessing the Internet and supports DHCP client, static IP, PPPoE and SNAT forwarding.
    -   LAN port: Used for accessing local terminal devices and supports DHCP server and static IP.
    -   Specification: Smart Access Gateway has three possible specifications. You can select the specification according to your business needs.
    -   Unified management: You can manage and maintain multiple Smart Access Gateway devices at once on the console or through APIs.
-   Cloud Connect Network

    Cloud Connect Network \(CCN\) is a device access matrix composed of Alibaba Cloud distributed access gateways.

    You can add multiple Smart Access Gateway devices to a CCN instance and then attach the CCN instance to a Cloud Enterprise Network \(CEN\) instance to connect the local branches to the Alibaba Cloud.

    The CCN instance and the Smart Access Gateway instances to be attached to it must be in the same area. If the local branches and the resources are in the same area, the branches can access cloud resources in Alibaba Cloud without additional configurations. For more information, see [Cloud Connect Network](../../../../intl.en-US/User Guide/Cloud Connect Network.md#). 


## Benefits {#section_htw_gms_j2b .section}

Smart Access Gateway has the following benefits:

-   Intelligent

    Smart Access Gateway automatically and quickly adapts to network topology changes, while the gateway device is completely plug-and-play.

-   Reliable

    Access is provided from a nearby cities through the Internet. Additionally, multiple local branches can access Alibaba Cloud using the Smart Access Gateway devices with master-slave links.

-   Secure

    The local branches and the Alibaba Cloud are connected through an encrypted private network and encryption authentication is implemented during the Internet transmission.

-   Centralized management

    The Alibaba Cloud console is the unified platform for global administration.


