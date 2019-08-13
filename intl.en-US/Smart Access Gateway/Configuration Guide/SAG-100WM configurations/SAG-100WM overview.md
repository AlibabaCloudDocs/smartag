# SAG-100WM overview {#concept_l2l_yb2_qfb .concept}

The SAG-100WM device is designed to connect small branches and outlets to Alibaba Cloud. As a plug-and-play device, SAG-100WM does not require Web configuration.

## Specifications {#section_gdf_25s_j2b .section}

|Property|SAG-100WM Specification|
|:-------|:----------------------|
|Operating environment|Indoor environment \(no fan provided\)|
|Operating temperature|0℃–45℃|
|Storage temperature|-40℃–70℃|
|Power supply|12 V DC|
|Power consumption|12 W|
|Network interface|Two GE/FE RJ45 WAN ports|
|Three GE/FE RJ45 LAN ports|
|Wi-Fi|IEEE 802.11 b/g/n, 2.4 G 300 Mbps, 20 terminals, 100 m2 coverage|
|4G LTE \(Mainland China\)|LTE FDD: B1, B3, B5, and B8|
|LTE TDD: B38, B39, B40, and B41|
|WCDMA: B1, B5, and B8|
|TD SCDMA: B34 and B39|
|GSM: B3 and B8|
|CDMA EVDO/1X: 800M|
|4G LTE \(Outside Mainland China\)|LTE FDD: B1, B3, B5, and B8|
|WCDMA: B1, B5, and B8|
|GSM: B3 and B8|
|USB|USB 2.0, 500 mA|

## SAG components {#section_j5t_k5s_j2b .section}

The Smart Access Gateway \(SAG\) device is shipped with the following components:

-   An SAG device
-   A power cable

**Note:** If any component is missing or damaged, contact Alibaba Cloud after-sales personnel. Two types of SAG-100WM devices are available.

## Type 1 \(dimensions: 180 mm × 110 mm × 30 mm\) {#section_izy_yzz_xgb .section}

-   Front panel

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/40483/156571220121278_en-US.png)

-   Rear panel

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/40483/156571220121279_en-US.png)


## Type 2 \(dimensions: 275 mm × 175 mm × 44.4 mm\) {#section_lqn_c11_ygb .section}

-   Front panel

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/40483/156571220239754_en-US.png)

-   Side panel

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/40483/156571220239755_en-US.png)

-   Rear panel

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/40483/156571220239756_en-US.png)


## Front panel and rear panel {#section_q1k_2vs_j2b .section}

The front panel and the rear panel of a Type 1 SAG-100WM device are described as follows:

-   Front panel: There are five LED indicators on the front panel.

    |LED indicator|Description|
    |-------------|-----------|
    |LTE|Indicates whether the device communication is normal.     -   Flashing: Data is being transmitted.
    -   Off: No card is inserted.
 |
    |WAN|Indicates the Ethernet status of the device.     -   On: The device is connected to the Ethernet.
    -   Flashing: Data is being transmitted.
    -   Off: The device is not connected to the Ethernet.
 |
    |Wi-Fi|Indicates the Wi-Fi connection status of the device.     -   On: The WLAN is enabled.
    -   Flashing: Data is being transmitted.
    -   Off: The WLAN is disabled.
 |
    |RUN|Indicates the status of the SAG device.     -   On: The device is powered on.
    -   Flashing: Data is being transmitted.
    -   Off: The device is powered off.
 |
    |CLOUD|Indicates whether the device is connected to Alibaba Cloud.     -   On: The device is connected to the CEN.
    -   Off: The device is not connected to the CEN.
 |

-   Rear panel: There is one RESET button, one SIM slot, one USB port, two WAN ports, three LAN ports, and a power interface on the rear panel of the SAG device.
    -   RESET button

        To restore the SAG device to its default settings, press and hold the RESET button for five seconds when the device is powered on.

        The default administration IP address of the SAG device is 192.168.0.1.

    -   SIM card slot

        A SIM card is inserted into the slot. Only Mini-SIM cards, Micro-SIM cards, and Nano-SIM cards are supported. If you use a Micro-SIM or Nano-SIM card, we recommend that you use a card frame rather than a card sleeve. Otherwise, it may be difficult to pull out the card.

        The SAG device is equipped with a SIM card frame that matches Mini-SIM, Micro-SIM, and Nano-SIM cards. You can use the card frame if you want to change the SIM card.

        Mini-SIM cards, Micro-SIM cards, and Nano-SIM cards are also called 2FF cards, 3FF cards, and 4FF cards respectively.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/40483/156571220252693_en-US.png)

    -   USB interface

        Access to the Internet by using the 4G USB interface is not supported.

    -   WAN ports

        The WAN ports are used to access the Internet. These ports support SNAT forwarding, dynamic IP addresses, static IP addresses, and PPPoE.

    -   LAN ports

        The LAN ports are used to connect local clients and can be connected to the switch by configuring routes.

    -   DC power interface

        The power interface is on the rightmost of the panel. The power supply must be 12 V DC.

        **Note:** We recommend that you use the original power cable.


## Networking mode {#section_ltr_jf3_pfb .section}

The SAG-100WM device connects local clients to Alibaba Cloud through inline mode, which means that the network topology is unchanged.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/24578/156571220221205_en-US.png)

