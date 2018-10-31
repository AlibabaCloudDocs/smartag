# SAG-100WM {#concept_sr2_j3s_j2b .concept}

收到智能接入网关设备后，请您检查网关设备是否完好，并按照说明连接网关设备。

## 网关设备规格 {#section_gdf_25s_j2b .section}

|属性|SAG-100WM规格|
|:-|:----------|
|工作环境|室内环境，无风扇设计|
|工作温度|0℃～45℃|
|存储温度|-40℃～70℃|
|电源|DC 12V|
|功耗|12W|
|网络接口|2个GE/FE RJ45 WAN口1 RJ45|
|3个GE/FE RJ45 LAN口|
|WiFi|IEEE 802.11 b/g/n,2.4G 150Mbps,终端数 32，范围100m2|
|4G LTE\(中国大陆\)|LTE FDD:B1,B3,B5,B8|
|LTE TDD:B38,B39,B40,B41|
|WCDMA:B1,B5,B8|
|TD SCDMA:B34,B39|
|GSM:B3,B8|
|CDMA EVDO/1X:800M|
|4G LTE\(海外\)|LTE FDD:B1,B3,B5,B8|
|WCDMA:B1,B5,B8|
|GSM:B3,B8|
|USB|USB 2.0，500ma|

## 网关设备配件 {#section_j5t_k5s_j2b .section}

在收到智能接入网关设备后，请检查以下配件是否完备：

-   一台智能接入网关设备
-   一根电源线

**说明：** 如果发现有配件短缺或损坏的情况，请及时与阿里云售后联系。

## 前面板 {#section_q1k_2vs_j2b .section}

智能接入网关的前面板由5个LED指示灯组成，具体说明如下：

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/23473/154095839913716_zh-CN.png)

|指示灯|状态说明|
|---|----|
|LTE|表示设备通讯是否正常：-   闪烁：通讯正常
-   熄灭：禁用

|
|WAN|表示以太网使用状态：-   长亮：以太网已连接
-   闪烁：数据传输
-   熄灭：以太网未连接

|
|WIFI|表示WIFI连接状态：-   长亮：WLAN启动
-   闪烁：数据传输
-   熄灭：WLAN未启动

|
|RUN|表示智能接入网关设备状态：-   长亮：电源接通
-   闪烁：数据传输
-   熄灭：电源未开

|
|CLOUD|表示是否连接到阿里云：-   闪烁：连接到阿里云
-   熄灭：没有连接到阿里云

|

## 后面板 {#section_xmv_qvs_j2b .section}

智能接入网关的后面板由1个RESET键、一个SIM插入口、1个USB接口，2个WAN口、3个LAN口和电源接口组成：

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/23473/154095839913717_zh-CN.png)

-   RESET键

    如果需要将智能接入网关恢复默认设置，请在通电的情况下，使用尖状物常按RESET键2~5秒后，将网关设备恢复到默认配置。

    智能接入网关的默认管理地址是192.168.0.1。

-   SIM卡插入口

    内嵌SIM卡，不支持外置LTE，软件驱动未适配。

-   USB口

    支持接入4G USB连接公网。

-   WAN口

    WAN口用于连接公网（Internet），支持SNAT转发、动态IP、静态IP和PPoE配置。

-   LAN口

    LAN口用于连接本地客户端，支持配置路由接入交换机。

-   DC电源接口

    电源接口位于面板最右边。接入电源需为12V直流电。

    **说明：** 请使用原装电源线。


