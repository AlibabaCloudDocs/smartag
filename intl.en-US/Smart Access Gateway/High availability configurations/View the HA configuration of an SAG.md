# View the HA configuration of an SAG {#task_1062418 .task}

This topic describe how to view the high availability \(HA\) configuration of a Smart Access Gateway \(SAG\).

Before you can view the HA configuration of an SAG, the following conditions must be met:

-   The standby usage mode is selected when you purchase the SAG.
-   The active SAG and standby SAG have the same configurations.

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com).
2.  In the left-side navigation pane, clickSmart Access Gateway, and then click the instance ID of the SAG for which you want to perform an active/standby switchover.
3.  In the left-side navigation pane of the SAG details page, click **HA Configuration**.
4.  On the HA Configuration page, view the SN of the active SAG and standby SAG. The active/standby switchover of SAG-100WM differs from that of SAG-1000 in the following aspects:
    -   If you switch an SAG-100WM device to its standby device in the console, you must also connect the physical WAN port of the standby device to the Internet.
    -   SAG-100WM devices support manual active/standby switchover, while SAG-1000 devices support automatic active/standby switchover.

