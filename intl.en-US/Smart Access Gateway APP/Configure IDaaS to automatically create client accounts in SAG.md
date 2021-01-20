# Configure IDaaS to automatically create client accounts in SAG

This topic describes how to use Alibaba Cloud Identity as a Service \(IDaaS\) to automatically create client accounts that are used to log on to the Smart Access Gateway \(SAG\) app. Then, the employees of your enterprise can use their employee accounts to log on to the SAG app and connect to the private network of the enterprise.

-   An Active Directory \(AD\) system is deployed and employee account data is synchronized to IDaaS. For more information, see [LDAP Provision Configuration](https://www.alibabacloud.com/help/zh/doc-detail/151237.htm?spm=a2c63.q38357.b99.8.24592d58I8B8RY).
-   A virtual private cloud \(VPC\) is created. For more information, see [Create a VPC](/intl.en-US/VPCs and VSwitches/VPC management/Create a VPC.md).

When an employee of an enterprise needs to access the private network of the enterprise through the SAG app, the administrator must create a client account in the SAG console for the employee. If the enterprise has a large number of employees and uses an AD system, creating and managing client accounts can be troublesome. To improve the user experience, Alibaba Cloud provides a solution that integrates SAG with IDaaS. You can add SAG to IDaaS as an application and grant application accounts the required permissions. Then, IDaaS can create client accounts in SAG. The client accounts created by IDaaS use the same usernames and passwords as the employee accounts. This way, employees can use their employee accounts to log on to the SAG app and access resources after their identities are verified.

The following example demonstrates how to add SAG to IDaaS as an application and then configure IDaaS to automatically create client accounts. After the client accounts are created, employees can use their employee accounts to log on to the SAG app and then connect to the private network of the enterprise.

![SAG works with IDaaS](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3881111161/p187938.png)

A large-scale enterprise has deployed an AD system. To facilitate employee account management and permission control, the AD system of the enterprise is connected with IDaaS and account data is synchronized to IDaaS. Due to business growth, the enterprise wants to enable employees to remotely access its resources deployed on Alibaba Cloud. The enterprise decides to use the SAG app to connect mobile clients to Alibaba Cloud. This solution facilitates account management and permission control. This solution requires the enterprise to add SAG to IDaaS as an application. Then, configure IDaaS to automatically create client accounts and grant permissions on SAG. After client accounts are created, employees can use their employee accounts to log on to the SAG app from mobile clients and then connect to the private network of the enterprise.

## Procedure

![Procedure for configuring IDaaS](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3881111161/p188428.png)

## Step 1: Purchase an SAG APP instance

You must purchase an SAG APP instance before you can use the SAG app. After you purchase an SAG APP instance, you can use the instance to manage connections between Alibaba Cloud and your private network or clients.

1.  Log on to the [SAG console](https://smartag.console.aliyun.com/sag/cn-shanghai/sags).

2.  In the left-side navigation pane, choose **Smart Access Gateway APP** \> **SAG APP Instances**.

3.  On the Smart Access Gateway APP page, click **Create SAG APP**. Set the following parameters and complete the payment:

    -   **Area**: Select the area where the SAG app is to be used. **Mainland China** is selected in this example.
    -   **Number of Client Accounts**: Select the number of client accounts that you want to purchase. **10** is selected in this example.

        This parameter specifies the number of client accounts that can be added to the SAG instance. Typically, you must create a client account for each user that needs to access the private network.

        **Note:** You can select 5 to 1,000 client accounts. Client accounts are billed based on a tiered pricing strategy. For more information, see [Billing and pricing of the SAG app](/intl.en-US/Smart Access Gateway APP/Billing and pricing of the SAG app.md).

    -   **Data Plan Per Account**: The amount of free quota of data transfer for each client account. Default value: **5 GB**.

        The free quota of data transfer cannot be shared among client accounts and is valid only within the month when the data transfer quota is allocated.

    -   **Billing Method When Data Plan is Exhausted**: The metering method used to bill the amount of data transfer that exceeds the free quota for each client account. Default value: **Pay-By-Data-Transfer**.

        The billing method of **Pay-By-Data-Transfer** is pay-as-you-go. For more information, see [Billing and pricing of the SAG app](/intl.en-US/Smart Access Gateway APP/Billing and pricing of the SAG app.md).

    -   **Subscription Duration**: The default value **1 Month** is selected in this example.

        SAG supports monthly subscriptions and auto-renewal.


## Step 2: Synchronize employee account data to IDaaS

After you purchase an SAG APP instance, you must add SAG to IDaaS as an application in the IDaaS console. Associate the application with the SAG instance and grant the application account permissions. Then, IDaaS automatically creates client accounts in the SAG console. The client accounts use the same usernames as the application accounts.

1.  Add SAG to IDaaS.

    1.  Log on to the [IDaaS console](https://yundun.console.aliyun.com/?spm=5176.12818093.0.didaas.6cb216d0VHVK5t&p=idaas#/instanceList/ap-southeast-1).

    2.  In the top navigation bar, select the region where the IDaaS instance is deployed.

    3.  On the **Instances** page, click the ID of the IDaaS instance.

    4.  In the left-side navigation pane, click **Add Applications**.

    5.  On the Add Application page, find **Aliyun SAG** and click **Add Application** in the **Actions** column.

    6.  In the **Add Application \(Aliyun SAG\)** panel, set the following parameters and click **Submit**:

        -   **Application Logo**: You can customize the SAG icon.

            Click **Upload File** and select the image file that you want to upload.

        -   **Application Name**: You can specify a name for SAG. **Aliyun SAG** is used in this example.
        -   **appKey**: Enter the AccessKey ID of your Alibaba Cloud account.
        -   **appSecret**: Enter the AccessKey secret of your Alibaba Cloud account.

            You can view your AccessKey ID and AccessKey secret on the [Security Management](https://ak-console.aliyun.com/#/accesskey) page.

            **Note:** An Alibaba Cloud account has full permissions on its resources. You have the same permissions when you sign in with either the AccessKey pair or the password of your Alibaba Cloud account. The AccessKey pair is used for program access, whereas the password is used for console logon. To prevent information leaks due to the disclosure of the AccessKey pair, we recommend that you do not create an AccessKey pair for your Alibaba Cloud account or use the AccessKey pair to manage resources.

            You can create AccessKey pairs for Resource Access Management \(RAM\) users and use the RAM users to manage resources. For more information, see [Create an AccessKey pair for a RAM user](/intl.en-US/Security Settings/AccessKey pairs/Create an AccessKey pair for a RAM user.md).

        -   **Gateway area**: Select the area where the SAG APP instance is deployed. **China \(Shanghai\)** is selected in this example.

            After you set **appKey** and **appSecret**, you can click **Query** next to **Gateway area**. The system automatically searches for areas where you can create SAG APP instances under the current Alibaba Cloud account. Then, you can select an area from the **Gateway area** drop-down list.

            **Note:** If your SAG APP instance is deployed in the Mainland China area, select **China \(Shanghai\)**.

        -   **Gateway Information**: Select the SAG APP instance that you want to authorize IDaaS to access. The SAG APP instance created in Step 1 is selected in this example.
        -   **Account Linking Type**: Select a method to associate the IDaaS account with an application account. **Account mapping** is selected in this example.
            -   **Account association**: Select this option if you already have an application account. The system associates the IDaaS account with the specified application account.
            -   **Account mapping**: Select this option if you do not have an application account. The system uses the username of the IDaaS account to create an application account.
2.  Configure System for Cross-domain Identity Management \(SCIM\) settings.

    After you add SAG to IDaaS, you must configure SCIM settings for SAG. SCIM settings are required to create client accounts. To configure SCIM settings,submit a ticket to the Alibaba Cloud IDaaS team.

3.  Grant application accounts permissions on SAG.

    1.  In the left-side navigation pane, click **Application Authorization**.

    2.  On the **Application Authorization** page,click the **Authorize Accounts by Applications** tab and click the application.

    3.  In the**Accounts** section, select the account that you want to authorize and click **Save**.

4.  Synchronize the account information to the SAG APP instance.

    1.  In the left-side navigation pane, click **Organizations and Groups**.

    2.  On the **OUs and Groups** page, find the **OUs** section and click the organization that you want to manage.

    3.  On the **Account** tab, find the account that you want to manage and click **Provision Account** in the **Actions** column.

    4.  In the **Provision Account** panel, you can view the provisioning progress of the account.

        If the account is in the **Yes** state, it indicates that the account has been granted the permissions. Click **Provision**. After the account information is synchronized to the SAG instance, IDaaS creates a client account with the username of the application account.

        ![Account provisioning progress](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6258229061/p188223.png)

    5.  View information about client accounts.

        After a client account is created, you can view its information in the SAG console.

        1.  Log on to the [SAG console](https://smartag.console.aliyun.com/sag/cn-shanghai/sags).
        2.  In the left-side navigation pane, choose **Smart Access Gateway APP** \> **SAG APP Instances**.
        3.  In the top navigation bar, select **Mainland China**.
        4.  On the **Smart Access Gateway APP** page, click the ID of the SAG APP instance that you want to manage.
        5.  On the instance details page, click the **Client Accounts** tab.
        6.  On the **Client Accounts** tab, you can view information about client accounts.

            The **Client Accounts** tab displays only the username of each client account. By default, the password is not displayed.

            ![Information about client accounts](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7258229061/p188240.png)

    6.  View client account information

        After a client account is created, the system sends you an email that includes the username of the client account, the ID of the SAG APP instance, and the enterprise code of the SAG APP instance. You can use this information to log on to the SAG app.

        **Note:** The system sends an email that includes the preceding information to you only if you have specified an email address. If you have not specified an email address, you can log on to the SAG console to view the preceding information.


## Step 3: Set up network connections

After a client account is created, you must set up network connections for the SAG APP instance to allow the client to access Alibaba Cloud and the private network of your enterprise.

1.  Set up network connections for the SAG APP instance.

    1.  Log on to the [SAG console](https://smartag.console.aliyun.com/sag/cn-shanghai/sags).

    2.  In the left-side navigation pane, choose **Smart Access Gateway APP** \> **SAG APP Instances**.

    3.  In the top navigation bar, select **Mainland China**.

    4.  On the **Smart Access Gateway APP** page, find the SAG APP instance and click **Network Configuration** in the **Actions** column.

    5.  In the **Network Configuration** dialog box, set the following parameters and click **OK**:

        -   **Instance Name/ID**: The current SAG APP instance is selected by default.
        -   **CCN**: You can select one of the following options to associate the SAG APP instance with a Cloud Connect Network \(CCN\) instance. **Create CCN** is selected in this example.

            CCN is an important component of SAG. After an SAG APP instance is associated with a CCN instance, clients associated with the SAG APP instance can communicate with networks attached to the CCN instance. For more information about CCN, see [Introduction to CCN](/intl.en-US/Configuration Guide/Cloud Connect Network/Introduction to CCN.md).

            -   **Existing CCN**: If you have already created CCN instances, you can select an existing CCN instance from the drop-down list.
            -   **Create CCN**: If you have not created a CCN instance, enter an instance name. The system then creates a CCN instance in the current region and automatically associates the CCN instance with the SAG APP instance.

                The instance name must be 2 to 100 characters in length, and can contain digits, underscores \(\_\), and hyphens \(-\). The name must start with a letter.

        -   **Standby and Active DNS**: optional. The active and standby DNS servers that the client uses to connect to the private network through the SAG app. After you configure the DNS servers, the system automatically synchronizes the DNS settings to the client. This parameter is ignored in this example. For more information, see [Set up network connections](/intl.en-US/Smart Access Gateway APP/User guide for administrators/Set up network connections.md).
        -   **Private CIDR Block**: Enter the private CIDR block that the client uses to access Alibaba Cloud. When a client connects to Alibaba Cloud, the system automatically selects an idle IP address from the specified private CIDR block. 192.168.1.0/24 is used in this example.

            You can click **Add Private CIDR Block** to add more private CIDR blocks. You can add a maximum of five private CIDR blocks. Make sure that the CIDR blocks do not overlap with each other.

2.  Configure a Cloud Enterprise Network \(CEN\) instance.

    You must associate the CCN instance with a CEN instance. This way, networks attached to the CCN instance can communicate with resources associated with the CEN instance. For more information, see [What is Cloud Enterprise Network?]().

    1.  In the left-side navigation pane, click **CCN**.

    2.  On the **CCN** page, find the CCN instance and click **Bind CEN Instance** in the Actions column.

    3.  In the **Bind CEN Instance** penal, set the following parameters and click **OK**:

        -   **Instance Name/ID**: The current CCN instance is selected by default.
        -   **Bind CEN Instance**: You can select one of the following options to associate the CCN instance with a CEN instance. **Create CEN** is selected in this example.
            -   **Existing CEN**: If you have already created CEN instances, you can select an existing CEN instance from the drop-down list.
            -   **Create CEN**: If you have not created a CEN instance, enter an instance name. The system then creates a CEN instance and automatically associates it with the CCN instance.

                The instance name must be 2 to 100 characters in length, and can contain digits, underscores \(\_\), and hyphens \(-\). It must start with a letter.

3.  Configure the virtual private cloud \(VPC\).

    1.  Create a security group rule for the Elastic Compute Service \(ECS\) instance deployed in the VPC to allow the private CIDR block 192.168.1.0/24 to access resources on the ECS instance. For more information, see [Add security group rules](/intl.en-US/Security/Security groups/Add security group rules.md).

    2.  Associate the VPC with the CEN instance to allow clients connected to the CCN instance to communicate with resources in the VPC through the CEN instance. For more information, see [Attach networks]().


## Step 4: Connect to the private network

After you perform the preceding steps, you must download and install the SAG app and connect to the private network.

1.  Download and install the SAG app. For more information, see [Install the SAG app](/intl.en-US/Smart Access Gateway APP/User guide for end users/Install the SAG app.md).

2.  After you install the SAG app, you can log on to it with the username and password of your employee account and the enterprise code of the SAG APP instance. You can then connect to the private network of your enterprise.

    ![Connect to the private network](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7258229061/p188266.png)


