---
title: "User-level data retention"
excerpt: "Understand AppsFlyer's retention and user-level raw data policies, including specific partner data retention periods and legal compliance guidelines."
---
Retention and user-level (raw data) use policies are determined by AppsFlyer, relevant laws, and SRNs (" **Partners**") terms of use.

> 🚧 Caution
>
> AppsFlyer provides the data restriction explanations, in this article, for information purposes only. _Nothing stated here is legal advice. It is provided for your information and convenience._

## Data retention and deletion obligations

AppsFlyer receives user-level data from apps, partners, and other sources.

### Availability of user-level data to advertisers

Typically, user-level data is made available to advertisers via raw data reporting tools if their subscription package includes raw data during a 90-day access window (See [data availability windows](/docs/data-availability-windows)). In some cases, there are also [raw data restrictions](https://support.appsflyer.com/hc/articles/360006868017).

### Data retention

AppsFlyer retains user-level data for a limited period. Raw data retention periods vary depending on the delivery method and partner requirements. In general:

- **User-level raw data** retention period is based on integration type and partner requirements.
- **Aggregated data** is retained for up to 25 months.

Before the end of the retention period, user events are attributed to the media source that brought the user. After the end of the retention period, user events are attributed to organic.

The retention period is determined according to the following:

- [AppsFlyer Services Privacy Policy](https://www.appsflyer.com/legal/processing-customer-data/)
- As directed, required, or allowed by law
- Partner terms of use and retention period as listed in the table that follows.

Consider the following:

- The access window and retention period may differ
- AppsFlyer, in some cases, may extend the access window
- The retention period can vary per partner, bringing the user
- Some user-level data is attributed to the [restricted media source](https://support.appsflyer.com/hc/articles/360006868017-FAQ-What-is-the-restricted-media-source-), which means that raw data doesn't contain the attribution data. This can occur in the following instances:
  - Partner data sharing policy
  - [Aggregated Advanced Privacy](https://support.appsflyer.com/hc/articles/360018515798-) is on

#### Partner data retention periods

| SRN/partner | Partner ID (PID) | After install, delete data after [x] months |
| --- | --- | --- |
| Amazon Ads | amazondsp\_int | 12 |
| Apple Search Ads | Apple Search Ads | No limit |
| Discord | discord\_int | 6 |
| DV360 | dv360\_int, doubleclick\_int | 6 |
| Google Ads\* | googleadwords\_int (all channels) | 6 |
| Hotstar | hotstar\_int | 6 |
| Meta ads\* | facebook\_int (all channels) | 6 |
| Microsoft | microsoftdisplay\_int and bingsearch\_int | 13 |
| Pinterest | pinterest\_int | 6 |
| Samsung DSP | samsungdsp\_int | 3 |
| Snapchat\* ( [TOS](https://businesshelp.snapchat.com/en-US/article/attribution-terms)) | snapchat\_int | 6 |
| TikTok for Business\* | tiktokglobal\_int | 13 |
| X Ads (formerly Twitter) | twitter\_int | 3 |

> 📘 Note\*
>
> For SRNs, the retention periods in this table apply only to data provided by the SRN directly. They do not apply to attribution made via AppsFlyer W2A attribution links (`googleads_int`, `metaweb_int`, `tiktokweb_int`, `snapweb_int`).