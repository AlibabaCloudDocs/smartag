---
keyword: [enable DPI, disable DPI, enable DPI-based monitoring, disable DPI-based monitoring]
---

# Manage DPI

This topic describes how to enable or disable the deep packet inspection \(DPI\) feature and the DPI-based monitoring feature.

The model of the Smart Access Gateway \(SAG\) device associated with the SAG instance is SAG-1000 or SAG-100WM. For more information, see [View basic information](/intl.en-US/Configuration Guide/Manage devices/Associate SAG devices with SAG instances/View basic information.md).

## Enable DPI

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com).

2.  In the top navigation bar, select the region where the SAG instance is deployed.

3.  On the Smart Access Gateway page, click the ID of the SAG instance.

4.  On the **Basic Info** tab, find the **Advanced Features** section and turn on the **DPI** switch.

5.  In the **Enable DPI** message, click **OK**.


## Disable DPI

Before you disable DPI, make sure that you have met the following requirements:

-   The SAG instance is not associated with application-aware QoS policies. If the SAG instance is associated with an application-aware QoS policy, disassociate the SAG instance from the QoS policy first. For more information, see [Associate with or disassociate from an SAG instance](/intl.en-US/Configuration Guide/QoS policies/Apply a QoS policy to an SAG instance.md).
-   The SAG instance is not associated with application-aware ACLs. If the SAG instance is associated with an application-aware ACL, disassociate the SAG instance from the ACL first. For more information, see [Manage SAG instances associated with ACLs]().

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com).

2.  In the top navigation bar, select the region where the SAG instance is deployed.

3.  On the Smart Access Gateway page, click the ID of the SAG instance.

4.  On the **Basic Info** tab, find the **Advanced Features** section and turn off the **DPI** switch.


## Enable DPI-based monitoring

SAG analyzes the distribution of application traffic based on the information collected by DPI. You must enable DPI-based monitoring for the SAG instance before you can view the traffic monitoring data.

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com).

2.  In the top navigation bar, select the region where the SAG instance is deployed.

3.  On the Smart Access Gateway page, click the ID of the SAG instance.

4.  On the instance details page, click the **Monitoring** tab and then click **DPI Statistics on Applications**.

    On the **DPI Statistics on Applications** tab, click **Activate Now** to enable the DPI feature and Log Service. For more information about Log Service, see [Quick Start](/intl.en-US/Quick Start/Quick Start.md).

    After these features are enabled, the traffic monitoring data of the SAG instance is displayed. For more information, see [View traffic monitoring data of applications]().


## Disable DPI-based monitoring

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com).

2.  In the top navigation bar, select the region.

3.  On the Smart Access Gateway page, click the ID of the SAG instance.

4.  On the instance details page, click the **Monitoring** tab and then click **DPI Statistics on Applications**.

5.  In the upper-right corner of the **DPI Statistics on Applications** tab, click **Disable DPI-based Monitoring**

6.  In the message that appears, click **OK**.


