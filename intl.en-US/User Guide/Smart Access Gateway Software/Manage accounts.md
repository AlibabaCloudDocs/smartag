# Manage accounts {#task_pnk_bbk_wgb .task}

This topic describes how to create and manage accounts as an administrator. After completing the network configuration, you can create multiple accounts and distribute them to end users so that clients can access Alibaba Cloud.

1.  Log on to the [SAG console](https://smartag.console.aliyun.com/sag/cn-shanghai/sags).
2.  Click the instance ID of the target Smart Access Gateway Software \(SAG Software\).
3.  In the Client Accounts area of the Smart Access Gateway Software Details page, click **Create Client Account**.
4.  On the Create Client Account page, set the configurations for the accounts to be used by end users to log on to SAG software clients. 

    -   **Username**: Optional. By default, it is an email account. The username must be 2 to 32 characters in length, and can contain letters, numbers, underscores \(\_\), at signs \(@\), periods \(.\), and hyphens \(–\).
    -   **Email Address**: Required. The email address of the end user used by the administrator to send the newly created account information.

        The email address must contain the at sign \(@\) and must be 2 to 32 characters in length. It can contain letters, numbers, underscores \(\_\), at signs \(@\), periods \(.\), and hyphens \(-\).

    -   **Whether to use a specified IP address**:
        -   If you enable this option, you must specify an IP address for the client. The account will always use the specified IP address to access Alibaba Cloud.

            **Note:** The IP address specified for the client must be within the private CIDR block of the SAG software.

        -   If you disable this option, the system automatically allocates an IP address from the private CIDR block of the SAG software to the client each time a connection is established.
    -   **Peak Bandwidth** 

        The available bandwidth range is 1 kbps to 2 Mbps, and the default value is 2 Mbps.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/129979/155745405844288_en-US.png)

5.  Click **OK**. After the preceding configurations are set, the end user receives the account information and instructions about how to download the client.

