# Step 1: Configure the local client {#concept_xpj_fj1_qfb .concept}

Before performing web configurations on the SAG-100, you must configure the static IP address of the local client to access the web configurations.

## Windows client configuration {#section_bzn_qj1_qfb .section}

To configure a static IP for a Windows client, follow these steps:

1.  Right-click the network connection icon in the lower right corner, then click **Open the Network and Sharing Center**.
2.  In the left-side panel, click **Change Adapter Configurations**.
3.  Right-click the connected network and then click **Properties**.
4.  Double-click the **Internet Protocol Version 4 \(TCP/IPv4\)** option.
5.  Select the **Use the following IP addresses** option and enter the static IP address and subnet mask to use.

    **Note:** Ensure that the IP address is in the administration CIDR block of the gateway device \(the default administration CIDR block is 192.168.0.0/24\) and does not conflict with other IP addresses. For example, 192.168.0.99. You do not need to configure the gateway and DNS.

6.  Click **OK**.

## Mac client configuration {#section_cmw_vm1_qfb .section}

To configure a static IP for a Mac client, follow these steps:

1.  On the desktop, click the **System Preferences** icon, and then click **Network** in the Internet and Wi-Fi option. **Open Network and Sharing Center**.
2.  Click the connected network and then click **Advanced**.
3.  On the Ethernet configuration page, click the **TCP/IP** tab page.
4.  In the **Configure IPv4** option, select **Manual**, and enter the static IP and subnet mask to use.

    **Note:** Ensure that the IP address is in the administrator CIDR block of the gateway device \(the default administrator CIDR block is 192.168.0.0/24\) and does not conflict with other IP addresses. For example, 192.168.0.99. You do not need to configure the router and DNS.


