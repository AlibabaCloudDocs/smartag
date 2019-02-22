# Cannot successfully ping an ECS instance in the same CEN or another PC in the same CCN {#trouble_j3z_yyf_4fb .troubleshooting}

## Symptoms: { .condition}

The terminal cannot be connected to Alibaba Cloud. For example, you cannot successfully ping an ECS instance in the same CEN or another PC in the same CCN.

## Causes: { .cause}

-   The link between the terminal and the device has failed.
-   The VPN link between the device and Alibaba Cloud has failed.
-   The target ECS instance has failed.
-   The network of the service provider has failed.

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com/sag/cn-shanghai/sags). 
2.  Click the ID of the target Smart Access Gateway instance and check if the status of the device is **Ready**. 
    -   If the device is offline, see [The device is offline](intl.en-US/Troubleshooting/Connectivity failure between the device and Alibaba Cloud (SAG-100WM)/The device is offline.md#) to troubleshoot.
    -   If the device is not offline, check if the device is in the **Ready** status. If not, check if the device is bound to a CCN or if it has expired. Otherwise proceed to [3](#step3).
3.  Check if the configurations of the device are as expected. 
    -   On the Smart Access Gateway console, check whether the private CIDR block of the device and the bound CCN are configured as expected.
    -   On the web configurations of the device, check if the WAN and LAN configurations of the device are as expected. If so, proceed to [4](#step4).
4.  The cause may be the internal software failure of the device. You can restart the device to see if the problem persists or open a ticket. 

