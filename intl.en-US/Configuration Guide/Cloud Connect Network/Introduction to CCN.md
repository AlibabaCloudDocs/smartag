# Introduction to CCN

Cloud Connect Network \(CCN\) is a matrix consisting of Alibaba Cloud distributed access gateways. It is an important component of Smart Access Gateway \(SAG\). After you associate an SAG instance with a CCN instance, the SAG instance connects associated private networks to Alibaba Cloud through the CCN instance.

When you purchase SAG or CCN, you must specify the area. For more information, see the following table that lists **CCN areas**.

**Note:** An SAG instance can be associated with CCN instances that are in the same area as the SAG instance. You cannot associate SAG instances with CCN instances across areas.

You can attach a CCN instance to a Cloud Enterprise Network \(CEN\) instance to connect on-premises workloads to Alibaba Cloud. For more information, see [What is Cloud Enterprise Network?]().

You can attach a CCN instance to a CEN instance in the same area or a different area. After you attach the CCN instance to the CEN instance, private networks associated with the CCN instance can communicate with cloud resources associated with the CEN instance.

-   Private networks associated with the CCN instance can directly communicate with cloud resources associated with the CEN instance in the same area. No cross-region bandwidth is required. For example, if you want to use SAG to connect an office branch in Hangzhou to a Virtual Private Cloud \(VPC\) network in the China \(Shanghai\) region, attach both the CCN instance that is associated with the SAG instance of the office branch and the VPC network in China \(Shanghai\) to the same CEN instance.
-   To enable communication across areas, you must attach the CCN instance to the CEN instance first, and then use a CEN bandwidth plan to set up cross-region bandwidths. For more information, see [Purchase a CEN bandwidth plan]() and [Set a cross-region connection bandwidth]().

Areas of CCN and areas of CEN are defined in different ways. A CEN area is a collection of Alibaba Cloud regions. Each area of CEN may contain one or more Alibaba Cloud regions. The following table lists the areas of CCN and CEN.

|CCN area|CEN area|Region in the CEN area|
|:-------|:-------|:---------------------|
|Mainland China|Mainland China|China \(Qingdao\)

China \(Beijing\)

China \(Zhangjiakou-Beijing Winter Olympics\)

China \(Hohhot\)

China \(Ulanqab\)

China \(Shenzhen\)

China \(Heyuan\)

China \(Hangzhou\)

China \(Shanghai\)

China \(Chengdu\) |
|China \(Hong Kong\)|Asia Pacific|China \(Hong Kong\)|
|Singapore|Singapore|
|Malaysia \(Kuala Lumpur\)|Malaysia \(Kuala Lumpur\)|
|Indonesia \(Jakarta\)|Indonesia \(Jakarta\)|
|Japan \(Tokyo\)|Japan \(Tokyo\)|
|Germany \(Frankfurt\)|Europe|Germany \(Frankfurt\)|
|Australia \(Sydney\)|Australia|Australia \(Sydney\)|

