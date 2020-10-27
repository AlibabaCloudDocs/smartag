# Descriptions of an SAG-1000 device

You can use SAG-1000 devices to connect large-scale networks, such as headquarters, to Alibaba Cloud. You can deploy an SAG-1000 device in one-arm mode to avoid network topology changes.

## Specifications

|Property|Specification|
|:-------|:------------|
|CPU|Intel Atom® Processor C3558|
|Device shell|Metal or aluminum alloy, frosted black, available to be installed on a server rack in an on-premises data center.|
|Size|1 U, halfwidth|
|Working environment|Indoor environment|
|Working temperature|0℃ to 45℃|
|Storage temperature|-40℃ to 70℃|
|Power|DC 12 V \(power adapter and power cord included\)|
|Power consumption|< 60 W|
|Network ports|Two reusable ports|
|Four RJ45 copper ports|

## Accessories

After you receive an SAG-1000 device, check whether you have received all the following items:

-   The SAG-1000 device
-   One power cord

**Note:** If an item is missing or damaged, contact Alibaba Cloud after-sales service. The SAG-1000 device is delivered randomly from one of the two manufacturers.

## Control panel overview

**Front panel**: consists of four LED indicators:

![1000 A](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/6449673061/p84919.png)

-   LTE: indicates the communication status of the device.
-   CLOUD: indicates whether the device is connected to Alibaba Cloud.
-   SYS: indicates the system status.
-   PWR: indicates the power status.

**I/O panel**: consists of one reset button, one SIM slot, two USB ports, two reusable ports, four copper ports, and one power inlet.

![I/O panel](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/6449673061/p82425.png)

-   The reset button

    To restore the SAG-1000 device to its default settings, keep the device powered on, and press and hold the reset button with a pointy object for five seconds. Then, the device is automatically restarted and restored to default settings.

-   The SIM card slot

    You can only directly insert a Mini-SIM card into the slot. A Micro-SIM or Nano-SIM card cannot be directly inserted into the slot. If you need to use a Micro-SIM or Nano-SIM card, you must use a card frame instead of a card sleeve. The card may be stuck in the slot if you use a card sleeve.

    SAG-1000 devices support Mini-SIM, Micro-SIM, and Nano-SIM cards. You must use card frames if you want to use a Micro-SIM or Nano-SIM card.

    Mini-SIM, Micro-SIM, and Nano-SIM cards are known as 2FF, 3FF, and 4FF cards, as shown in the following figure.

    ![](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/3222341061/p52693.png)

-   The USB port

    Currently, 4G USB is not supported to access the Internet.

-   The reusable ports

    One reusable port provides two ports: one copper port and one fiber port. You can only use one of the two ports. If you have used the copper port, you cannot use the fiber port. If you have used the fiber port, you cannot use the copper port.

    -   If both ports are used, the one enabled first is the only active port.
    -   If both ports are connected, by default, the fiber port has the priority to be active when the SAG-1000 device is powered on for the first time.
-   WAN and LAN ports:
    -   The WAN ports

        The WAN ports support Internet access, Source Network Address Translation \(SNAT\), dynamic IP addresses, static IP addresses, and PPPoE.

    -   The LAN ports

        The LAN ports can be connected to on-premises clients and allow you to configure dynamic routes that connect the device to a switch.

-   The DC power inlet

    The DC power inlet is on the rightmost side of the panel. The power supply must be 12 V direct current.

    **Note:** Use the original power cord.


## Descriptions of LED indicator states

The LED indicator states of an SAG-1000 device are described in the following table.

|LED indicator|Shard status|
|-------------|------------|
|LTE|Indicates the communication status of the device: -   On or off: abnormal communication.
-   Blinking: device communicating as expected. |
|Signal indicator|The number of bars indicates the strength of the 4G LTE signal. Three bars indicate the strongest signal.|
|SYS|Indicates the system status: -   On or off: system not working as expected.
-   Blinking: system working as expected. |
|CLOUD|Indicates whether the device is connected to Alibaba Cloud: -   On: connected to Alibaba Cloud.
-   Blinking: restoring the system or restoring to default settings.
-   Off: not connected to Alibaba Cloud. |
|PWR|Indicates whether the device is powered on. On: device powered on. Off: device powered off.|
|RJ45 yellow light|Indicates the connection status and speed of the network interface controller \(NIC\): -   On: Ethernet port working in 1000Base-T mode.
-   Off: Ethernet port working in 10/100Base-T mode. |
|RJ45 green light|Indicates the connection status and speed of the NIC: -   On: Ethernet connected.
-   Blinking: transferring data.
-   Off: Ethernet not connected. |
|Some SAG devices use the following indicators:|
|![The power indicator](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/6449673061/p127378.png)|Indicates whether the device is powered on. On: device powered on. Off: device powered off.|
|![The alert indicator](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/6449673061/p127379.png)|Indicates whether the device is working as expected: -   Green: device working as expected.
-   Yellow: device having faults. |
|![The cloud indicator](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/7449673061/p127380.png)|Indicates whether the device is connected to Alibaba Cloud: -   Green: device connected to Alibaba Cloud.
-   Yellow: device not connected to Alibaba Cloud. |

