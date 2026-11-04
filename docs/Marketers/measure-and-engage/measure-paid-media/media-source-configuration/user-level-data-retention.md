---
title: User-level data retention
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - SRN
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Agencies
    - Ad Networks
  created_at: '2020-02-23T15:35:57Z'
  edited_at: '2026-11-02T08:54:08Z'
  id: 360006091197
  locale: en-us
  section: Media source configuration
  section_id: 6551067072785
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360006091197-User-level-data-retention
---
> **At a glance:** Retention and user-level (raw data) use policies are determined by AppsFlyer, relevant laws, and SRNs ("**Partners**") terms of use.

<div id="caution" />

> ❗️ **Caution**
>
> AppsFlyer provides the data restriction explanations, in this article, for information purposes only.  *Nothing stated here is legal advice. It is provided for your information and convenience.*

<div id="data-retention-and-deletion-obligations" />

## Data retention and deletion obligations

AppsFlyer receives user-level data from apps, partners, and other sources.

<div id="availability-of-user-level-data-to-advertisers" />

### Availability of user-level data to advertisers

Typically, user-level data is made available to advertisers via raw data reporting tools if their subscription package includes raw data during a 90-day access window (See <Anchor target="_blank" href="/marketers/docs/data-availability-windows">data availability windows</Anchor>). In some cases, there are also <Anchor target="_blank" href="/marketers/docs/about-raw-data-identifier-restrictions">raw data restrictions</Anchor>.

<div id="data-retention" />

### Data retention

AppsFlyer retains user-level data for a limited period. Raw data retention periods vary depending on the delivery method and partner requirements. In general:

* **User-level raw data** retention period is based on integration type and partner requirements.
* **Aggregated data** is retained for up to 25 months.

Before the end of the retention period, user events are attributed to the media source that brought the user. After the end of the retention period, user events are attributed to organic.

The retention period is determined according to the following:

* <Anchor target="_blank" href="https://www.appsflyer.com/legal/processing-customer-data/">AppsFlyer Services Privacy Policy</Anchor>
* As directed, required, or allowed by law
* Partner terms of use and retention period as listed in the table that follows.

Consider the following:

* The access window and retention period may differ
* AppsFlyer, in some cases, may extend the access window
* The retention period can vary per partner, bringing the user
* Some user-level data is attributed to the <Anchor target="_blank" href="/marketers/docs/about-raw-data-identifier-restrictions">restricted media source</Anchor>, which means that raw data doesn't contain the attribution data. This can occur in the following instances:
  * Partner data sharing policy
  * <Anchor target="_blank" href="/marketers/docs/apply-aggregated-advanced-privacy-framework">Aggregated Advanced Privacy</Anchor> is on

<div id="partner-data-retention-periods" />

#### Partner data retention periods

| SRN/partner | Partner ID (PID) | After install, delete data after [x] months |
| --- | --- | --- |
| Amazon Ads | amazondsp\_int | 12 |
| Apple Search Ads | Apple Search Ads | No limit |
| Discord | discord\_int | 6 |
| DV360 | dv360\_int, doubleclick\_int | 6 |
| Google Ads* | googleadwords\_int (all channels) | 6 |
| Hotstar | hotstar\_int | 6 |
| Meta ads* | facebook\_int (all channels) | 6 |
| Microsoft | microsoftdisplay\_int and bingsearch\_int | 13 |
| Pinterest | pinterest\_int | 6 |
| Samsung DSP | samsungdsp\_int | 3 |
| Snapchat* (<Anchor target="_blank" href="https://businesshelp.snapchat.com/en-US/article/attribution-terms">TOS</Anchor>) | snapchat\_int | 6 |
| TikTok for Business* | tiktokglobal\_int | 13 |
| X Ads (formerly Twitter) | twitter\_int | 3 |
| Walmart | walmart\_int | 6 |

<div id="note" />

> 📘 **Note***
>
> For SRNs, the retention periods in this table apply only to data provided by the SRN directly. They do not apply to attribution made via AppsFlyer W2A attribution links (`googleads_int`, `metaweb_int`, `tiktokweb_int`, `snapweb_int`).

<div data-zendesk-anchors="h_01H95FY07TRAAD3K0A0TSG3RB6=caution h_01H95FY07TABPC769R7TYGY5DD=data-retention-and-deletion-obligations availability-of-userlevel-data-to-advertisers=availability-of-user-level-data-to-advertisers h_01H95FY07T2Q9QAGW5A5S6KP6J=availability-of-user-level-data-to-advertisers h_01H95FY07TXS63FVDJC2NEFXYC=data-retention h_01H95FY07TZ4N0RRJRGJ6FN2EK=partner-data-retention-periods h_01KRKAWSHH2WFZT9Q5M0FSBBAB=note" />
