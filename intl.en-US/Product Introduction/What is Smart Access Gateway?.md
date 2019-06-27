# What is Smart Access Gateway? {#concept_i2w_zgs_j2b .concept}

Smart Access Gateway is an all-in-one solution for connecting local branches to the Alibaba Cloud. With Smart Access Gateway, enterprises can access Alibaba Cloud through the Internet using a fully encrypted connection, allowing businesses to experience a more intelligent, more reliable, and more secure network. Both Smart Access Gateway and Smart Access Gateway \(Software\) are provided. Smart Access Gateway is a physical device used for site-to-site connection by using a leased line, a broadband link, or a 4G link. Smart Access Gateway \(Software\) is used for point-to-site connection.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15401/15616295426804_en-US.png)

## Components {#section_fdf_cls_j2b .section}

-   Smart Access Gateway instance

    A Smart Access Gateway instance is the logic mapping of a Smart Access Gateway device or a Smart Access Gateway \(Software\) client. You can operate the device or the software client by managing the instance in the console.

-   Smart Access Gateway device

    Smart Access Gateway provides devices that are used by local branches to access. After you complete the payment, Alibaba Cloud sends the device to you. You can view the delivery status of the device, and then configure and manage the device through the console. For more information, see [Device introduction](reseller.en-US/Product Introduction/Smart Access Gateway device/Device overview.md#).

    **Note:** Only Smart Access Gateway corresponds to a device.

-   Alibaba Cloud network client

    End users of Smart Access Gateway \(Software\) can achieve mobile access to an intranet through an Alibaba Cloud network client.

-   Cloud Connect Network

    Cloud Connect Network \(CCN\) is another important component of Smart Access Gateway. It is a device access matrix composed of Alibaba Cloud distributed Smart Access Gateways.

    You can add multiple Smart Access Gateway devices to a CCN instance and then attach the CCN instance to a Cloud Enterprise Network \(CEN\) instance to connect the local branches to the Alibaba Cloud.

    The CCN instance and the Smart Access Gateway instances to be added must be in the same area. If the CCN areas and CEN areas are the same, the local branch can directly access Alibaba Cloud without additional configurations required. For more information, see [Cloud Connect Network](../../../../reseller.en-US/User Guide/Cloud Connect Network/Cloud Connect Network.md#).

-   Express Cloud Connect

    Express Cloud Connect is a service for connecting to the cloud that features high reliability, high performance, high speed and low latency. It is based on the capabilities of Smart Access Gateway and built-in routing encapsulation technology, and is integrated with one or more physical connections provided by carriers. For more information, see [../../../../dita-oss-bucket/SP\_72/DNEXPRESSCONNECT19100664/EN-US\_TP\_162666.md\#](../../../../reseller.en-US/Express Cloud Connect (Beta)/Activate Express Cloud Connect.md#).


## Scenarios of Smart Access Gateway {#section_vxm_pwg_4fb .section}

Smart Access Gateway connects organizations \(such as local data centers, branches, and outlets\) to Alibaba Cloud, allowing you to implement highly scalable services and easily establish a hybrid cloud.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15401/156162954221212_en-US.png)

## Scenarios of Smart Access Gateway \(Software\) {#section_ayw_6oc_hrl .section}

Smart Access Gateway \(Software\) enables Alibaba Cloud network clients to access Alibaba Cloud through dial-up. It is suitable for the following scenarios:

-   Mobile working and remote O&M.
-   Test before purchasing a device.

