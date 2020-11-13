# Switch the active-standby mode to the active-active mode

This topic describes how to switch the active-standby mode to the active-active mode for SAG-100WM devices.

-   Two SAG-100WM devices are purchased.
-   The SAG-100WM devices run in active-standby mode.

SAG devices support two deployment modes: active-standby mode and active-active mode.

-   Active-standby mode: Only the active device is connected to Alibaba Cloud. When the active device is malfunctioning, you must manually switch over to the standby device in the SAG console and connect the standby device to Alibaba Cloud.
-   Active-active mode: Both devices are connected to Alibaba Cloud. The system automatically switches over to the other device when one device is malfunctioning.

SAG-100WM devices run in active-standby mode by default. To switch to the active-active mode, perform the following steps: When you switch the active-standby mode to the active-active mode for SAG-100WM devices, note that:

-   The software versions of both devices must be 1.8.0 or later.
-   The software versions of both devices must be the same.

1.  Perform the following steps to view the software version of the active SAG device:

    1.  Log on to the [SAG console](https://smartag.console.aliyun.com).

    2.  In the top menu bar, select the region.

    3.  On the Smart Access Gateway page, click the ID of the SAG instance.

    4.  On the instance details page, click the **Device Management** tab. In the **Device Information** section, you can view the software version of the active SAG device.

        ![View the software version](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/1336325061/p129792.png)

    5.  If the software version of the active device is earlier than 1.8.0, upgrade the software version. For more information, see [Upgrade an SAG device to a later version](/intl.en-US/Configuration Guide/Manage devices/Associate SAG devices with SAG instances/Upgrade an SAG device to a later version.md).

        **Note:**

        -   The upgrade process takes about 10 minutes.
        -   The upgrade may cause network disconnections. We recommend that you upgrade your instance during off-peak hours.
2.  Perform the following steps to switch over to the standby device and view the software version.

    1.  On the instance details page, click the **Configure High Availability** tab.

    2.  In the **HA Configuration** section, click **Switch** in the **Standby Device SN** section to connect the standby device to Alibaba Cloud.

    3.  Return to the **Device Management** tab and click the serial number of the device.

    4.  In the **Device Information** section, you can view the software version.

    5.  If the software version is earlier than 1.8.0, upgrade the software version. For more information, see [Upgrade an SAG device to a later version](/intl.en-US/Configuration Guide/Manage devices/Associate SAG devices with SAG instances/Upgrade an SAG device to a later version.md).

        **Note:**

        -   The upgrade process takes about 10 minutes.
        -   The upgrade may cause network disconnections. We recommend that you upgrade your instance during off-peak hours.
3.  Switch to the active-active mode.

    1.  On the instance details page, click the **Configure High Availability** tab.

    2.  In the **HA Configuration** section, click **Switch** in the **Standby Device SN** section to disconnect the standby device from Alibaba Cloud and connect the active device to Alibaba Cloud.

        In active-active mode, the SAG device that is first connected to Alibaba Cloud functions as the active device. The other device that is later connected to Alibaba Cloud functions as the standby device. After you click Switch, the standby device is disconnected from Alibaba Cloud and the active device is connected to Alibaba Cloud.

    3.  Click **Switch to Hot Standby** in the **SAG Device HA** section to switch the mode. In the dialog box that appears, click **OK**. After you complete the preceding steps, both SAG devices run in active-active mode. In this mode, both devices are connected to Alibaba Cloud.

        **Note:** If you disassociate or reassociate the SAG devices that run in active-active mode, the SAG devices will switch back to the active-standby mode.


