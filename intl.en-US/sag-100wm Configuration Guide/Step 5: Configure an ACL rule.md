# Step 5: Configure an ACL rule {#task_kl2_ndg_qfb .task}

You can add an access control list \(ACL\) rule to allow specific IP addresses to access the Internet or intranet, or to deny the access of the IP addresses.

1.  Log on to the web configuration page of the Smart Access Gateway device. 
2.  After configuring the LAN ports, click **Next** to configure the ACL. 
3.  Select a rule direction, and then click **Add Rule** to configure security rules. 

    |Configuration|Description|
    |-------------|-----------|
    |**Rule direction**|     -   **Outbound**: Traffic that is bound from the local branch.
    -   **Inbound**: Traffic that is bound for the local branch.
 |
    |**Source address**|     -   **Outbound**: The CIDR block of the local branch that initiates access.
    -   **Inbound**: The CIDR block that accesses the local branch.
 |
    |**Destination address**|     -   **Outbound**: The external destination CIDR block to be accessed.
    -   **Inbound**: The destination CIDR block of the local branch to access.
 |
    |**Source port**|The source port range of the transport layer. 0/65535 represents all ports.|
    |**Protocol type**|The transport layer protocol.|
    |**Destination port**|The destination port range of the transport layer. 0/65535 represents all ports.|
    |**Authorization policy**|Select **Allow** or **Refuse**.|
    |**Priority**|Valid range: 1–100. As a general rule, the smaller the number, the higher the priority. If the priority of two rules is the same, the rule added earlier takes effect.|


