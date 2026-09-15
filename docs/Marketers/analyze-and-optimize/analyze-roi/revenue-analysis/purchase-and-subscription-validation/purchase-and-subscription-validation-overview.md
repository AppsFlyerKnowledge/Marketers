---
title: "Purchase and subscription validation - Overview"
excerpt: "Understand how AppsFlyer validates purchases and subscriptions, and compare the two available solutions: Receipt validation and ROI360 store revenue."
---
Purchase and subscription validation is essential for ensuring the accuracy and reliability of your revenue data. When users make purchases in your app - whether one-time or subscription-based - validating those transactions with the app stores (Apple App Store and Google Play) ensures that only legitimate, paid transactions are measured and attributed.

AppsFlyer offers two solutions that validate and measure in-app purchases and subscription revenue: Receipt validation and ROI360 store revenue.

The article provides a high-level introduction to each solution and [a feature comparison](#compare-receipt-validation-and-roi360-store-revenue) to help you determine which option is right for your app.

## The two solutions for purchase and subscription validation

### Receipt validation

Receipt validation is AppsFlyer's free solution for verifying in-app purchases and subscriptions on iOS and Android. It ensures that only real transactions are measured. It does this by validating receipts directly with the app stores.

Using this solution, the AppsFlyer SDK integrated into your app provides minimal data, such as the product ID, purchase ID, and type. AppsFlyer then retrieves the full revenue details from the store response. This includes the amount and currency. This solution does not provide net revenue calculation, full subscription funnel coverage, refund handling, and automated purchase detection & deduplication.

Use Receipt validation to make informed decisions and optimize campaigns based on verified revenue data.

For more information, see:

- [About Receipt validation](/docs/about-receipt-validation)
- [Set up Receipt validation](https://support.appsflyer.com/hc/articles/42137474889489--WIP-Set-up-receipt-validation)

### ROI360 store revenue Premium

> 📘 Important!
>
> ROI360 store revenue is available only to customers on the ROI360 premium plan. To check your plan or upgrade, contact your Customer Success Manager (CSM).

The ROI360 store revenue solution is AppsFlyer's premium product for complete and accurate revenue measurement from in-app purchases and subscriptions. It validates transactions server-to-server with the app stores and returns enriched, verified revenue data.

Within this server-to-server validation flow, ROI360 store revenue provides deduplication, calculates net revenue after store fees and taxes, and offers full subscription lifecycle coverage, including renewals, cancellations, refunds, and upgrades. It also processes events from existing subscribers, and it resolves delayed payments from stores like Google Play.

Use this solution if you need complete revenue accuracy, subscription lifecycle insights, and support for complex business models.

For more information, see:

- [About ROI360 store revenue](https://support.appsflyer.com/hc/articles/42138855425297--WIP-About-ROI360-store-revenue)
- [Set up ROI360 store revenue](https://support.appsflyer.com/hc/articles/42158608158353-Setup-ROI360-store-revenue)

## Compare Receipt validation and ROI360 store revenue

Use the tables below to determine which solution best fits your needs.

### Compare features

| **Feature** | **Receipt validation** | ROI360 store revenue Premium |
| --- | --- | --- |
| **Receipt validation**<br>Verifies in-app purchases to filter out fraudulent transactions. | ✔ | ✔ |
| **Automated purchase detection & deduplication**<br>Automatically detects IAPs and subscriptions, including transactions from existing subscribers, and removes duplicates for cleaner reporting. | ✖ | ✔ |
| **Refund handling**<br>Detects refunds and attributes them to the original purchase to reflect true revenue. | ✖ | ✔\* |
| **Complete IAP measurement**<br>Handles family sharing and reports the final outcome of pending purchases using App Store confirmation. | ✖ | ✔ |
| **Full subscription funnel coverage**<br>Measures renewals, upgrades, and conversions to reflect the full value from your subscriber base. | ✖ | ✔ |
| **Net revenue calculation**<br>Calculates both gross and net revenue by deducting store fees and taxes automatically. | ✖ | ✔ |

\* Refund handling **for in-app purchases** is available only on the ROI360 Advanced plan.

### Compare in-app purchase event support

| **Event name** | **Receipt validation** | **ROI360** store revenue |
| --- | --- | --- |
| af\_purchase | ✔ | ✔ |
| af\_purchase\_refund\* | ❌ | ✔ |
| af\_purchase\_pending | ❌ | ✔ |
| af\_purchase\_canceled\* | ❌ | ✔ |
| af\_purchase\_free | ❌ | ✔ |
| af\_purchase\_sandbox\_sdk | ✔ | ✔ |
| af\_purchase\_sandbox\_s2s\* | ❌ | ✔ |

\* Available only on the ROI360 Advanced plan.

### Compare Subscription-related event support

| **Event name** | **Receipt validation** | **ROI360** store revenue |
| --- | --- | --- |
| af\_ars\_trial\_started | ✔ | ✔ |
| af\_ars\_trial\_canceled | ❌ | ✔ |
| af\_ars\_trial\_churned | ❌ | ✔ |
| af\_ars\_trial\_converted | ❌ | ✔ |
| af\_ars\_subscription\_started | ✔ | ✔ |
| af\_ars\_subscription\_canceled | ❌ | ✔ |
| af\_ars\_subscription\_paused | ❌ | ✔ |
| af\_ars\_subscription\_resumed | ❌ | ✔ |
| af\_ars\_subscription\_churned | ❌ | ✔ |
| af\_ars\_subscription\_refunded | ❌ | ✔ |
| af\_ars\_subscription\_billing\_grace | ❌ | ✔ |
| af\_ars\_subscription\_renewed | ❌ | ✔ |
| af\_ars\_subscription\_xgraded | ❌ | ✔ |
| af\_ars\_existing\_subscriber | ❌ | ✔ |
| af\_ars\_sandbox\_sdk | ✔ | ✔ |
| af\_ars\_sandbox\_s2s | ❌ | ✔ |