# Use two SAG devices to implement HA

You can use two Smart Access Gateway \(SAG\) devices to implement high availability \(HA\). You can purchase two SAG devices and associate them with the same SAG instance. This way, when one SAG device is malfunctioning, the other SAG device takes over to ensure that your business is not interrupted. This topic describes how to view the HA configuration in the SAG console.

-   Two SAG devices are purchased.
-   The gateway configurations of the active and standby devices are the same.

SAG devices support two deployment modes: active-standby mode and active-active mode.

-   Active-standby mode: Only the active device is connected to Alibaba Cloud. When the active device is malfunctioning, you must manually switch over to the standby device in the SAG console and connect the standby device to Alibaba Cloud.
-   Active-active mode: Both devices are connected to Alibaba Cloud. The system automatically switches over to the other device when one device is malfunctioning.

By default, SAG-100WM devices run in active-standby mode. You can change the active-standby mode to the active-active mode in the SAG console. For more information, see [Switch the active-standby mode to the active-active mode](/intl.en-US/Configuration Guide/High availability/Switch the active-standby mode to the active-active mode.md).

SAG-1000 devices run only in active-active mode.

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com).

2.  In the top menu bar, select the region.

3.  On the Smart Access Gateway page, click the ID of the SAG instance.

4.  On the instance details page, click the **Configure High Availability** tab.

5.  In the HA Configuration section, you can check the HA status of the SAG devices.

    ![HA 1.1](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/1496325061/p101922.png)


