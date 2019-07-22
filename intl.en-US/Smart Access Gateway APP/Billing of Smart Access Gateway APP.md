# Billing of Smart Access Gateway APP {#concept_ld5_pfk_wgb .concept}

Smart Access Gateway \(SAG\) APP is billed by the number of client accounts. By default, each client account is provided with a free 5 GB data plan each month. If traffic in the data plan is used up, additional traffic usage is billed by the Pay-As-You-Go method.

## Billing method {#section_jbc_ghw_hhb .section}

The following table describes how SAG APP is billed according to the target region:

-   The Smart Access Gateway APP is billed by the number of client accounts. For more information, see [Table 1](#table_5gn_pje_b9h).

    Assume that the number of accounts is n:

    -   If n\>100, the price per month is: \(n-100\) × 35 + 100 × 45. Unit: RMB.
    -   If n<=100, the price per month is: n × 45. Unit: RMB.
-   The free data plan provided for each client account cannot be shared by different accounts.
-   The 5 GB traffic per month refers to the maximum upstream or downstream traffic.
-   5 GB/month
-   If a free data plan is not used up at the end of a month, the remaining traffic in the data plan does not carry over to the next month.
-   If a free data plan is used up, additional traffic usage is billed by the Pay-As-You-Go method once each month.
-   The price of international-site SAG APP is calculated based on that of China-site SAG APP according to the exchange rate \(unit: USD\).

The following table describes the usage and billing of the SAG APP package.

|Number of accounts|Mainland China|Outside Mainland China \(except Dubai\)|Dubai|
|------------------|--------------|---------------------------------------|-----|
|5-100|45|45|120|
|100-1000|35|35|100|
|Unit price when the data plan is used up \(GB\)|20|20|70|

## Status change and notification {#section_lzc_jhw_hhb .section}

智能接入网关APP实例停机/释放/受限状态导致的动作如下表所示。

|Instance status|Action|
|---------------|------|
|Notification before SAG APP expires|You will receive notifications that the SAG APP is near its expiration date 14 days, 12 days, and 8 days before the instance expires.|
|SAG APP is stopped when it expires.|Your instance will be stopped 15 days after it expires.|
|Notification before release|You will receive a notification that the instance will be released soon 14 days after the instance is stopped.|
|Release on time|Your instance will be released 15 days after the instance is stopped. After the instance is released, its configurations will be cleared and cannot be recovered.|
|Notification before the instance is locked due to insufficient balance|You will receive a notification that the instance will soon be locked due to insufficient account balance six days before the balance becomes insufficient.|
|Locking when the balance is insufficient|Your instance will be locked when the balance becomes insufficient.|

