# Device-level high availability configurations {#task_mj4_by5_q2b .task}

If you choose the active/standby mode when you purchase devices, the device can quickly switch to the standby device when the active device fails.

-   Make sure that you select the **Active/Standby** mode when purchasing the device.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17036/15574536178559_en-US.png)

-   Make sure the device configurations are the same for both devices.

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com).
2.  In the left-side navigation pane, click **Smart Access Gateway Hardware** and then click the ID of the target gateway instance.
3.  In the **High-Availability Configurations** area, click **Switch** to switch to the other device. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17036/15574536178561_en-US.png)

    **Note:** For SAG-100WM devices, after you switch to the standby device in the console, you must connect the WAN port of the standby SAG device to the Internet.

    SAG-100WM devices support manual switching between active and standby devices. SAG-1000 devices support automatic switching between active and standby devices and do not support manual switching between them.


