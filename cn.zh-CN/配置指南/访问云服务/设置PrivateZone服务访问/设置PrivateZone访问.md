# 设置PrivateZone访问

云解析PrivateZone是基于阿里云专有网络（VPC）环境的私有DNS域名解析和管理服务。智能接入网关（SAG）可通过云企业网访问PrivateZone服务。本文为您介绍如何在云企业网控制台设置智能接入网关PrivateZone服务访问。

-   您已经在云解析PrivateZone平台配置了私网解析服务。详情请参见[云解析PrivateZone快速入门](https://help.aliyun.com/document_detail/64627.html?spm=a2c4g.11186623.6.554.32b73210vjcDyU)。
-   您已创建了云企业网实例并加载了PrivateZone服务所在地的VPC网络实例。详情请参见[创建云企业网实例]()。
-   您本地网络连接的云连接网实例已经加载到云企业网中。详情请参见[加载网络实例]()。

云解析PrivateZone是基于阿里云专有网络（VPC）环境的私有DNS服务。该服务允许您在自定义的一个或多个VPC中将私有域名映射到IP地址。

通过PrivateZone，您可以方便地使用私有域名记录来管理VPC中的云服务器（ECS）主机名、负载均衡（SLB）、对象存储（OSS）等阿里云资源，而这些私有域名在VPC之外将无法访问。您可以通过智能接入网关和云企业网将您的本地网络与VPC相连，并通过在云企业网控制台设置PrivateZone服务访问，实现本地网络与阿里云VPC之间通过私有域名进行资源互访。

![PrivateZone服务架构图](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/6995752061/p172779.png)

1.  登录[云企业网管理控制台](https://cen.console.aliyun.com/cen/list)。

2.  单击目标云企业网实例ID。

3.  单击Private Zone页签，然后单击**点击授权**。

    **说明：** 您只有在第一次配置PrivateZone访问时需要为智能接入网关进行授权。

4.  在云资源访问授权页面，单击**同意授权**允许加载到云企业网的云连接网（智能接入网关的组成部分）关联的本地网络访问PrivateZone服务。

5.  单击**设置PrivateZone**，然后在设置PrivateZone面板，完成以下配置。

    ![设置PrivateZone服务](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/2454752061/p172717.png)

    1.  **服务所在地**：选择配置了PrivateZone服务的VPC的所在地域。

    2.  **服务VPC**：选择配置了PrivateZone服务的VPC。

        PrivateZone只能通过选定服务所在地的VPC进行访问。

    3.  **访问所在地**：选择发起访问的地域。

        **说明：**

        -   访问所在地只能选择与服务所在地同地域的云连接网实例，且确保所选地域的云连接网实例已加载到云企业网实例中。
        -   如果您选择的云连接网实例所属账号和云企业网实例、VPC实例的账号不同，您需要进行授权。详细信息，请参见[云连接网授权]()。
    4.  单击**确定**。


