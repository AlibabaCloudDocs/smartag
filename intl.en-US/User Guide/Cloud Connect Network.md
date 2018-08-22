# Cloud Connect Network {#concept_us2_hjs_j2b .concept}

Cloud Connect Network \(CCN\), a component of Smart Access Gateway, is a device access matrix composed of Alibaba Cloud distributed access gateways. You can add multiple Smart Access Gateway devices to a CCN instance and then bind the CCN instance to a Cloud Enterprise Network \(CEN\) instance to connect the local branches to the Alibaba Cloud.

## CCN areas {#section_sb4_vqf_l2b .section}

You must specify an area when buying a Smart Access Gateway device or creating a CCN instance. Each Smart Access Gateway area corresponds to a country, while a CEN area contains one or more Alibaba Cloud regions. The relationships between CCN areas and CEN areas are shown in the following table.

A local branch can access the Alibaba Cloud without any other configurations if the CCN area and CEN area are the same. For example, to connect a local branch in Hangzhou to a VPC in Shanghai, you just need to bind the CCN instance to which the Smart Access Gateway is bound to the CEN instance where the VPC is located.

**Note:** 

-   Currently, Smart Access Gateway is available only in Mainland China.
-   Cross-area connection is not supported.

|CCN area|CEN area|Regions in CEN area|
|:-------|:-------|:------------------|
|Mainland China|Mainland China| China \(Qingdao\) 

 China \(Beijing\)  

 China \(Zhangjiakou\)

 China \(Shenzhen\)

 China \(Hangzhou\)

 China \(Shanghai\)

 China \(Hohhot\)

 |
|Hong Kong|Asia Pacific|Hong Kong|
|Singapore|Singapore|
|Malaysia \(Kuala Lumpur\)|Malaysia \(Kuala Lumpur\)|
|Japan \(Tokyo\)|Japan \(Tokyo\)|
|India \(Mumbai\)|India \(Mumbai\)|
|North America|North America|US \(Silicon Valley\)|
|US \(Virginia\)|
|Europe|Europe|Germany \(Frankfurt\)|
|Australia|Australia|Sydney|

## Create a CCN instance {#section_blt_bxt_j2b .section}

To create a CCN instance, follow these steps:

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com/).
2.  In the left-side navigation pane, click **CCN**.
3.  Select the target area and click **Create CCN Instance**.
4.  Enter the name and description of the CCN instance and click **OK**.

## Bind a CCN instance to a CEN instance {#section_ygr_nxt_j2b .section}

After you bind a CCN instance to a CEN instance, local branches connected to the CCN instance can access Alibaba Cloud without any other configurations if the CCN areas and CEN areas are the same.

To bind a CCN instance to a CEN instance, follow these steps:

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com/).
2.  In the left-side navigation pane, click **CCN**.
3.  Select the area of the CCN instance, and click **Bind CEN Instance** in the **Actions** column of the target CCN instance.
4.  Select the CEN instance where the VPC is located and click **OK**.

