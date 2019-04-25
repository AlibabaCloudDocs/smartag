# What is an access control list? {#concept_dq3_zz4_dhb .concept}

Smart Access Gateway \(SmartAG\) provides the access control list \(ACL\) function in the form of whitelists and blacklists for different SmartAG instances that are applicable to different access requirements.

## Access Control List usage process { .section}

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/143856/155616079944986_en-US.png)

The process is described as follows:

1.  Create an ACL, and set the ACL name.
2.  Set access control rule for ACL.
3.  Add an SmartAG instance to ACL.
4.  You can configure multiple access control rules for an ACL. Add or remove a SmartAG instance.

    **Note:** A SmartAG instance can only be associated with one ACL, unable to adjust.

5.  You can modify or delete existing ACL rules.

## Access Control List Configuration Recommendations {#section_rlx_ccp_dhb .section}

The ACL configuration recommendations are as follows:

-   ACL is used as a whitelist.
-   Open application access rules follow the minimum authorization principle. For example, you can choose to open a specific port \(such as port 80\).
-   All application should not be managed with one ACL, and different layers have different access control requirements.
-   Add instances with the same security protection requirements to the same ACL, there is not necessay to set up a separate security group for each instance.

