# Manage accounts {#task_pnk_bbk_wgb .task}

This topic describes how to manage accounts as an administrator. After you configure the network, you can create multiple accounts and distribute them to end users so that clients can access Alibaba Cloud.

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com/sag/cn-shanghai/sags).
2.  Click the instance ID of the target Smart Access Gateway \(SAG\) APP.
3.  In the Client Accounts area of the Smart Access Gateway APP Details page, click **Create Client Account**.
4.  On the Create Client Account page, configure the accounts to be used by end users to log on to SAG APP clients. 

    -   **Username**: Optional. By default, it is an email account. The username must be 2 to 32 characters in length, and can contain letters, numbers, underscores \(\_\), at signs \(@\), periods \(.\), and hyphens \(-\).
    -   **Email Address**: Required. The email address of the end user used by the administrator to send the newly created account information.

        The email address must contain the at sign \(@\) and must be 2 to 32 characters in length. It can contain letters, numbers, underscores \(\_\), at signs \(@\), periods \(.\), and hyphens \(-\).

    -   **Static IP**:
        -   If you enable this option, you must specify an IP address for the client. The account will always use the specified IP address to access Alibaba Cloud.

            **Note:** The IP address specified for the client must be within the private CIDR block of the SAG APP.

        -   If you disable this option, the system automatically allocates an IP address from the private CIDR block of the SAG APP to the client each time a connection is established.
    -   **Set Maximum Bandwidth**: The peak bandwidth for the current account.

        The available bandwidth range is 1 Kbps to 2 Mbps, and the default value is 2 Mbps.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/129979/156376121044288_en-US.png)

5.  Click **OK**. The end user receives the account information and instructions about how to download the client.

    ![](images/43452_en-US.png)


