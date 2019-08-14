# Cloud Connect Network {#concept_gwh_wlb_mfb .concept}

Cloud Connect Network \(CCN\) is another important component of Smart Access Gateway. It is a device access matrix composed of Alibaba Cloud distributed access gateways. You can add multiple Smart Access Gateway \(SAG\) devices to a CCN instance and then attach the CCN instance to a Cloud Enterprise Network \(CEN\) instance to connect the local branches to the Alibaba Cloud.

You must specify an area when buying an SAG device or creating a CCN instance. Each SAG area corresponds to a country, while a CEN area contains one or more Alibaba Cloud regions. The relationships between CCN areas and CEN areas are shown in the following table.

A CCN instance and a CEN instance can directly communicate with each other and no cross-area bandwidth is required if the CCN instance and the CEN instance are in the same area. For example, to connect a local branch in Hangzhou to a VPC in Shanghai, you just need to bind the CCN instance to which the Smart Access Gateway is bound to the CEN instance where the VPC is located.

**Note:** 

-   Currently, Smart Access Gateway is available only in Mainland China.
-   Cross-area connection through Smart Access Gateway is not supported.

|CCN area|CEN area|Regions in the CEN area|
|:-------|:-------|:----------------------|
|Mainland China|Mainland China| China \(Qingdao\)

 China \(Beijing\)

 China \(Zhangjiakou\)

 China \(Shenzhen\)

 China \(Hangzhou\)

 China \(Shanghai\)

 China \(Hohhot\)

 |
|China \(Hong Kong\)|Asia Pacific|China \(Hong Kong\)|
|Singapore|Singapore|
|Malaysia \(Kuala Lumpur\)|Malaysia \(Kuala Lumpur\)|
|Japan \(Tokyo\)|Japan \(Tokyo\)|
|India \(Mumbai\)|India \(Mumbai\)|
|North America|North America|US \(Silicon Valley\)|
|US \(Virginia\)|
|Europe|Europe|Germany \(Frankfurt\)|
|Australia|Australia|Sydney|

