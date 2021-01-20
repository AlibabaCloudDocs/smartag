# Descriptions of SAG-100WM

SAG-100WM devices are suitable for connecting small-scale private networks to Alibaba Cloud. This topic describes the specifications of the SAG-100WM device model.

## Specifications

SAG-100WM provides two device types that have different specifications. The exterior and sizes of these two device types are different, but the supported features are the same. For more information, see [Features of Smart Access Gateway devices](/intl.en-US/Smart Access Gateway/Features of Smart Access Gateway devices.md).

-   **Type 1 Size: 180 mm × 110 mm × 30 mm**
    -   **Front panel**

        ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8328673061/p21278.png)

    -   **I/O panel**

        ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/40483/156571220321279_en-US.png)

-   **Type 2 Size: 240 mm × 148 mm × 28 mm**
    -   **Front panel**

        ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9328673061/p66684.png)

    -   **Side panel**

        ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9328673061/p66686.png)

    -   **I/O panel**

        ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9328673061/p66687.png)


|Property|SAG-100WM specification|
|Type 1|Type 2|
|:-------|:----------------------|
|:-----|:-----|
|Performance \(tested in 512 bytes\)|The bandwidth for encrypted private connections can reach 50 Mbit/s|The bandwidth for encrypted private connections can reach 50 Mbit/s|
|Working environments|Suitable for indoor environments with no fans attached|Suitable for indoor environments with no fans attached|
|Size|180 mm\*110 mm\*30 mm|240 mm\*148 mm\*28 mm|
|Working temperature|0℃ to 45℃|0℃ to 45℃|
|Storage temperature|-40℃ to 70℃|-20℃ to 70℃|
|Power LED indicator light|DC 12 V|DC 12 V|
|Power consumption|12 W|12 W|
|Network ports|Two GE/FE RJ45 WAN ports**Note:** One of the WAN ports is in bridge mode. Therefore, only one WAN port is available.

|One GE/FE RJ45 WAN port|
|Three GE/FE RJ45 WAN ports|One WAN/LAN reusable port \(port 2\)|
|Three GE/FE RJ45 WAN ports|
|WIFI|-   2.4 GHz and supports IEEE 802.11 b/g/n
-   Supports at most 20 terminals
-   Signal covers 100 square meters

|-   2.4 GHz and supports IEEE 802.11 b/g/n
-   Supports at most 20 terminals
-   Signal covers 100 square meters |
|4G LTE in mainland China|4G network provided by China Unicom, China Telecom, and China Mobile|4G network provided by China Unicom, China Telecom, and China Mobile|
|USB|USB 2.0|USB 2.0|

## Device panels

The following tables describe the device panels. "√" indicates "supported" while "×" indicates "not supported".

-   **Front panel**: provides five LED indicator lights, as described in the following table.

    |LED indicator light|Description|SAG-100WM specification|
|Type 1|Type 2|
    |-------------------|-----------|-----------------------|
    |------|------|
    |LTE|Indicates the connection status of the device:     -   On or off: an error occurred.
    -   Flashing: working as expected.
|√|√|
    |WAN|Indicates the Ethernet status:     -   On or off: an error occurred.
    -   Flashing: working as expected.
|√|×|
    |WIFI|Indicates the Wi-Fi connection status:     -   On or off: an error occurred.
    -   Flashing: working as expected.
|√|√|
    |RUN/SYS|Indicates the power status:     -   On or off: an error occurred.
    -   Flashing: system working as expected.
|√|√|
    |CLOUD|Indicates whether the device is connected to Alibaba Cloud:     -   On: connected to Cloud Connect Network \(CCN\).
    -   Flashing: restoring the system or restoring to default settings.
    -   Off: not connected to CCN.
|√|√|
    |PWR|Indicates whether the device is powered on:    -   On: powered on.
    -   Off: not powered on.
|×|√|
    |Descriptions of status indicator lights|
    |RJ45 yellow light|Indicates the working mode of the network interface controller \(NIC\):    -   On: Ethernet port working in 1000Base-T mode.
    -   Off: Ethernet port working in 10/100Base-T mode.
|√|√|
    |RJ45 green light|Indicates the connection status and speed of the NIC:    -   On: Ethernet connected.
    -   Flashing: transferring data.
    -   Off: Ethernet not connected.
|√|√|

-   **I/O panel**: provides one reset button, one subscriber identity module \(SIM\) slot, one USB port, two WAN ports, three LAN ports, and one power inlet.

    **Note:** The SIM card slot of a Type 2 device is on the side of the device.

    -   The reset button

        To restore the device to the default settings, keep the device powered on, and press and hold the reset button for three seconds. Then, the device is automatically restarted and restored to the default settings.

    -   The SIM card slot

        You can directly insert only a Mini-SIM card into the slot. A Micro-SIM or Nano-SIM card cannot be directly inserted into the slot. If you need to use a Micro-SIM or Nano-SIM card, you must use a card frame adapter instead of a card sleeve adapter. The card may be stuck in the slot if you use a card sleeve adapter.

        SAG-100WM devices support Mini-SIM, Micro-SIM, and Nano-SIM cards. You must use a card frame adapter if you want to use a Micro-SIM or Nano-SIM card.

        Mini-SIM, Micro-SIM, and Nano-SIM cards are known as 2FF, 3FF, and 4FF cards, as shown in the following figure.

        ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3222341061/p52693.png)

    -   The USB port

        4G USB is not supported for access to the Internet.

    -   The WAN ports

        The WAN ports support Internet access, Source Network Address Translation \(SNAT\), dynamic IP addresses, static IP addresses, and Point-to-Point Protocol over Ethernet \(PPPoE\).

    -   The LAN ports

        The LAN ports can be connected to on-premises clients and allow you to configure routes that connect the device to switches.

    -   WAN or LAN reusable port

        The WAN or LAN reusable port can be used as a WAN port or a LAN port.

        **Note:**

        -   If the version of your SAG-100WM device is 1.0.x, the WAN or LAN reusable port functions as a LAN port by default.
        -   If the version of your SAG-100WM device is 2.0.x, the WAN or LAN reusable port functions as a WAN port by default.
    -   The DC power inlet

        The power inlet is on the I/O panel. The power supply must be 12V DC.

        **Note:** Use the original power cord.


## Device accessories

After you purchase an SAG device in the SAG console, you will receive an SAG-100WM device and a power cord.

**Note:** Check the SAG-100WM device and its accessories. If an accessory is missing or damaged, contact Alibaba Cloud after-sales service. The SAG-100WM device is selected randomly from one of the two types.

