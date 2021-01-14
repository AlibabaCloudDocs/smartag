# Billing and pricing of the SAG app

The Smart Access Gateway \(SAG\) app is billed based on the number of client accounts. By default, each client account has a 5 GB data transfer plan. After the 5 GB data transfer plan is exhausted, you can select the subscription or pay-as-you-go billing method for the exceeded data usage.

## Billing rules

The SAG app is billed based on the following rules:

-   The SAG app is billed based on the number of client accounts and a tiered pricing strategy. For more information, see [Table 1](#table_5gn_pje_b9h).

    Assume that the number of client accounts is n:

    -   If n \> 100: Fees per month = \(n-100\) × 5.42 + 100 × 6.96. Unit: USD.
    -   If n ≤ 100: Fees per month = n × 6.96. Unit: USD.
-   After the 5 GB data transfer plan is exhausted, you can purchase a subscription data transfer plan for the exceeded amount.
    -   Subscription data transfer plans offer multiple specifications. The validity period of each data transfer plan is one month. For more information about pricing, see[Table 2](#table_hxx_14d_6pe).
    -   A subscription data transfer plan is shared by all the SAG app instances and client accounts that are under the same Alibaba Cloud account that has purchased the subscription.
-   If the data transfer plan is exhausted, you can select the pay-as-you-go billing method for the exceeded amount. Pay-as-you-go bills are generated on a daily basis. For more information about pricing, see [Table 3](#table_tos_bd6_5w6).
-   The 5 GB data transfer plan provided to each client account cannot be shared.
-   5 GB refers to the upper limit of the data transferred from external networks to Alibaba Cloud, or from Alibaba Cloud to external networks.
-   The 5 GB data transfer plan or subscription data transfer plan is effective only within the month when the data transfer plan or the subscription is issued.

The following table describes the pricing of the SAG app.

|The number of client accounts|Mainland China|Outside mainland China and Dubai|
|-----------------------------|--------------|--------------------------------|
|5~100|6.96|6.96|
|101~1000|5.42|5.42|

|Specification \(GB\)|Mainland China|Outside mainland China and Dubai|
|--------------------|--------------|--------------------------------|
|10|26|26|
|50|123|123|
|128|288|288|
|512|1149|1149|
|1024|2154|2154|
|5120|10193|10193|
|10240|19381|19381|
|51200|92310|92310|

|Unit price of the exceeded data usage|Mainland China|Outside mainland China and Dubai|
|-------------------------------------|--------------|--------------------------------|
|Unit price of the exceeded data usage|3.10|3.10|

## The states of an SAG app instance

The following table describes different states of an SAG app instance.

|State|Action|
|-----|------|
|Notifications before expiration|14 days, 12 days, and 8 days before the SAG app instance expires, you will receive notifications.|
|Expired|15 days after the SAG app instance expires, it stops running. You cannot use the SAG app instance when it stops running.|
|Notifications before release|14 days after the SAG app instance stops running, you will receive notifications that the SAG app instance will be released.|
|Released|15 days after the SAG app instance stops running, it will be released and the configurations will be deleted and cannot be restored.|
|Overdue payments|6 days before the payment is overdue, you will receive notifications that the SAG app instance will be locked due to the overdue payment.|
|Locked|When the payment is overdue, the SAG app instance is locked and unavailable.|

