# Connect AWS to Alibaba Cloud through SAG vCPE

This topic describes how to establish network communication between cloud resources deployed on Alibaba Cloud and Amazon Web Services \(AWS\).

Before you start, make sure that the following requirements are met:

-   Cloud services are deployed on an AWS server. For more information, consult your service provider.
-   Virtual Private Cloud \(VPC\) networks are created. For more information, see [Create a VPC](/intl.en-US/VPCs and VSwitches/VPC management/Create a VPC.md).

SAG vCPE is an image that can be deployed on cloud instances. You can deploy the SAG vCPE image on an Alibaba Cloud Edge Node Service \(ENS\) instance or an AWS instance. After the image is deployed on an instance, the instance functions as a virtual client-premises equipment \(CPE\) device. This allows you to connect private networks to Alibaba Cloud in a more flexible way.

The following figure describes how to establish network communication between cloud resources deployed on Alibaba Cloud and AWS. For example, an enterprise has deployed cloud services on Alibaba Cloud in the Singapore \(Singapore\) region and on AWS. The enterprise wants to establish network communication between cloud resources deployed on Alibaba Cloud and AWS.

![Procedure](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/4410380061/p139990.png)

## Procedure

![Procedure](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/4410380061/p139916.png)

## Step 1: Purchase an SAG vCPE device

After you purchase an SAG vCPE device in the SAG console, the system creates an SAG vCPE instance that allows you to manage and configure the SAG vCPE device.

1.  Log on to the [SAG console](https://smartag.console.aliyun.com).

2.  On the Smart Access Gateway page, click **Purchase SAG**.

3.  Set the following parameters and click **Buy Now**.

    -   **Area**: Select the region where you want to deploy the SAG vCPE image. **Singapore** is selected in this example.
    -   **Instance Name**: Optional. Enter a name for the SAG vCPE instance.

        The name must be 2 to 128 characters in length, and can contain digits, periods \(.\), underscores \(\_\), and hyphens \(-\). It must start with a letter or a Chinese character.

    -   **Instance Type**: Select the instance type. **SAG-vCPE** is selected by default.
    -   **Edition**: Select the edition of SAG vCPE. **Basic Edition** is selected by default.
    -   **Deployment Mode**: Select the deployment mode. **HA** is selected by default.

        You can purchase two SAG vCPE devices, and use one as the active device and the other as the standby device. When the active device is faulty, you can switch to the standby device. In this example, only the active device is used.

    -   **Peak Bandwidth**: Select the maximum bandwidth for network connections.
    -   **Quantity**: Enter the number of SAG vCPE devices that you want to purchase. **1** is entered in this example.
    -   **Duration**: Select the duration of the subscription.

        You can select **Auto-renewal** to enable automatic renewal upon expiration.

4.  On the Confirm Order page, confirm the order information, select **I have read and agree to Smart Access Gateway-vCPE Agreement of Service**, and then click **Pay**.

5.  Return to the SAG console. In the top navigation bar, select the region that you specified when you created the SAG vCPE instance.

6.  On the **Smart Access Gateway** page, click the ID of the SAG vCPE instance that you created.

7.  On the page that appears, click the **Device Management** tab and record the serial number and key of the active SAG vCPE device.

    ![View the serial number and key](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/5752240061/p137880.png)


## Step 2: Deploy the SAG vCPE image

To establish network communication between cloud resources deployed on Alibaba Cloud and AWS, you must create an instance in the AWS VPC network. Then, you can deploy the SAG vCPE image on the newly created instance. After you deploy the image, AWS can be connected to Alibaba Cloud through the AWS SAG vCPE instance.

For more information about how to create an instance in the AWS VPC network, see relevant documentations provided by AWS. When you create an AWS VPC instance, note that:

1.  When you select a system image for the instance, select the SAG vCPE image.

    To select the SAG vCPE image, [submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.15120809.nav-right.dticket.130266ebEB92in#/ticket/add/?productId=1308).

    ![Select an AMI](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/7752240061/p139734.png)

2.  When you select the instance type, we recommend that you select a vCPU with 2 cores and 4 GB memory.

    With the preceding specification, the bandwidth of private networks for encrypted connections can reach 300 Mbit/s and higher \(the packet length in the performance test is 1024 bytes\). You can also select a vCPU with 1 core and 2 GB memory. In this case, the system performance is at least 30% lower. You can select the specification based on your requirements.

    ![2C4G](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/7752240061/p142362.png)

3.  When you configure the instance, you must provide the serial number and key of the SAG vCPE device to associate the SAG vCPE device with the SAG vCPE instance. Make sure that a public IP address is assigned to the instance.

    An example of the serial number and key:

    ```
    {"sn":"sage6m2ph5sit**********","key":"y7y7LUWqnbc4fCpIJnxRQ2c1nOYtW***********"}
    ```

    ![Enter the serial number and key](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/7752240061/p139741.png)

4.  When you configure the security group, you must allow the private CIDR blocks of Alibaba Cloud and AWS to access the SAG vCPE instance.

5.  After the instance is started, you must disable the source and destination check.

    ![Disable the source and destination check.](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/7752240061/p139751.png)


## Step 3: Configure the networks of the SAG vCPE device

After you deploy the SAG vCPE image, the AWS SAG vCPE instance functions as a virtual CPE device to provide services. To allow the AWS SAG vCPE instance to access Alibaba Cloud services, you must configure the networks of the instance in the SAG console.

1.  Select a method to advertise routes to Alibaba Cloud.

    1.  Log on to the [SAG console](https://smartag.console.aliyun.com).

    2.  In the top navigation bar, select the region where the SAG vCPE instance is deployed.

    3.  On the **Smart Access Gateway** page, find the instance and click **Network Configuration** in the **Actions** column.

    4.  On the **Method to Synchronize with On-premises Routes** page, click **Add Static Route**.

    5.  Enter the private CIDR block of your AWS service and click **OK**.

        ![The Method to Synchronize with On-premises Routes page](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/5752240061/p139262.png)

2.  Associate the SAG vCPE instance with a CCN instance.

    Cloud Connect Network \(CCN\) is an important component of SAG. SAG connects your private networks to Alibaba Cloud through CCN. For more information, see [Introduction to CCN](/intl.en-US/Configuration Guide/Cloud Connect Network/Introduction to CCN.md).

    If you have not created a CCN instance, create a CCN instance before you perform the following steps. For more information about how to create a CCN instance, see [Create a CCN instance](/intl.en-US/Configuration Guide/Cloud Connect Network/Create a CCN instance.md).

    1.  On the **Smart Access Gateway** page, find the instance and click **Network Configuration** in the **Actions** column.

    2.  Click **Network Instance Details**.

    3.  Click **Attach Network**, select the CCN instance you want to associate, and then click **OK**.

    4.  After the CCN instance is associated with the SAG vCPE instance, the VPN Status and Control Status change to Normal on the **Device Management** tab.

        ![VPN Status and Control Status](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/5752240061/p139110.png)

3.  Configure the CEN instance.

    Cloud Enterprise Network \(CEN\) allows the SAG vCPE instance to communicate with the resources deployed in your Alibaba Cloud VPC networks. For more information about CEN, see [What is Cloud Enterprise Network]().

    You must perform the following steps to associate the SAG vCPE instance and the created Alibaba Cloud VPC network with a CEN instance. Then, the routes of the SAG vCPE instance and the VPC network can be advertised to each other.

    1.  In the left-side navigation pane, click **CCN**.

    2.  On the **CCN** page, find the CCN instance and click **Bind CEN Instance** in the **Actions** column.

    3.  In the Bind CEN Instance pane, select the CEN instance you want to associate and click **OK**.

        You can use one of the following methods to select the CEN instance. **Create CEN** is selected in this example.

        -   **Existing CEN**: If you have already created a CEN instance, you can select an existing CEN instance from the drop-down list.
        -   **Create CEN**: If you have not created a CEN instance, enter an instance name. The system then creates a CEN instance and automatically associates it with the CCN instance.

            The name must be 2 to 100 characters in length, and can contain digits, underscores \(\_\), and hyphens \(-\). It must start with a letter or a Chinese character.

    4.  Associate the Alibaba Cloud VPC network with the CEN instance. For more information, see [Attach networks]().

    5.  After the VPC network is associated with the CEN instance, you must configure the security group of the Elastic Compute Service \(ECS\) instance that is deployed in the VPC network. You must allow the private CIDR block of the AWS instance to access the resources deployed in the VPC network. For more information, see [Add security group rules](/intl.en-US/Security/Security groups/Add security group rules.md).

        ![Security group settings](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/6752240061/p139292.png)


## Step 4: Configure the AWS instance

To implement interconnections between AWS and Alibaba Cloud, you must configure the AWS instance. For more information about how to configure the AWS instance, consult your service provider.

1.  Log on to the AWS instance.

2.  Configure routes for the AWS instance.

    Map the next hop of the Alibaba Cloud CIDR block to the SAG vCPE instance that is deployed in the AWS VPC network. This establishes network communication between cloud resources deployed on Alibaba Cloud and AWS.

    ![Configure routes for the AWS instance](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/8752240061/p147915.png)

3.  Configure a security group rule for the AWS instance.

    Allow the private CIDR block of Alibaba Cloud to access AWS services.

4.  After you configure the routes, use the private IP address of the AWS instance as the source IP address and run the `ping` command to test the connectivity between Alibaba Cloud and AWS.


