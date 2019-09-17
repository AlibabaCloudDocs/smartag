# Purchase an SAG device and an ECC link {#task_1681229 .task}

This topic describes how to purchase a Smart Access Gateway \(SAG\) device and an Express Cloud Connect \(ECC\) link in the Express Connect console. You can use the ECC link to connect to Alibaba Cloud.

Only SAG-1000 devices support ECC links.

1.  Log on to the [Express Connect console](https://expressconnect.console.aliyun.com).
2.  In the left-side navigation pane, choose **Physical Connections**\>**Express Cloud Connect**.
3.  On the Express Cloud Connect page, click **Apply for Express Cloud Connect**. 

    ![Apply for Express Cloud Connect](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1332542/156871446055384_en-US.png)

4.  In the Apply for Express Cloud Connect dialog box, configure the ECC instance and then click **OK**. 

    ![Apply for ECC](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1332542/156871446055388_en-US.png)

    Configure the ECC instance according to the following information:

    |Configuration|Description|
    |-------------|-----------|
    |IDC Address|Enter the detailed location of the on-premises data center that needs to connect to Alibaba Cloud, including which room the on-premises data center is.|
    |IDC Service Provider|Select the service provider of the on-premises data center. You can contact customer service of the on-premises data center to obtain such information.|
    |IDC Port Type|Select the type of the port to which the leased line will be connected at the on-premises data center.|
    |Bandwidth|Set the bandwidth of the ECC link, which is also the bandwidth of the leased line.|

5.  Alibaba Cloud reviews the ECC application based on available resources and determines whether the application should be approved. If the application is approved, the application status of the ECC instance changes to **Approved**. Click **Pay** in the **Actions** column. 

    ![Pay](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1332542/156871446055389_en-US.png)

6.  In the ECC section, configure the ECC link. In the **SAG Device** section, set the SAG device quantity. Click **Buy Now**.
7.  On the Confirm Order page, click **Confirm Purchase**.
8.  In the Address dialog box, enter the shipping address and other required information, and click **Order Now**.
9.  On the Pay page, click **Pay**. After the payment is completed, the application status of the ECC instance changes to **In Construction**. After the leased line provider completes the installation, the ECC instance enters the **Completed** state. At this stage, the ECC instance is available for use.

**More information**  


[Add an Internet link](../../../../reseller.en-US/Smart Access Gateway/Configuration Guide/SAG instance management/Add an Internet link.md#)

