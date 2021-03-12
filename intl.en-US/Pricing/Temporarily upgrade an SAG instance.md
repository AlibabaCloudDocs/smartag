# Temporarily upgrade an SAG instance

This topic describes how to temporarily upgrade an SAG instance to meet your business requirements.

You can temporarily upgrade an SAG instance in scenarios such as sales promotions and online operations activities during holidays. You can upgrade the maximum bandwidth value of an SAG instance. After the temporary upgrade ends, the maximum bandwidth is automatically restored to the previous value. Rules of temporary upgrades:

-   The minimum upgrade duration supported by a temporary upgrade is 5 days.You are charged on an hourly basis. After you complete the payment, the new bandwidth value takes effect immediately and your service is not interrupted.
-   After the temporary upgrade ends, the maximum bandwidth of the SAG instance is automatically restored to the previous value. During the restoration process, your workloads are not interrupted. However, transient connections may occur. We recommend that you configure a reconnecting mechanism for your backend applications.
-   The latest restoration time that you can set for a temporary upgrade is the day before the expiration day of the SAG instance.

    For example, if your SAG instance expires at 00:00:00, November 18, 2021, the latest restoration time you can set is 00:00:00, November 17, 2021.


1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com).

2.  In the top navigation bar, select the region where the SAG instance is deployed.

3.  On the Smart Access Gateway page, find the target instance and click ![更多](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/4492404061/p101595.png) in the **Actions** column.

4.  Click **Temporary Upgrade**.

5.  On the Temporary Upgrade page, set the **Peak Bandwidth** and **Restore Time**, select the **SAG Bandwidth Terms of Service** check box, and then complete the payment.


