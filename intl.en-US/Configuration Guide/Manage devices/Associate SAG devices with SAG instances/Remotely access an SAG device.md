# Remotely access an SAG device

This topic describes how to specify an IP address used to remotely log on to the web console of a Smart Access Gateway \(SAG\) device. You must specify the IP address in the SAG console. Remote access allows you to log on to the web console over a secure and private connection.

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com).

2.  In the left-side navigation pane, click **Smart Access Gateway**.

3.  In the top menu bar, select the region.

4.  On the Smart Access Gateway page, find the SAG instance.

5.  Use one of the following methods to go to the Device Management tab.

    -   Click the ID of the SAG instance. On the instance details page, click the **Device Management** tab.
    -   Find the SAG instance and choose **![The Hide/Show icon](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/4492404061/p101595.png)** \> **Device Management** in the **Actions** column.
6.  If the SAG instance is associated with an active and a standby SAG device, click the serial number of the SAG device that you want to remotely log on to.

    By default, the **Device Management** displays information about the active SAG device.

7.  Click **Remote Access**.

8.  In the Remote Access from Private Network dialog box, enter the private IP address used to log on to the web console and click **OK**.

9.  **Note:**

-   SAG allows only remote access to the web console over a private connection. Therefore, the terminal where access is initiated must be connected to the SAG device over a private network.
-   If the SAG device needs to communicate with other networks over Cloud Enterprise Network \(CEN\), the private IP address used to log on to the web console must not conflict with those of other networks. Otherwise, you cannot remotely log on to the web console.
-   If the private IP address used to log on to the web console is not specified, you can use the default management IP address. For SAG-1000 devices, the management IP address is the IP address of the management port by default. For SAG-100WM devices, the management IP address is the IP address of the LAN port by default. For more information, see [Configure SAG-100WM in the web console](/intl.en-US/Smart Access Gateway/SAG-100WM usage instructions/Configure SAG-100WM in the web console.md) and [Configure the SAG-1000 device in the web console](/intl.en-US/Smart Access Gateway/SAG-1000 usage instructions/Configure the SAG-1000 device in the web console.md).
10. Open your browser, enter the IP address specified in [Step 8](#step_p2a_dh4_v02) in the address bar, and then press Enter to remotely log on to the web console.


**Related topics**  


[DescribeSagRemoteAccess](/intl.en-US/API Reference/SAG instances/DescribeSagRemoteAccess.md)

[ModifySagRemoteAccess](/intl.en-US/API Reference/SAG instances/ModifySagRemoteAccess.md)

