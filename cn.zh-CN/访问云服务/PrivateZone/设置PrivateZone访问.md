# 设置PrivateZone访问 {#task_zp5_nwy_pgb .task}

PrivateZone是基于阿里云专有网络VPC环境的私有DNS域名解析和管理服务。加载到云企业网（CEN）中的网络实例可以通过CEN访问PrivateZone服务。

确保选择的服务所在地、访问所在地已有网络实例（VPC/VBR/CCN）加载到云企业网中。

1.  登录[云企业网管理控制台](https://cen.console.aliyun.com/)。 
2.  单击目标云企业网实例ID。 
3.  单击PrivateZone页签，然后单击**点击授权**。 

    **说明：** 您只有在第一次配置PrivateZone访问时需要为智能接入网关进行授权。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/122838/156015501938425_zh-CN.png)

4.  在云资源访问授权页面，单击**同意授权**允许加载到云企业网的云连接网（智能接入网关的组成部分）关联的本地分支访问PrivateZone服务。 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/122838/156015502038860_zh-CN.png)

5.  单击**设置PrivateZone**，然后在设置PrivateZone页面，完成以下配置： 
    1.  **服务所在地**：选择配置了PrivateZone服务的VPC的所在地域。 
    2.  **服务VPC**：选择配置了PrivateZone服务的VPC。 

        PrivateZone只能通过选定服务所在地的VPC进行访问。

    3.  **访问所在地**：选择发起访问的地域。 

        **说明：** 

        -   访问所在地只能选择和服务所在地相同的地域或云连接网，且确保所选地域的网络实例已加载到云企业网。
        -   如果选择了云连接网，且云连接网的账号和VPC、云企业网的账号不同，您需要进行授权。详细信息，请参见[云连接网授权](cn.zh-CN/用户指南/访问云服务/PrivateZone/云连接网授权.md#)。
    4.  单击**确定**。 

