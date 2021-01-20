---
keyword: traffic distribution by application
---

# View traffic monitoring data of applications

This topic describes how to view the traffic monitoring data of applications.

The deep packet inspection \(DPI\)-based monitoring feature of Smart Access Gateway \(SAG\) is enabled. For more information, see [Manage DPI](/intl.en-US/Configuration Guide/DPI/Manage DPI.md).

## View traffic distribution of applications

1.  Log on to the [SAG console](https://smartag.console.aliyun.com).

2.  In the top navigation bar, select the region where the SAG instance is deployed.

3.  On the **Smart Access Gateway** page, click the ID of the SAG instance.

4.  On the instance details page, click the **Monitoring** tab.

5.  On the **Monitoring** tab, click **DPI Statistics on Applications**.

6.  On the **DPI Statistics on Applications** tab, you can view the following information:

    -   **DPI Statistics by Application Group**: displays the traffic percentage of each application group for the current SAG instance by default.
    -   **DPI Statistics by Application**: displays the traffic percentage of each application by default.
    -   **DPI Statistics by Request Source**: displays the traffic percentage of each application by request source by default.

## View traffic distribution of specific applications

On the **DPI Statistics on Applications** tab, you can set the following conditions to filter traffic monitoring data. For example, you can view the traffic percentages of applications during a specified time period or traffic percentages of specified applications.

-   **topN**: queries the traffic information about the top 10, top 50, top 100, or top 500 applications, application groups, or application request sources that have the highest percentages of traffic.
-   **Time**: Click **Select** in the upper-right corner of the tab to select a time period for querying traffic distribution of applications.

    You can set the time period in the following formats:

    -   **Relative**: queries traffic distribution of applications from the current time to a specified time in the past.

        For example, you can select **5 Minutes** and the current time is 14:33:38 \(UTC+8\) on November 26, 2020. In this case, the traffic distribution from 14:28:38 \(UTC+8\) on November 26, 2020 to 14:33:38 \(UTC+8\) on November 26, 2020 is queried.

    -   **Rounded to Hour**: queries traffic distribution of applications from the beginning of the current hour to a specified time in the past.

        For example, you can select **1 Hour** and the current time is 14:33:38 \(UTC+8\) on November 26, 2020. In this case, the traffic distribution from 13:00:00 \(UTC+8\) on November 26, 2020 to 14:00:00 \(UTC+8\) on November 26, 2020 is queried.

    -   **Custom**: queries traffic distribution of applications during a custom time period.
-   **Specified Applications**: queries traffic distribution of applications in specified application groups or of specified applications.

    For example, the following figure shows the traffic percentage of each application for a specified SAG instance. The information is displayed on the **DPI Statistics by Application Group** tab. If you click the green area in the ring diagram, you are redirected to the **DPI Statistics on Applications** tab. This tab displays the traffic distribution of each application in the **General internet** group.

    ![Click an application group](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7119229061/p185344.png)


