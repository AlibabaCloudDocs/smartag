# Overview

Smart Access Gateway \(SAG\) supports access control. You can configure a whitelist or blacklist for an SAG instance.

## Configuration procedure

![ACL process](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/0080287951/p132913.png)

The procedure to configure access control is as follows:

1.  Create an access control list \(ACL\) and specify the list name.
2.  Add a rule to the ACL.
3.  Associate the target SAG instance with the ACL.
4.  You can add multiple rules to an ACL. You can associate SAG instances with or disassociate SAG instances from an ACL.

    **Note:** An SAG instance can be associated with only one ACL, and this limit cannot be increased.

5.  You can modify or delete ACL rules.

## Limits

The limits on ACLs are as follows:

-   You can associate an SAG instance with only one ACL, and this limit cannot be increased.
-   You can add a maximum of 50 rules to an ACL. To request a quota increase, [submit a ticket](https://selfservice.console.aliyun.com/ticket/createIndex?spm=a2c8b.12571063.console-base-top.dwork-order-1.6c3a5675P2NEW9).
-   You can create a maximum of 10 ACLs under each Alibaba Cloud account. To request a quota increase, [submit a ticket](https://selfservice.console.aliyun.com/ticket/createIndex?spm=a2c8b.12571063.console-base-top.dwork-order-1.6c3a5675P2NEW9).

