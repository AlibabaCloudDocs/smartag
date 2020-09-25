# SAG vCPE介绍

智能接入网关（SAG）vCPE是智能接入网关软件镜像版，通过将SAG vCPE镜像部署在您网络的服务器中，使服务器作为一个虚拟CPE设备为您提供上云服务，突破了物理的限制，更加灵活的帮您将网络接入阿里云。

## 部署说明

SAG vCPE支持部署在阿里云边缘节点服务ENS（Edge Node Service）实例中，也支持部署在亚马逊云计算服务AWS（Amazon Web Services）平台的云服务器中。部署后，您可以通过SAG控制台管理SAG vCPE设备并对其进行网络配置，将您的网络接入阿里云。

**说明：** 在中国内地以外区域，SAG vCPE目前只支持部署在AWS云服务器中。

![VCPE部署流程](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/5713129951/p143452.png)

部署流程如下所示：

![vCPE流程](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/5713129951/p143457.png)

1.  购买SAG vCPE设备。

    您在SAG管理控制台购买SAG vCPE设备后，系统会为您生成一个SAG vCPE类型的实例帮您管理部署了SAG vCPE镜像的设备，并且每台SAG vCPE设备会被分配一个序列号和密钥，用于后续将实例和SAG vCPE设备进行绑定。

2.  部署SAG vCPE镜像。

    在您为服务器安装镜像时，需要将SAG vCPE设备的序列号和密钥写入到镜像中，用于实例和设备的绑定，并且云端会进行设备安全性校验，如果序列号和密钥校验不成功，则不允许SAG vCPE设备上线，提高您设备和网络的安全性。

3.  配置SAG vCPE设备。

    SAG vCPE镜像部署成功后，您需要在SAG管理控制台为设备配置线下路由同步方式并将设备绑定到云连接网，将SAG vCPE设备接入阿里云。

4.  业务端网络配置。

    在业务端进行路由等网络配置，引导流量进入SAG vCPE设备，进而接入阿里云。


SAG vCPE镜像部署在不同平台的服务器中时，其详细部署流程会有所差异，详情您可参见[SAG vCPE部署教程](/cn.zh-CN/VCPE手册/SAG vCPE部署教程/SAG vCPE联合ENS上云.md)。

## 实例规格说明

SAG vCPE支持部署的实例规格及其性能说明如下表所示：

|规格|ENS|AWS|
|--|---|---|
|1核vCPU，2 GB内存|加密私网带宽可达200 Mbps以上（1024字节）|加密私网带宽可达200 Mbps以上（1024字节）|
|2核vCPU，4 GB内存|加密私网带宽可达350 Mbps以上（1024字节）|加密私网带宽可达350 Mbps以上（1024字节）|

