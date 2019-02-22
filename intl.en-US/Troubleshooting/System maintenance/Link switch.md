# Link switch {#task_lwv_qft_mfb .task}

Active/standby double links are enabled on SAG-100WM devices by default. The WAN port link operates as the active link and the 4G link operates as the standby link. When the active link fails, you can quickly switch to the standby link.

On the Instance Details page, ensure that you have enabled link-level high availability and set the high-availability mode to **Channel**.

Currently, active/standby dual links are only supported by SAG-100WM devices.

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com). 
2.  On the SAG page, find the target instance and click the ID of the instance. 
3.  In the **High-Availability Configurations** area, click the **Switch** option next to the **Backup Channel**. 

    ![](images/14030_en-US.png)


