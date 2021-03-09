# Use SAG and CEN to access OSS

This topic describes how to use Smart Access Gateway \(SAG\) along with Cloud Enterprise Network \(CEN\) to connect on-premises clients to Alibaba Cloud. This way, the clients can access Object Storage Service \(OSS\) buckets through CEN.

-   A Virtual Private Network \(VPC\) network is deployed in the China \(Shanghai\) region. For more information, see [Create a VPC](/intl.en-US/VPCs and vSwitchs/Create a VPC.md).
-   A CEN instance is created and associated with the VPC network in the China \(Shanghai\) region. For more information, see [Create a CEN instance]().

Cloud services refer to Alibaba Cloud services, such as OSS, Log Service, and Data Transmission Service \(DTS\), that use the CIDR block 100.64.0.0/10 to provide services. You can use SAG to connect on-premises clients to Alibaba Cloud and then access cloud services through CEN.

OSS is a secure, cost-effective, and highly reliable cloud storage service provided by Alibaba Cloud. You can store large amounts of data in OSS buckets. OSS buckets are accessible through their endpoints. Endpoints refer to internal network connections between Alibaba Cloud services that are deployed in different regions. If you access an OSS bucket through its endpoint, no data transfer fees are incurred. The following figure shows how on-premises clients of a company are connected to Alibaba Cloud and access OSS buckets through their endpoints. The company has created a VPC network in the China \(Shanghai\) region and plans to activate OSS in this region. The company needs to store sensitive data in OSS buckets and allow employees to download the data through the endpoints of the OSS buckets. To meet the preceding requirements while minimizing expenses, the company plans to connect on-premises clients to Alibaba Cloud through the SAG app.

![How on-premises clients are connected to Alibaba Cloud](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8706631061/p165144.png)

## Configuration procedure

![Configuration procedure](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8706631061/p165699.png)

## Step 1: Purchase OSS

You can deploy OSS through multiple methods. This procedure demonstrates how to deploy OSS in the OSS console. For more information, see [What is OSS?](/intl.en-US/Product Introduction/What is OSS?.md)

1.  Activate OSS. For more information, see [Activate OSS](/intl.en-US/Console User Guide/Sign up for OSS.md).

2.  Create an OSS bucket.

    1.  Log on to the [OSS console](https://oss.console.aliyun.com/).

    2.  In the left-side navigation pane, click **Buckets**. On the Buckets page, click **Create Bucket**.

    3.  In the Create Bucket pane, set the parameters.

        The following parameters are set in this example. You can set parameters based on your business requirements. For more information, see [Create buckets](/intl.en-US/Console User Guide/Manage buckets/Create buckets.md).

        -   **Bucket Name**: Specify a name for the bucket. The name cannot be changed after the bucket is created. shosstest is used in this example.
        -   **Region**: Select the region where you want to create the bucket. The region cannot be changed after the bucket is created. **China \(Shanghai\)** is used in this example.
        -   **Storage Class**: Select a storage class for the bucket. **Standard** is used in this example.

            The standard storage class provides highly reliable, highly available, and high-performance object storage services that can handle frequent data access. Standard storage is suitable for scenarios such as image sharing, social media, audio and video applications, large-scale websites, and big data analytics. For more information, see [Overview](/intl.en-US/Developer Guide/Storage classes/Overview.md).

        -   **Zone-redundant Storage**: Select whether to enable zone-redundant storage. **Disable** is selected in this example.

            If you disable zone-redundant storage, replicas of files stored in the bucket are saved only in the current zone.

        -   **Versioning**: Select whether to enable versioning. **Enable** is selected in this example.

            If you enable versioning for the bucket, data that is overwritten or deleted is saved as a historical version. Versioning allows you to restore objects in a bucket to a specific version. It protects your data from accidental overwritten or deletion. For more information, see [Overview](/intl.en-US/Developer Guide/Data security/Versioning/Overview.md).

        -   **Access Control List \(ACL\)**: Select the read and write permissions on the bucket. **Private** is selected in this example.

            Only the bucket owner can perform read and write operations on objects in the bucket. Other users do not have access to objects in the bucket.

        -   **Encryption Method**: Select whether to enable server-side encryption. **None** is selected in this example.
        -   **Real-time Log Query**: Select whether to enable real-time log query. **Disable** is selected in this example.
        -   **Scheduled Backup**: Select whether to enable scheduled backup to back up data in the OSS bucket by using Hybrid Backup Recovery \(HBR\). **Disable** is selected in this example.
    4.  Click **OK**.

3.  Upload an object to the OSS bucket.

    1.  In the left-side bucket management pane, click **Files**.

    2.  Click **Upload**.

    3.  In the **Upload** pane, set the parameters.

        -   **Upload To**: Specify the path to which you want to upload the object. The default path is used in this example.
        -   **File ACL**: Select the read and write permissions on the object. The default option is **Inherited from Bucket**. The default option is used in this example.
        -   **Upload**: Drag and drop one or more objects to this section, or click **Upload** to upload objects.
    4.  In the Upload Tasks dialog box, wait until the objects are uploaded to the bucket and then close the dialog box.

4.  Set permissions on the object.

    For data security, the bucket is set to private in this example. Therefore, permissions on a specific object must be manually granted to users that need to access the object. The following example demonstrates how to grant read-only permissions on an image file to all users. You can set permissions on objects based on your business requirements. For more information, see [Add bucket policies](/intl.en-US/Console User Guide/Upload, download, and manage objects/Add bucket policies.md).

    1.  On the **Files** tab, click **Authorize**.

    2.  In the Authorize pane, click **Authorize**.

    3.  In the Authorize pane to which you are redirected, set the following parameters and click **OK**.

        -   **Applied To**: **Specified Resource** is selected in this example.
        -   **Resource Paths**: SHOSS.jpg is specified in this example.
        -   **Accounts**: **Anonymous Accounts** is selected in this example.
        -   **Authorized Operation**: **Read Only** is selected in this example.
        ![OSS-Set the image file to read-only](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/0360201061/p165522.png)


## Step 2: Connect on-premises clients to Alibaba Cloud

In this step, you must purchase an SAG APP instance, set up network connections, and create client accounts in the SAG console. After the configurations are completed, on-premises clients can connect to Alibaba Cloud through the SAG app.

1.  Purchase an SAG APP instance.

    1.  Log on to the [SAG console](https://smartag.console.aliyun.com/sag/cn-shanghai/sags).

    2.  In the left-side navigation pane, click **Smart Access Gateway APP**.

    3.  On the Smart Access Gateway APP page, click **Create SAG APP** and set the following parameters:

        -   **Region and Zone**: Select the area where you want to create the SAG APP instance. **Mainland China** is selected in this example.
        -   **Number of Client Accounts**: Specify the number of client accounts that can be added to the SAG APP instance. Typically, you need to create an account for each user that needs to log on to the SAG app. The default value 10 is used in this example.

            **Note:** You can purchase 5 to 1,000 client accounts for each SAG APP instance. Pricing is tiered and based on the number of client accounts. For more information, see [Billing and pricing of the SAG app](/intl.en-US/Smart Access Gateway APP/Billing and pricing of the SAG app.md).

        -   **Data Plan Per Account**: The amount of free data usage allocated to each client account per month. The data transfer plan cannot be shared among different accounts and remains effective only within the month. By default, 5 GB of data usage is offered to each client account per month.
        -   **Billing Method When Data Plan is Exhausted**: If the actual data usage of an account exceeds the data transfer plan, the excess data is charged based on the pay-as-you-go billing method.
        -   **Subscription Duration**: Select the subscription duration of the data transfer plan for each account. Monthly subscriptions and auto renewal are supported. One month is selected in this example.
    4.  Click **Buy Now** to confirm the order and complete the payment.

2.  Set up network connections.

    After you purchase an SAG APP instance, you must set up network connections. In this step, you must associate the SAG APP instance with a Cloud Connect Network \(CCN\) instance and specify the CIDR blocks of the clients.

    CCN is an important component of SAG. After an SAG APP instance is associated with a CCN instance, on-premises clients associated with the SAG APP instance can connect to Alibaba Cloud. For more information, see [Introduction to CCN](/intl.en-US/Configuration Guide/Cloud Connect Network/Introduction to CCN.md).

    1.  On the Smart Access Gateway APP page, find the SAG APP instance that you want to manage and click **Quick Configuration** in the **Actions** column.

    2.  In the Quick Configuration wizard, set the required parameters.

        -   **CCN**: You can select one of the following options to associate the SAG APP instance with a CCN instance. **Create CCN** is selected in this example.
            -   **Existing CCN**: If you have already created CCN instances, you can select an existing CCN instance from the drop-down list.
            -   **Create CCN**: If you have not created a CCN instance, enter an instance name. The system then creates a CCN instance and automatically associates it with the SAG APP instance.

                The name must be 2 to 100 characters in length, and can contain digits, underscores \(\_\), and hyphens \(-\). The name must start with a letter or a Chinese character.

        -   **Standby and Active DNS**: optional. The active and standby DNS servers that the clients use to connect to the private network through the SAG app. After you configure the DNS servers, the system automatically synchronizes the DNS settings to the clients. Ignore this parameter in this example.
        -   **Private CIDR Block**: Specify the private CIDR blocks that the clients use to connect to Alibaba Cloud. When a client connects to Alibaba Cloud, an IP address within the specified CIDR block is assigned to the client. Make sure that the private CIDR blocks do not overlap with each other. 192.168.10.0/24 is used in this example.

            You can click **Add Private CIDR Block** to add more private CIDR blocks. You can add a maximum of five private CIDR blocks.

3.  Associate the CCN instance with a CEN instance.

    You must associate the CCN instance with a CEN instance. This way, on-premises clients associated with the SAG APP instance can access OSS through the CEN instance.

    1.  Click **Associate with a CEN \(Optional\)** to associate the CCN instance with a CEN instance.

    2.  You can select one of the following options to associate the CCN instance with a CEN instance to enable communication between the clients and cloud resources. **Existing CEN** is selected in this example.

        -   **Existing CEN**: If you have already created CEN instances, you can select a CEN instance from the drop-down list.
        -   **Create CEN**: If you have not created a CEN instance, enter an instance name. The system then creates a CEN instance and automatically associates it with the CCN instance.

            The name must be 2 to 100 characters in length, and can contain digits, underscores \(\_\), and hyphens \(-\). It must start with a letter or a Chinese character.

4.  Create a client account.

    After you set up network connections, you must create client accounts to allow on-premises clients to log on to the SAG app and connect to the private network.

    1.  Click **Next: Create a client account** to create a client account.

        -   **Username**: optional. The username must be 7 to 33 characters in length, and can contain underscores \(\_\), at signs \(@\), periods \(.\), and hyphens \(-\). It must start with a digit or a letter.

            **Note:**

            -   The usernames of client accounts added to the same SAG APP instance must be unique.
            -   When you create a client account, if you specify only the email address, the system automatically generates a username and password. The specified email address is used as the username.
        -   **Email Address**: required. The email address of the user. The username and password are sent to the specified email address.

            The email address must be 2 to 64 characters in length, and can contain letters, digits, underscores \(\_\), periods \(.\), and hyphens \(-\). It must contain an at sign \(@\).

        -   **Static IP**:
            -   If you enable this feature, you must configure the IP address of the client. The client account uses the specified IP address to connect to Alibaba Cloud.

                **Note:** The specified IP address must fall into the CIDR block of the private network.

            -   If you disable this feature, an IP address within the CIDR block of the private network is assigned to the client. Each connection to Alibaba Cloud uses a different IP address.
        -   **Set Maximum Bandwidth**: Specify the maximum bandwidth for the client account. The default value is used in this example.

            You can set the maximum bandwidth to 1 to 2,000 Kbit/s. The maximum bandwidth is set to 2,000 Kbit/s by default.

        -   **Set Password**: optional. Set the password that is used to log on to the SAG app.

            The password must be 8 to 32 characters in length, and can contain underscores \(\_\) and hyphens \(-\). It must start with a letter or a digit.

    2.  Click **OK**.

5.  Connect the client to Alibaba Cloud.

    1.  After you create a client account, click **Download Now** to go to the page that provides instructions on how to download and install the SAG app. For more information, see [Install the SAG app](/intl.en-US/Smart Access Gateway APP/User guide for end users/Install the SAG app.md).

    2.  After the SAG app is installed on a client, the client can log on to the SAG app with the client account and connect to Alibaba Cloud. For more information, see [Connect to Alibaba Cloud](/intl.en-US/Smart Access Gateway APP/User guide for end users/Connect to an intranet environment.md).

    ![Connect to Alibaba Cloud](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/0360201061/p166079.png)


## Step 3: Configure routes to OSS

In this step, you must configure routes to OSS in the CEN console. After routes are configured, CEN establishes network communication between the network associated with the CCN and OSS. This way, on-premises clients can access OSS through CEN.

1.  Log on to the [CEN console](https://cen.console.aliyun.com/cen/list).

2.  On the Instances page, click the ID of the CEN instance that you want to manage.

3.  On the AnnyTunnel tab, click **SetAnyTunnelService**.

    ![AnyTunnel](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/0360201061/p96967.png)

4.  In the SetAnyTunnelService pane, set the following parameters:

    -   **Service IP address**: Enter an IP address or CIDR block used by OSS. The IP address or CIDR block must fall into 100.64.0.0/10. In this example, 100.118.102.0/24 is used.

        Typically, a cloud service uses multiple IP addresses. Repeat the preceding steps to add routes to all the IP addresses of OSS. In the China \(Shanghai\) region, add the following CIDR blocks of OSS:

        -   100.98.35.0/24
        -   100.98.110.0/24
        -   100.98.169.0/24
        -   100.118.102.0/24
        For more information, see [OSS internal endpoints and VIP address ranges](/intl.en-US/Developer Guide/Endpoint/OSS internal endpoints and VIP address ranges.md).

    -   **Host Region**: Select the region where OSS is deployed. **China \(Shanghai\)** is selected in this example.
    -   **Host VPC**: From the drop-down list, select a VPC network that is attached to the CEN instance.

        After you select a VPC network, networks attached to the CCN instance can access OSS through the VPC network.

    -   **Access Region**: Select the CCN instance that is associated with the CEN instance. **Mainland China CCN** is selected in this example.

        **Note:** Make sure that the selected CCN instance is associated with the CEN instance. For more information, see [Configure routes to OSS](#step_b2l_v9z_wky).

    -   **Description**: Enter a description for OSS. This parameter is optional.

        The description must be 2 to 256 characters in length, and can contain digits, hyphens \(-\), underscore \(\_\), and periods \(.\). It must start with a letter or a Chinese character and cannot start with `http://` or `https://`.

    ![OSS-AnyTunnel](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/0360201061/p165539.png)

5.  Click **OK**.


## Step 4: Test network connectivity

After the preceding steps are completed, on-premises clients can connect to Alibaba Cloud through the SAG app and access OSS.

For example, you can visit `https://shosstest.oss-cn-shanghai-internal.aliyuncs.com/SHOSS.jpg` through the SAG app and download the image file `SHOSS.jpg`.

