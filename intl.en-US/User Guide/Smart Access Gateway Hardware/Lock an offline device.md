# Lock an offline device {#task_yqq_3kb_mfb .task}

When a Smart Access Gateway device \(SAG device\) is offline, you can lock the SAG device and then the device cannot be used any more.

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com/).
2.  In the left-side navigation pane, click **Smart Access Gateway Hardware** and then click the ID of the target gateway instance.
3.  On the Instance Details page, click **Enable** next to the **Offline Lock** configuration . 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/23717/155745358945427_en-US.png)

4.  Enter a threshold \(in seconds\) for the locked status to take effect and click **OK**. 

    For example, if 3600 is entered, the SAG device becomes locked after 60 minutes.

    When you need to enable the SAG device, click **Disable** next to the **Offline Lock** configuration. After you click **Disable**, the button changes to **Enable**, indicating that you can use the SAG device as normal.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/23717/155745358914244_en-US.png)


