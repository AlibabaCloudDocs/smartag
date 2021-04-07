# Introduction to CCN

Cloud Connect Network \(CCN\) is a matrix consisting of Alibaba Cloud distributed access gateways. It is an important component of Smart Access Gateway \(SAG\). After you associate an SAG instance with a CCN instance, the SAG instance connects associated private networks to Alibaba Cloud through the CCN instance.

You must select an area when you create a CCN instance. For more information about areas that support CCN, see [Supported areas](#table_vse_lbl_mb0).

**Note:** An SAG instance can be associated with a CCN instance that belongs to the same area as that of the SAG instance. You cannot associate an SAG instance with a CCN instance that belongs to a different area.

You can attach a CCN instance to a Cloud Enterprise Network \(CEN\) instance to connect on-premises workloads to Alibaba Cloud. For more information, see [What is CEN?]().

After you attach a CCN instance to a CEN instance, private networks associated with the CCN instance can communicate with cloud resources attached to the CEN instance.

-   Private networks associated with the CCN instance can directly communicate with cloud resources attached to the CEN instance in the same area. No cross-area bandwidth is required.

    For example, if you want to use SAG to connect the network of an office branch in Hangzhou to a virtual private cloud \(VPC\) in the China \(Shanghai\) region, attach the CCN instance associated with the SAG instance to the CEN instance to which the VPC is attached.

-   To enable communication across areas, you must purchase a CEN bandwidth plan and set cross-region bandwidth after you attach the CCN instance to the CEN instance.

    For more information, see [CEN tutorial]().


Areas of CCN and areas of CEN are defined in different ways. A CEN area is a collection of Alibaba Cloud regions. Each area of CEN may contain one or more Alibaba Cloud regions. The following table lists the areas of CCN and CEN.

|CCN area|CEN area|Region in the CCN area|
|:-------|:-------|:---------------------|
|Mainland China|Mainland China|China \(Qingdao\)

China \(Beijing\)

China \(Zhangjiakou\)

China \(Hohhot\)

China \(Ulanqab\)

China \(Shenzhen\)

China \(Heyuan\)

China \(Hangzhou\)

China \(Shanghai\)

China \(Chengdu\) |
|China \(Hong Kong\)|Asia Pacific|China \(Hong Kong\)|
|Singapore \(Singapore\)|Singapore \(Singapore\)|
|Malaysia \(Kuala Lumpur\)|Malaysia \(Kuala Lumpur\)|
|Indonesia \(Jakarta\)|Indonesia \(Jakarta\)|
|Japan \(Tokyo\)|Japan \(Tokyo\)|
|Germany \(Frankfurt\)|Europe|Germany \(Frankfurt\)|
|Australia \(Sydney\)|Australia|Australia \(Sydney\)|

