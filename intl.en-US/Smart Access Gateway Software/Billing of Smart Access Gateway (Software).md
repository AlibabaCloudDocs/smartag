# Billing of Smart Access Gateway \(Software\) {#concept_ld5_pfk_wgb .concept}

Smart Access Gateway \(SAG\) \(Software\) is billed based on the number of client accounts. By default, each client account is provided with a free 5G data plan each month. If traffic in the data plan is used up, additional traffic usage is billed by the Pay-As-You-Go method.

## Billing calculation {#section_jbc_ghw_hhb .section}

The following table describes how SAG \(Software\) is billed according to the target region:

**Note:** 

-   The free data plan provided for each client account cannot be shared across different accounts.
-   If a free data plan is not used up at the end of a month, the remaining traffic in the data plan does not carry over to the next month.
-   If a free data plan is used up, additional traffic usage is billed by the Pay-As-You-Go method once each month.
-   The price of international-site SAG \(Software\) is calculated based on that of China-site SAG \(Software\) according to the following exchange rate.

    1 USD=6.4 RMB


|Number of accounts|Mainland China|Overseas \(except Dubai\)|Dubai|
|------------------|--------------|-------------------------|-----|
|5-100|45|45|120|
|100-1000|35|35|100|
|Unit price when the data plan is used up \(GB\)|20|20|70|

SAG \(Software\) uses tiered pricing based on the number of client accounts. Assume the number of accounts is n:

-   If n\>100, the price per month is: \(n-100\) × 35 + 100 × 45. Unit: RMB.
-   If n<=100, the price per month is n\*45. Unit: RMB.

## Status change and notification {#section_lzc_jhw_hhb .section}

|Instance status|Action|
|---------------|------|
|Notification before SAG \(Software\) expires.|You will receive notifications that the SAG \(Software\) is near its expiration date 14 days, 12 days, and 8 days before the instance expires.|
|SAG \(Software\) is stopped when it expires.|Your instance will be stopped 15 days after it expires.|
|Notification before release|You receive a notification that the instance will be released soon 14 days after the instance is stopped.|
|Release on time|You instance will be released 15 days after the instance is stopped. After the instance is released, its configurations will be cleared and cannot be recovered.|
|Notification before the instance is locked due to insufficient balance|You will receive a notification that the instance will soon be locked due to insufficient account balance six days before the balance becomes insufficient.|
|Locking when the balance is insufficient|Your instance will be locked when the balance becomes insufficient.|

