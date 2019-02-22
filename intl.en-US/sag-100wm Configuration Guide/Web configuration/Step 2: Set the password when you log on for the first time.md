# Step 2: Set the password when you log on for the first time {#task_dq3_2f2_qfb .task}

After you power on the Smart Access Gateway device for the first time, you need to go to the Web console and set the logon password before you can continue using the device.

Before logging on to the web configuration page, make sure that:

-   The Smart Access Gateway is powered on.
-   The LAN port of the Smart Access Gateway is connected to the local client.
-   The local client has DNS enabled to automatically obtain an IP address.

1.  Enter `192.168.0.1` in the browser. 

    `192.168.0.1` is the default web configuration address of the gateway device.

    **Note:** 

    -   If the LAN port uses a static IP address that you configured, log on by using that IP address.
    -   If the LAN port uses a dynamic IP address \(that is, you have configured CIDR blocks on the console, the WAN port has DHCP enabled, and the cloud status light turns on when the network cable is connected\), log on by using the first IP address in the first CIDR block configured on the console.

        For example, if the first CIDR block specified by you is 192.168.0.0/16, the web configuration address is 192.168.0.1.

    -   If neither the LAN port nor the console is configured, the default address is `192.168.0.1`.
2.  Set the logon password. 
3.  Click **OK**. Enter the new password. Keep your logon password securely. If the password is lost or forgotten, you can press and hold the reset button on your device for two seconds and then log on to the Web console to reset the password.

    **Note:** 

    -   After you press and hold the reset button for five seconds when the gateway is powered on, the cloud status light flickers quickly, which means all configurations are cleared and that the device is restarted.
    -   To restore the device to its default configurations, first power off the device, and press and hold the reset key while powering the device back on until the cloud status light is on, which means the device is restoring.

        After about two to three minutes, the cloud status light goes off, which means the default configurations are restored.


