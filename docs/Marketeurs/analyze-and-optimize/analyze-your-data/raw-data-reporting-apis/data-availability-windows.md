---
title: Data availability windows
metadata:
  keywords:
    - Advertisers
    - Premium Feature
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Raw Reports
  created_at: '2022-01-04T03:33:13Z'
  edited_at: '2026-07-15T08:18:16Z'
  id: 4415473374865
  locale: en-us
  section: Raw data reporting/APIs
  section_id: 6550930711057
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/4415473374865-Data-availability-windows
---
> **At a glance:** Data availability depends on the report type and the defined availability window.

## Data availability windows

* The terms **availability window** and **data retention** mean different things. <Anchor target="_blank" href="https://www.appsflyer.com/legal/services-privacy-policy/">Data retention</Anchor> relates to the period we keep raw data on our servers and is of longer duration than the availability window.
* The window duration depends on your subscription package.
* The article doesn't apply to <Anchor target="_blank" href="/marketers/fr/docs/data-locker-for-marketers">Data Locker</Anchor>.

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
| Aggregated reports | 25 months (2 years + 1 month), <Anchor target="_blank" href="/marketers/fr/docs/bulletin-aggregated-ltv-data-availability">starting with the first app install</Anchor> |

> 📄 **See also**
>
> * <Anchor target="_blank" href="/marketers/fr/docs/report-generation-quotas-rate-limitations">Report generation quotas</Anchor>

<div data-zendesk-anchors="h_01HE0FT9CNECNKYMVX9ZJJ9DNV=data-availability-windows h_01HE0FT9CNS4N1GD1AYRBSRWPF=raw-data-availability-window h_01HE0FT9CPW91ASDH9MEW083ZH=aggregated-data-availability-window h_01HE7S7VH4PC6FQAYKP6A0G4YY=see-also" />
