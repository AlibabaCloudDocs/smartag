# ping不通同CEN的ECS或同CCN的PC {#trouble_ddb_ygb_4fb .troubleshooting}

## 故障现象 { .condition}

终端无法连接到阿里云，例如ping不通同CEN的ECS或同CCN的PC。

## 可能原因 { .cause}

-   终端到设备的链路故障。
-   设备到阿里云的VPN链路故障。
-   目标ECS故障。
-   运营商网络故障。

1.  登录[智能接入网关控制台](https://smartag.console.aliyun.com/sag/cn-shanghai/sags)。 
2.  单击智能接入网关实例ID，查看设备状态是否为**在线**。 
    -   如果离线，请参考[设备显示离线](cn.zh-CN/故障处理/设备和云的连通性故障（SAG-100WM）/设备显示离线.md#)处理。
    -   如果在线，请跳转至[3](#step3)。
3.  请观察设备的cloud LED灯是否点亮。 
    -   如果cloud的LED灯是亮的，表示设备和阿里云VPN隧道是正常的，登录云服务器控ECS制台，查看VPC中ECS实例的安全组规则，流量是否放行。
    -   如果cloud LED灯是暗的，表示设备和阿里云VPN隧道未正常建立，请跳转至[4](#step4).
4.  可能是设备内部软件问题， 可以尝试重启盒子进行恢复或提交工单处理。 

