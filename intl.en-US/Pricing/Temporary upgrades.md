# Temporary upgrades

Smart Access Gateway \(SAG\) instances support temporary upgrades to handle traffic spikes.

You can temporarily upgrade the bandwidth of an SAG instance for a specific time period. After the temporary upgrade ends, the SAG instance is restored to the previous bandwidth. Rules of temporary upgrades:

-   The minimum upgrade duration is five days. Fees are incurred on an hourly basis. The upgraded bandwidth takes effect immediately after the payment is completed. Your workloads are not interrupted during the upgrade process.
-   After the temporary upgrade ends, the SAG instance is restored to the previous bandwidth. During the restoration process, your workloads are not interrupted. However, transient disconnections may occur when the bandwidth is being downgraded. We recommend that you ensure a reconnecting mechanism for back-end applications.

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com).

2.  In the top navigation bar, select the target region.

3.  On the Smart Access Gateway page, find the target instance and click ![More](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/7568219951/p126899.png) in the **Actions** column.

4.  Click **Temporary Upgrade**.

5.  On the Temporary Upgrade page, set the **Peak bandwidth** and **Restore Time**, select the **SAG Bandwidth Terms of Service** check box, and then settle the payment.


