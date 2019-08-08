# DeviceLinkDown {#reference_f45_jft_mfb .reference}

The DeviceLinkDown event indicates that the branch-side OSPF neighbor or the static route link has failed.

## Alarm information {#section_qry_ygw_mfb .section}

|Event name|Event level|Status code|Status description|
|----------|-----------|-----------|------------------|
|DeviceLinkDown|CRITICAL|linkdown|Device Link State Change|

## Causes {#section_umr_dhw_mfb .section}

-   The customer-side switch has failed.
-   The customer-side switch is incorrectly configured.
-   The connection between the customer-side switch and the Smart Access Gateway has failed.

## Actions {#section_fs3_ghw_mfb .section}

Check the customer-side switch. For more information, see [Link failure between SAG-1000 and the switch](reseller.en-US/Smart Access Gateway/SAG Troubleshooting/Link failure between SAG-1000 and the switch.md#).

