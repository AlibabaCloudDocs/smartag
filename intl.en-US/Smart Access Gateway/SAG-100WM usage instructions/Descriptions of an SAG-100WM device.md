# Descriptions of an SAG-100WM device

SAG-100WM devices are suitable for connecting small-scale private networks to Alibaba Cloud. This topic describes the specifications of an SAG-100WM device.

## Specifications

SAG-100WM provides two models of devices that have different specifications. The exterior and sizes of these two device models are different, but the supported features are the same. For more information about supported features, see [Features of Smart Access Gateway devices](/intl.en-US/Smart Access Gateway/Features of Smart Access Gateway devices.md).

-   **Model 1 size: 180 mm × 110 mm × 30 mm**
    -   **Front panel**

        ![](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/8328673061/p21278.png)

    -   **I/O panel**

        ![](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/40483/156571220321279_en-US.png)

-   **Model 2 size: 240 mm × 148 mm × 28 mm**
    -   **Front panel**

        ![](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9328673061/p66684.png)

    -   **Side panel**

        ![](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9328673061/p66686.png)

    -   **I/O panel**

        ![](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9328673061/p66687.png)


|Property|SAG-100WM specification|
|Model 1|Model 2|
|:-------|:----------------------|
|:------|:------|
|Performance \(tested in 512 bytes\)|The encrypted bandwidth for private connections can reach 50 Mbit/s|The encrypted bandwidth for private connections can reach 50 Mbit/s|
|Working environments|Suitable for indoor environments with no fan attached|Suitable for indoor environments with no fan attached|
|Size|180 mm\*110 mm\*30 mm|240 mm\*148 mm\*28 mm|
|Working temperature|0℃ to 45℃|0℃ to 45℃|
|Storage temperature|-40℃ to 70℃|-20℃ to 70℃|
|The power indicator|DC 12V|DC 12 V|
|Power consumption|12 W|12 W|
|Network interfaces|Two GE/FE RJ45 WAN ports|One GE/FE RJ45 WAN ports|
|Three GE/FE RJ45 LAN ports|One WAN/LAN reusable port \(port 2\)|
|Three GE/FE RJ45 LAN ports|
|WIFI|-   2.4 GHz and supports IEEE 802.11 b/g/n
-   Supports at most 20 terminals
-   Signal covers 100 square meters

|-   2.4 GHz and supports IEEE 802.11 b/g/n
-   Supports at most 20 terminals
-   Signal covers 100 square meters |
|4G LTE in mainland China|4G|4G|
|USB|USB 2.0|USB 2.0|

## Device panels

The following tables describe the device panels. "√" indicates "supported" while "×" indicates "not supported".

-   **Front panel**: consists of five LED indicators, as described below:

    |LED indicator|Description|SAG-100WM specification|
|Model 1|Model 2|
    |-------------|-----------|-----------------------|
    |-------|-------|
    |LTE|Indicates the communication status of the device:     -   On or off: abnormal communication.
    -   Blinking: device communicating as expected.
|√|√|
    |WAN|Indicates the Ethernet usage status:     -   On or off: abnormal Ethernet connection.
    -   Blinking: transferring data over the Ethernet.
|√|×|
    |WIFI|Indicates the Wi-Fi connection status:     -   On or off: abnormal Wi-Fi connection.
    -   Blinking: transferring data over Wi-Fi.
|√|√|
    |RUN/SYS|Indicates the power status:     -   On or off: system not working as expected.
    -   Blinking: system working as expected.
|√|√|
    |CLOUD|Indicates whether the device is connected to Alibaba Cloud:     -   On: connected to Alibaba Cloud.
    -   Blinking: restoring the system or restoring to default settings.
    -   Off: not connected to Alibaba Cloud.
|√|√|
    |PWR|Indicates whether the device is powered on:    -   On: device powered on.
    -   Off: device not powered on.
|×|√|
    |Descriptions of status indicators|
    |RJ45 yellow light|Indicates the connection status and speed of the network interface controller \(NIC\):    -   On: Ethernet port working in 1000Base-T mode.
    -   Off: Ethernet port working in 10/100Base-T mode.
|√|√|
    |RJ45 green light|Indicates the connection status and speed of the NIC:    -   On: Ethernet connected.
    -   Blinking: transferring data.
    -   Off: Ethernet not connected.
|√|√|

-   **I/O panel**: consists of one reset button, one SIM slot, one USB port, two WAN ports, three LAN ports, and one power inlet.

    **Note:** The sim card slot of a model 2 device is on the side of the device.

    -   The reset button

        To restore the device to default settings, keep the device powered on, and press and hold the reset button with a pointy object for three seconds. Then, the device is automatically restarted and restored to default settings.

    -   The SIM card slot

        You can only directly insert a Mini-SIM card into the slot. A Micro-SIM or Nano-SIM card cannot be directly inserted into the slot. If you need to use a Micro-SIM or Nano-SIM card, you must use a card frame instead of a card sleeve. The card may be stuck in the slot if you use a card sleeve.

        SAG-100WM devices support Mini-SIM, Micro-SIM, and Nano-SIM cards. You must use a card frame if you want to use a Micro-SIM or Nano-SIM card.

        Mini-SIM, Micro-SIM, and Nano-SIM cards are known as 2FF, 3FF, and 4FF cards, as shown in the following figure.

        ![](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/3222341061/p52693.png)

    -   The USB port

        Currently, 4G USB is not supported to access the Internet.

    -   The WAN ports

        The WAN ports support Internet access, Source Network Address Translation \(SNAT\), dynamic IP addresses, static IP addresses, and PPPoE.

    -   The LAN ports

        The LAN ports can be connected to local clients and allow you to configure routes that connect the device to a switch.

    -   WAN/LAN reusable port

        The WAN/LAN reusable port can be used as a WAN port or a LAN port.

        **Note:**

        -   If your SAG-100WM device runs in version 1.0.x, the WAN/LAN reusable port functions as a LAN port by default.
        -   If your SAG-100WM device runs in version 2.0.x, the WAN/LAN reusable port functions as a WAN port by default.
    -   The DC power inlet

        The power inlet is at the I/O panel. The power supply must be 12 V direct current.

        **Note:** Use the original power cord.


## Device accessories

The SAG-100WM device package contains the following items:

-   One SAG-100WM device
-   One power cord

**Note:** If an item is missing or damaged, contact Alibaba Cloud after-sales service. The SAG-100WM device is delivered randomly from one of the two models.

