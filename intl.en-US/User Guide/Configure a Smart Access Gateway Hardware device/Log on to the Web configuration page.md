# Log on to the Web configuration page {#task_hd1_d55_mfb .task}

After you power on the Smart Access Gateway device, you need to log on to the Web configuration page.

Before you log on to the Web configuration page, make sure that:

-   The Smart Access Gateway is powered on.
-   For a SAG-100WM device, its LAN port is connected to the local client. For a SAG-1000 device, the administration port 2 is connected to the network cable.
-   The local client has DHCP enabled to automatically obtain an IP address.

1.  Enter the default Web configuration address `192.168.0.1` of the SAG device in your browser. 

    For an SAG-100WM device, note the following:

    -   If you have configured the LAN port, the Web configuration address of the SAG device is the static IP address of the LAN port.
    -   If you have not configured a static IP address for the LAN port, but have configured a private CIDR block for the SAG instance in the console, the Web configuration address is the first address in the first private CIDR block configured by you. For example, if the first CIDR block specified by you is 192.168.0.0/16, the Web configuration address is 192.168.0.1.
2.  Set the logon password. Keep your logon password confidential. If the password is lost or forgotten, press the reset button on your device once to reset the password.
3.  Log on to the Web configuration page.

