# SAG-100WM {#concept_sr2_j3s_j2b .concept}

SAG-100WM devices are suitable for connecting small branches and outlets to Alibaba Cloud through inline mode.

## Specifications {#section_py4_b3l_qgb .section}

|Property|SAG-100WM|
|:-------|:--------|
|Operating environment|Indoor environment \(no fan provided\)|
|Operating temperature|0℃–45℃|
|Storage temperature|-40℃–70℃|
|Power|12 V DC|
|Power consumption|12 W|
|Network interface|Two GE/FE RJ45 WAN ports|
|Three GE/FE RJ45 LAN ports|
|Wi-Fi|IEEE 802.11 b/g/n, 2.4 G 150 Mbps, 20 terminals, 100m2 coverage|
|4G LTE \(Mainland China\)|LTE FDD: B1, B3, B5, B8|
|LTE TDD: B38, B39, B40, B41|
|WCDMA: B1, B5, B8|
|TD SCDMA: B34, B39|
|GSM: B3, B8|
|CDMA EVDO/1X: 800M|
|4G LTE \(Outside China\)|LTE FDD: B1, B3, B5, B8|
|WCDMA: B1, B5, B8|
|GSM: B3, B8|
|USB|USB 2.0, 500ma|

## Accessories {#section_lnq_l3l_qgb .section}

After receiving the Smart Access Gateway device, check that the following items are provided:

-   A Smart Access Gateway device
-   A power cable

**Note:** If any item is missing or damaged, contact Alibaba Cloud after-sales personnel.

## Front panel {#section_gpl_g3l_qgb .section}

The following is an overview about a Smart Access Gateway device of the Type 1 category. \(Types 2, although different in appearance, possess the same functions as Type 1 devices.\)

-   Front panel: There are five LED indicators on the front panel.

    |LED indicator|Description|
    |-------------|-----------|
    |LTE|Indicates whether the device communication is normal:     -   Flickering: Data transmission is normal.
    -   Off: No card is inserted.
 |
    |WAN|Indicates the Ethernet status of the device:     -   On: The device is connected to the Ethernet.
    -   Flickering: Data transmission is normal.
    -   Off: The device is not connected to the Ethernet.
 |
    |WIFI|Indicates the WIFI connection status of the device:     -   On: The WLAN is enabled.
    -   Flickering: Data transmission is normal.
    -   Off: The WLAN is not enabled.
 |
    |RUN|Indicates the status of the Smart Access Gateway device:     -   On: The device is powered on.
    -   Flickering: Data transmission is normal.
    -   Off: The device is not powered on.
 |
    |CLOUD|Indicates whether the device is connected to Alibaba Cloud:     -   On: The device is connected to the CEN.
    -   Off: The device is not connected to the CEN.
 |

-   Rear panel: There is one reset button, one SIM slot, one USB port, two WAN ports, three LAN ports, and a power interface on the rear panel of Smart Access Gateway:
    -   RESET button

        To restore the Smart Access Gateway to its default configurations, press and hold the reset button for five seconds while the device is powered on.

        The default administration IP address of the Smart Access Gateway device is 192.168.0.1.

    -   SIM slot

        Insert a SIM card into the slot.

    -   USB interface

        Currently, you cannot use a 4G USB to access the Internet.

    -   WAN port

        The WAN port is used for accessing the Internet. It supports SNAT forwarding, dynamic IP, static IP, and PPoE.

    -   LAN port

        LAN ports are used for connecting local clients and can be connected to the switch through configured routes.

    -   DC power socket

        The power interface is on the far right side of the panel. The power supply must be 12-V DC power supply.

        **Note:** We recommend that you use the original power cable.


## Networking mode {#section_iqp_vcn_qgb .section}

The SAG-100WM device connects local clients to Alibaba Cloud through inline mode. The network topology is unchanged for this device.

![](../DNsmartag1895345/../DNsmartag1836777/images/21205_en-US.png)

