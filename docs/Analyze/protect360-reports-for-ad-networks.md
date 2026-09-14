---
title: "Protect360 reports for ad networks"
excerpt: "Ad networks responsible for user acquisition and retargeting can receive data regarding blocked clicks and impressions."
---
## Protect360 reports for ad networks

> 📘 Disclaimer
>
> This article provides information on Protect360 reports available only to ad networks. For data that is also available to advertisers, see [Protect360 for integrated partners](https://support.appsflyer.com/hc/articles/115004745523).

Ad networks can receive reports via [Data Locker for Partners](https://support.appsflyer.com/hc/articles/360020818517) with valuable information regarding clicks and impressions that are blocked either because of:

- Blocked clicks and impressions that occur when ad networks cross their fraud limit. The report includes total blocks, as well as blocks due to click and impression capping. [Learn more about capping](https://support.appsflyer.com/hc/articles/115004745523#impression-and-click-capping)
- Failed click signatures that occur when a click with the network's PID parameter networks and a click signature to validate clicks can't be validated. [Learn more about click signing](https://support.appsflyer.com/hc/articles/360017831497)

Ad networks can then ingest this network-level data with cross-customer visibility of their blocked clicks and impressions and use it to protect against fraud.

### Report considerations

- Data arrives in CSV format to the UA/retargeting partner's bucket.
- Contains dimensions and metrics relevant to the ad network (that is cleaned of all dimensions irrelevant to the ad network).
- Available via [Data Locker for Partners](https://support.appsflyer.com/hc/articles/360020818517).
- Data freshness: [Daily, meaning data for Day 0 arrives on Day 1](https://support.appsflyer.com/hc/articles/360000310629-Data-freshness-and-time-zone-support#ad-revenue). Data is written daily at 07:00 [UTC time](https://support.appsflyer.com/hc/articles/360000310629-Data-freshness-and-time-zone-support#daily) to the h=23 of your Data Locker bucket.
- Apps included: A single report contains the data of all apps.

## Report types

### Blocked clicks and impressions

This report contains aggregate level data about clicks and impressions that are blocked due to capping or any other reason.

#### Report structure: Fields/Dimensions

| **Field** | **Remarks** |
| --- | --- |
| app\_id | App ID in the AppsFlyer platform. |
| site\_id | ID that identifies the publisher that displays the ad. |
| date | Blocked date |
| agency | - Agency that brought the traffic via this ad network.<br>- Returns as null if there is no agency involved. |

#### Report structure: Metrics

| **Field** | **Remarks** |
| --- | --- |
| number\_of\_blocked\_clicks | Total number of the network’s blocked clicks |
| number\_of\_blocked\_impressions | Total number of the network’s blocked impressions |
| number\_of\_capped\_clicks | The number of the network’s capped clicks (out of the total blocked clicks) |
| number\_of\_capped\_impressions | The number of the network’s capped impressions (out of the total blocked impressions) |

### Failed click signatures

This report contains user-level about failed click signatures. Meaning, when ad networks use the [AppsFlyer click signing method](https://support.appsflyer.com/hc/articles/360017831497), the report contains clicks of URLs with the network’s PID that don't have validated click signatures, either because the signature is invalid or expired, or the click is not signed at all. Click signing failures could occur when there are technical errors in the implementation of click signatures by the ad network, or when clicks are sent on behalf of the network (with its PID) by another party.

#### Report structure: Fields/Dimensions

| **Field** | **Remarks** |
| --- | --- |
| event\_time |  |
| original\_url |  |
| failed\_signing\_reason | For example:<br>- Invalid signature<br>- Missing signature<br>- Expired signature<br>- Expired secret key |
| is\_blocking\_enabled | Refers to the configuration mode of the [click signature API](https://support.appsflyer.com/hc/articles/360017831497):<br>- TRUE for enabled.<br>- FALSE for report-only.<br>- Not included in the report for disabled. |