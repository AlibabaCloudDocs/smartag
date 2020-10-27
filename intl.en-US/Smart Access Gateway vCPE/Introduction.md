# Introduction

Smart Access Gateway \(SAG\) vCPE is an image that can be deployed on your server. After you deploy the SAG vCPE image on your server, the server functions as a virtual customer-premise equipment \(CPE\) device. This allows you to connect private networks to Alibaba Cloud in a more flexible way.

## Deploy the SAG vCPE image

You can deploy the SAG vCPE image on an Alibaba Cloud Edge Node Service \(ENS\) instance or an Amazon Web Services \(AWS\) instance. After you deploy the SAG vCPE image, you can configure the SAG vCPE device in the SAG console and connect private networks to Alibaba Cloud.

**Note:** In regions outside mainland China, the SAG vCPE image can be deployed only in AWS instances.

![Procedure](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/5815280061/p143452.png)

The following procedure describes how to deploy the SAG vCPE image:

![Procedure](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/3535280061/p143457.png)

1.  Purchase an SAG vCPE device.

    After you purchase an SAG vCPE device, the system creates an SAG vCPE instance that allows you to manage the server where the SAG vCPE image is deployed. Each SAG vCPE device is assigned a serial number and key. You can use the serial number and key to associate the SAG vCPE device with the SAG vCPE instance.

2.  Deploy the SAG vCPE image.

    When you deploy the SAG vCPE image, you must provide the valid serial number and key of the SAG vCPE device to associate the SAG vCPE device with the SAG vCPE instance. The system checks whether the serial number and key are valid in the cloud. If the serial number or key is invalid, the SAG vCPE device cannot be connected to Alibaba Cloud. This reinforces the security of your networks and devices.

3.  Configure the SAG vCPE device.

    After you deploy the SAG vCPE image, you must advertise routes to Alibaba Cloud and associate the SAG vCPE device with a Cloud Connect Network \(CCN\) instance. Then, you can connect the SAG vCPE device to Alibaba Cloud.

4.  Configure the networks of your workloads.

    Before you can connect workloads to the SAG vCPE device and connect private networks to Alibaba Cloud, you must configure the routing of your workloads.


## Specifications

The following table describes the specifications of the servers where you can deploy the SAG vCPE image.

|Specification|ENS|AWS|
|-------------|---|---|
|1 Core - 2 GB|The bandwidth of the private network for encrypted connections can reach 200 Mbit/s and higher \(the packet length in the performance test is 1024 bytes\).|The bandwidth of the private network for encrypted connections can reach 200 Mbit/s and higher \(the packet length in the performance test is 1024 bytes\).|
|2 Core - 4 GB|The encrypted private bandwidth can reach 350 Mbit/s and higher \(the packet length in the performance test is 1024 bytes\).|The encrypted private bandwidth can reach 350 Mbit/s and higher \(the packet length in the performance test is 1024 bytes\).|

**Related topics**  


[Connect AWS to Alibaba Cloud through SAG vCPE](/intl.en-US/Smart Access Gateway vCPE/Deploy an SAG vCPE/Connect AWS to Alibaba Cloud through SAG vCPE.md)

