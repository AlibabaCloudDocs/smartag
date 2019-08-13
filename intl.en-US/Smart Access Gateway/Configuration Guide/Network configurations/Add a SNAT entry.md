# Add a SNAT entry {#task_995154 .task}

This topic describes how to add a SNAT entry to enable the SNAT function. The SNAT function can hide internal IP addresses and resolve private IP address conflicts. With this function, on-premises sites can access internal IP addresses, but cannot be accessed by internal IP addresses. If you do not add a SNAT entry, on-premises sites can access each other only when all related IP addresses do not conflict.

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com).
2.  In the left-side navigation pane, click **Smart Access Gateway**, and then click the target instance ID or click **Configure Network** in the **Actions** column.
3.  On the SAG instance details page, click **SNAT**.
4.  On the SNAT tab page, click **Add SANT**.
5.  In theAdd SNAT dialog box, set the SNAT parameters. 

    The SANT parameters are described as follows:

    -   **Public IP Address**: An IP address in the SNAT CIDR block of the CCN instance.
    -   **Private CIDR Block**: The private CIDR block used by on-premises terminals to access Alibaba Cloud. The private CIDR blocks cannot conflict with each other.
    ![Add a SNAT entry](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/803493/156571144251427_en-US.png)


