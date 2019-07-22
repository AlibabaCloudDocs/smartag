# Configure the network {#task_i33_cbk_wgb .task}

Before you can run a Smart Access Gateway \(SAG\) APP, you need to configure the network of the target instance.

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com/sag/cn-shanghai/sags).
2.  On the Smart Access Gateway APP page, find the target instance and click **Configure Network** in the **Actions** column.
3.  Configure the network according to the configuration items described in the following table. 

    |Configuration|Description|
    |-------------|-----------|
    |**CCN Instance ID/Name**|Select the CCN instance to attach. You can use the default CCN instance or a created CCN instance. CCN is a device access matrix composed of Alibaba Cloud distributed access gateways. After an SAG device is attached to a CCN instance, the SAG device can communicate with other gateway devices attached to the CCN instance.

 **Note:** Make sure that the CCN instance and the SAG instance are in the same region.

 |
    |**Private CIDR Block**| Configure the private CIDR blocks used by the mobile client. Then, the client uses IP addresses allocated from the private CIDR blocks to access Alibaba Cloud. The private CIDR blocks must belong to the private CIDR block of the CCN instance. Make sure all private CIDR blocks do not conflict with one another.

 Click **Add Private CIDR Block** to add more CIDR blocks. Up to five CIDR blocks can be added.

 |

4.  Click **OK**.

