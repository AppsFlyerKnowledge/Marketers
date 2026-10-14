---
title: "Attribution discrepancies between Amazon Ads and AppsFlyer"
excerpt: "Learn about the differences in attribution models between Amazon Ads and AppsFlyer."
x-zendesk:
  id: 28461159218449
  url: https://support.appsflyer.com/hc/en-us/articles/28461159218449-Attribution-discrepancies-between-Amazon-Ads-and-AppsFlyer
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Amazon Ads
  section_id: 28703975923729
  position: 1
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11085
  content_tags: [pm-shay-maoz, Marketers, Mobile Attribution]
  labels: [Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2024-09-18T04:28:03Z'
  edited_at: '2026-08-27T06:51:52Z'
---
## Overview

As two major players in the mobile user acquisition ecosystem, Amazon Ads and AppsFlyer use distinct attribution models. This may cause discrepancies between Amazon Ads and AppsFlyer dashboards. While we work closely with Amazon Ads to minimize these discrepancies, advertisers need to be aware of potential causes.

## Differences in attribution models

The table below describes possible reasons for discrepancies between the Amazon Ads and the AppsFlyer dashboards:

| Cause | Amazon Ads Manager | AppsFlyer |
| --- | --- | --- |
| Multi-channel source attribution | Amazon Ads self-attributes installs regardless of other media sources. | AppsFlyer uses last-click attribution.  <br />Learn more about the [AppsFlyer attribution model](/docs/appsflyer-attribution-model). |
| Different timezones | Amazon Ads timezone (displayed next to the date range) can't be adjusted. It was configured while creating the ad account. | The AppsFlyer default app timezone is UTC+0. To match the timezone defined in the Amazon Ads, change the timezone set for the app on the [app settings page](/docs/app-settings#localization-time-zone). |

