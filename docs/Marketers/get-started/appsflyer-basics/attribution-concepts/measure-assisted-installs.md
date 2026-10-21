---
title: Measure assisted installs
metadata:
  keywords:
    - Attribution
    - installs
    - Assisted
    - multi-touch
    - reporting
    - assisted intalls
    - Advertisers
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2015-12-24T10:21:25Z'
  edited_at: '2026-05-25T14:01:59Z'
  id: 207040506
  locale: en-us
  section: Attribution concepts
  section_id: 6551394235409
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/207040506-Measure-assisted-installs
---
**At a glance:** Measure the broader impact of media sources that engaged your users and assisted before the last touch.

## Assisted installs

<Anchor target="_blank" href="https://www.appsflyer.com/mobile-fraud-glossary/assisted-installs-mobile-advertising-assists/">Assisted installs</Anchor> (AKA multi-touch attribution) are installs where the media source/campaign didn't have the last touch but did touch the user before the install and during the attribution window. One install can have up to 3 assisted installs.

Analytical data of assisted installs are available at both the media source and campaign levels to measure the broader impact of each media source and campaign.

### View assisted installs metrics in the Overview dashboard

**To view assisted installs in the Overview dashboard**:

1. In AppsFlyer, from the side menu, select **Analyze** > **Overview**.
2. Select the Extended Overview report.
3. Scroll down to the trend over time charts.
4. Select the **Media source** or **Campaign** dimension.
5. Select the **Assisted installs** metric.  
   The assisted installs chart displays. The blue indicates non-organic installs and the orange indicates assisted installs. ![AssitedInstallWidget.png](https://files.readme.io/a2fb5fb1f7414ede9a96858e325688d0c60b2ff910e24bc86e5597160c7548ca-33302646504977.png)

### Why are assists important

In many cases, potential users get familiar with an app via the assisting source but fail to install it for some reason. Thus measuring and recognizing assists is important in campaign optimization and measurement.

### Assisted installs reporting

AppsFlyer attributes up to 3 contributing networks in addition to the attributed install source.

In aggregate dashboards and raw data reports, the (up to 3) contributor networks are consolidated into one metric called "assisted installs". Meaning, 1 install can have up to 3 assisted installs counted.

In raw data reports, data on the contributing networks is broken down into separate fields for Contributors 1-3.

[![](https://files.readme.io/ee3558f74cedbec698c5e466a9697cad7a5b1910c45cd0851cfaf741959deba1-33302646505617.png)](https://files.readme.io/ee3558f74cedbec698c5e466a9697cad7a5b1910c45cd0851cfaf741959deba1-33302646505617.png)

For each of the contributing networks, the raw data report includes the following:

* Network name (Media source)
* Campaign name
* Engagement time (touch time)
* Engagement type (click or impression)
* Name of the involved agency (partner), if there was one
* Match type (<Anchor target="_blank" href="/marketers/docs/raw-data-field-dictionary#attribution::cecc12c5">The same as install match types.</Anchor>)

See <Anchor target="_blank" href="/marketers/docs/raw-data-reporting-overview#user-journey-reports">user journey raw data.</Anchor>

> 📘 **Note**
>
> **Media sources with user-level data restrictions**
> If a
> <Anchor target="_blank" href="/marketers/docs/about-raw-data-identifier-restrictions">media source restricts user-level data</Anchor>,
> it cannot be attributed as a contributor or an assist to a winning attribution.
> This means that certain sources, do not
> appear as contributors even if they engaged the user before the install.

> 📘 **Note**
>
> **Agency considerations**
> Several major ad networks <Anchor target="_blank" href="/marketers/docs/user-level-data-retention">restrict sharing their data with 3rd party platforms</Anchor>, including agencies. Therefore, assisted installs do not appear in the agency dashboard for these networks.

In raw data reports, data on the contributing networks is broken down into separate fields for **Contributors 1–3**.

### Total candidates field

In addition to the **Contributors 1–3** fields, the `total_candidates` field shows the number of engagements (such as clicks or impressions) associated with the same device at the time of the install or re-engagement.

However, not every engagement counted in `total_candidates` is eligible for attribution. For example, some engagements may have been:

* Outside of the lookback window
* Blocked by fraud protection
* Affected by app or partner integration settings
* Otherwise not meeting AppsFlyer’s attribution conditions

In practice, this means:

* If the install was attributed to organic, it is because none of the engagements in `total_candidates` met all the conditions required for attribution.
* If there are no contributors, it is for the same reason: the engagements recorded under `total_candidates` were not eligible to serve as contributors.

To summarize, `total_candidates` indicates engagements received, which are not necessarily valid candidates for attribution. It is possible to see value in this field while still having the install attributed to organic or without contributors.

> 📘 **Note**
>
> AppsFlyer Support will not provide engagement-level explanations or breakdowns of `total_candidates` due to the complexity of the attribution logic.

<div data-zendesk-anchors="h_01HCBC922K9PCDXGDCCVEARADH=assisted-installs h_01HCBC922KRHB043FK1CQRKXDA=view-assisted-installs-metrics-in-the-overview-dashboard h_01HCBC922KDAG8T27KK2JGRE7C=why-are-assists-important h_01HCBC922KJV54QW6G85SN2JM7=assisted-installs-reporting h_01KSFPXWNAX8FZ6H2ZKN1Z2TJQ=note h_01HCBC922K5HKF94JCY7C88R88=note-1 h_01K453B1K1X7QVJHPQ505P745N=note-2" />
