# What is an access control list? {#concept_dq3_zz4_dhb .concept}

Smart Access Gateway \(SAG\) provides the access control list \(ACL\) function in the form of whitelists and blacklists for different SAG instances.

## ACL usage process {#section_4xg_tpn_60j .section}

The process is described as follows:

1.  Create an ACL, and set the ACL name.
2.  Set an ACL rule for the ACL.
3.  Add an SAG instance to the ACL.
4.  You can configure multiple ACL rules for an ACL. You can also add SAG instances to the rules or remove the instances from them.

    **Note:** An SAG instance can be associated with only one ACL, and the quota cannot be adjusted.

5.  You can modify or delete existing ACL rules.

## ACL configuration recommendations {#section_rlx_ccp_dhb .section}

The recommendations on ACL configuration are as follows:

-   Use ACL as a whitelist.
-   Follow the minimum authorization principle. For example, you can choose to open a specific port \(such as port 80\).
-   All applications should not be managed with only one ACL, and different layers have different access control requirements.
-   Add instances with the same security requirements to the same ACL, and there is no need to configure a separate security group for each instance.

