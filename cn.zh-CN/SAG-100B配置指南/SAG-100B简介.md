# SAG-100B简介 {#concept_amd_jxb_pfb .concept}

智能接入网关SAG-100B设备适用于小型分支接入阿里云，即插即用。SAG-100B支持SNAT转发、动态IP、静态IP和PPPoE配置。

## 网关设备规格 {#section_gdf_25s_j2b .section}

|属性|SAG-100B规格|
|:-|:---------|
|产品外壳|塑料外壳，白色|
|机构尺寸|W≤215mm, D≤180mm, H≤44mm|
|工作环境|室内环境|
|工作温度|-5°C — 40°C|
|输入电压|DC 12V|
|功耗|<10W|
|WAN口数量|1 RJ45|
|LAN口数量|4 RJ45|
|LTE支持|否|
|安装方式|放装式|

## 网关设备配件 {#section_j5t_k5s_j2b .section}

在收到智能接入网关设备后，请检查以下配件是否完备：

-   一台智能接入网关设备
-   一根电源线

**说明：** 如果发现有配件短缺或损坏的情况，请及时与阿里云售后联系。

## 前面板 {#section_q1k_2vs_j2b .section}

智能接入网关的前面板由电源开关、USB口、指示灯和Reset键组成：

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15408/15410820266810_zh-CN.jpg)

-   电源开关

    网关设备连接电源后，启动电源开关开启网关设备。

-   USB口

    支持接入USB连接公网。

-   RST键

    如果需要将智能接入网关恢复默认设置，请在通电的情况下，使用尖状物长按RST键5秒后，将网关设备恢复到默认配置。智能接入网关的默认管理地址是192.168.0.1。

-   指示灯

    指示灯包括PWR指示灯、系统状态灯和连接状态指示灯，如下表所示。

    |指示灯|状态说明|
    |:--|:---|
    |PWR（电源指示灯）|开机后常亮，表示系统供电正常。|
    |SYS（系统指示灯）|开机后常亮，表示系统运行正常。按RST（Rest键）后，该指示灯熄灭。

|


## 后面板 {#section_xmv_qvs_j2b .section}

智能接入网关的后面板由1个Console接口、1个WAN口、4个LAN口和电源接口组成：

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15408/15410820266811_zh-CN.png)

-   Console口

    Console接口位于面板最左边。

    **说明：** 请您不要连接Console口，该接口仅供阿里云运维调试使用。

-   WAN口

    WAN口用于连接公网（Internet），支持SNAT转发、动态IP、静态IP和PPPoE配置。

-   LAN口

    LAN口用于连接本地客户端，支持配置路由接入交换机。

-   电源接口

    电源接口位于面板最右边。接入电源需为12V直流电。

    **说明：** 请使用原装电源线。


## 组网 {#section_hzk_5yb_pfb .section}

SAG-100B设备支持小型分支或门店以直挂或旁挂方式接入阿里云。

![](images/21204_zh-CN.png "旁挂组网")

![](images/21205_zh-CN.png "直挂组网")

