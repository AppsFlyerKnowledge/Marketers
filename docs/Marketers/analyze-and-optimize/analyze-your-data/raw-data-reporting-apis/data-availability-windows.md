---
title: "Data availability windows"
excerpt: "Data availability depends on the report type and the defined availability window."
x-zendesk:
  id: 4415473374865
  url: https://support.appsflyer.com/hc/en-us/articles/4415473374865-Data-availability-windows
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Raw data reporting/APIs
  section_id: 6550930711057
  position: 2
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-rona-einat, Marketers, Raw Reports]
  labels: [Advertisers, Premium Feature, Marketers, Loc In Prog]
  promoted: false
  comments_disabled: true
  created_at: '2022-01-04T03:33:13Z'
  edited_at: '2026-07-15T08:18:16Z'
---
## Data availability windows

* The terms **availability window** and **data retention** mean different things. [Data retention](https://www.appsflyer.com/legal/services-privacy-policy/) relates to the period we keep raw data on our servers and is of longer duration than the availability window.
* The window duration depends on your subscription package.
* The article doesn't apply to [Data Locker](/docs/data-locker-for-marketers).

### Raw data availability window

The availability window limits raw data provided by Pull API and the Raw Data export page. The window duration depends on the report type, as detailed in the following table.

| Report event type | Example report types | Default availability window |
| --- | --- | --- |
| Attributions | Organic installs, non-organic installs, retargeting conversions, uninstalls | 60 out of the last 90 days |
| In-app events | Organic in-app events, non-organic in-app events, retargeting in-app events | 31 out of the last 90 days |

### Aggregated data availability window

An availability window limits data provided by Pull API and the Aggregated Data export page. The window duration depends on the report type, as detailed in the following table.

| Report | Availability window |
| --- | --- |
| Aggregated reports | 25 months (2 years + 1 month), [starting with the first app install](/docs/bulletin-aggregated-ltv-data-availability) |

> 📘 **See also**
>
> * [Report generation quotas](/docs/report-generation-quotas-rate-limitations)

<div data-zendesk-anchors="h_01HE0FT9CNECNKYMVX9ZJJ9DNV=data-availability-windows h_01HE0FT9CNS4N1GD1AYRBSRWPF=raw-data-availability-window h_01HE0FT9CPW91ASDH9MEW083ZH=aggregated-data-availability-window h_01HE7S7VH4PC6FQAYKP6A0G4YY=see-also" />
