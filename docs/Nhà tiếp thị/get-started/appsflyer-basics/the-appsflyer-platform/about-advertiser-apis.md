---
title: About advertiser APIs
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2020-05-24T15:14:53Z'
  edited_at: '2025-05-13T15:23:31Z'
  id: 360009122638
  locale: en-us
  section: The AppsFlyer platform
  section_id: 6551361489297
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360009122638-About-advertiser-APIs
---
> **At a glance:** APIs available to advertisers to access or update data.

## Advertiser API list and interfaces

<span id="01EEQJERAWW3HY59HVPY3YWA0B"></span>Specific information about reports, reporting tools, and reporting APIs:

* <span id="01EEQJERAW2ZTBWBQKBCDSC76Z"></span><span id="01EEQJERAWQ2WCPV0207XM6FR4"></span><Anchor target="_blank" href="/marketers/vi/docs/raw-data-reporting-overview"><span id="01EEQJERAX0W7RCYQWVM2M5S13"></span>Raw-data reporting tools/APIs</Anchor>
* <span id="01EEQJERAWA09P200SGR985846"></span><span id="01EEQJERAW6AC6WR7E46T5DMHW"></span><Anchor target="_blank" href="/marketers/vi/docs/aggregated-and-analytics-reporting-overview">Aggregate and analytics reporting tools/APIs</Anchor>

#### Interfaces for advertisers

| Arena | API name | <Image alt="af_premium.png" src="https://files.readme.io/ad0c279c48242ea25529f1bc386ee2c747bcd332f5fb1eb2fc26dd378a257f6e-4403570953105.png" width="80px" /><br /><br />Premium feature | Description | Authentication  <br />token/key | Interface type |
| --- | --- | --- | --- | --- | --- |
| Mobile attribution | <Anchor target="_blank" href="/marketers/vi/docs/server-to-server-events-api-for-mobile-s2s-mobile">Server-to-server events</Anchor> | No | Record in-app events that occur outside a mobile app | <Anchor target="_blank" href="/marketers/vi/docs/app-settings#sdk-authentication-dev-key">SDK dev key</Anchor> | REST API |
| People-based Attribution (PBA) | <Anchor target="_blank" href="/marketers/vi/docs/web-server-to-server-events-api-for-pba-web-s2s">Server-to-server web</Anchor> | No | Report PBA events that occur in the Backend | <Anchor target="_blank" href="/marketers/vi/docs/pba-brand-bundles-and-settings#quản-lý-gói-thương-hiệu">PBA key</Anchor> | REST API |
| Engagement | <Anchor target="_blank" href="/marketers/vi/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">OneLink</Anchor> | Yes | Manage OneLinks: create, update, retrieve, delete | <Anchor target="_blank" href="/marketers/vi/docs/app-settings#sdk-authentication-dev-key">SDK dev key</Anchor> | REST API |
| Remarketing | <Anchor target="_blank" href="/marketers/vi/docs/audiences-guide#import-an-audience">Audiences</Anchor> | Yes | Upload user lists to Audiences | <Anchor target="_blank" href="/marketers/vi/docs/audiences-import-audience-segments-from-internal-systems">Import key</Anchor> | REST API |
| Privacy | <Anchor target="_blank" href="/marketers/vi/docs/send-opendsr-api-requests">openDSR requests</Anchor> | No | Data removal requests and status | <Anchor target="_blank" href="/marketers/vi/docs/managing-appsflyer-tokens">V2.0</Anchor> | REST API |
| Reporting | <Anchor target="_blank" href="/marketers/vi/docs/master-api-user-acquisition-metrics-via-api">Master performance KPIs</Anchor> | Yes | Multi-app campaign performance metrics in CSV files | <Anchor target="_blank" href="/marketers/vi/docs/managing-appsflyer-tokens">V2.0</Anchor> | REST API |
| Reporting | <Anchor target="_blank" href="/marketers/vi/docs/pull-api-aggregate-data">Pull aggregate reports</Anchor> | No | Aggregate reports in CSV files | <Anchor target="_blank" href="/marketers/vi/docs/managing-appsflyer-tokens">V2.0</Anchor> | REST API |
| Reporting | <Anchor target="_blank" href="/marketers/vi/docs/pull-api-raw-data">Pull raw data</Anchor> | Yes | Raw data reports in CSV files | <Anchor target="_blank" href="/marketers/vi/docs/managing-appsflyer-tokens">V2.0</Anchor> | REST API |
| Reporting | <Anchor target="_blank" href="/marketers/vi/docs/cohort-api">Cohort analytics</Anchor> | Yes | Cohort metrics in JSON or CSV files | <Anchor target="_blank" href="/marketers/vi/docs/managing-appsflyer-tokens">V2.0</Anchor> | REST API |
| Reporting | <Anchor target="_blank" href="/marketers/vi/docs/data-locker-for-marketers">Data Locker</Anchor> | Yes | Raw and aggregate data reports | N/A | Cloud storage |
| Mobile attribution | <Anchor target="_blank" href="/marketers/vi/docs/push-api-streaming-raw-data">Push</Anchor> | Yes | Real-time installs and in-app events sent to advertisers' servers | N/A | REST API |
| Campaign cost | <Anchor target="_blank" href="/partners/vi/docs/cost-import-for-ad-networks">Cost Import</Anchor> | No | Report campaign cost | N/A | File upload |
| Account | <Anchor target="_blank" href="/marketers/vi/docs/app-list-api-for-app-owners">Get app list</Anchor> | No | Get a list of apps in your account | <Anchor target="_blank" href="/marketers/vi/docs/managing-appsflyer-tokens">V2.0</Anchor> | REST API |
| Reporting | <Anchor target="_blank" href="/marketers/vi/docs/set-up-and-use-roi360-cost-etl-reports">ETL Cost</Anchor> | Yes | Cost ETL granular campaign cost | N/A | Cloud storage |
| Reporting | <Anchor target="_blank" href="/marketers/vi/docs/skadnetwork-skan-solution-guide#reporting-options">SKAN reporting</Anchor> | No | SKAN aggregate reporting | V2.0 | REST API |
| Integrated partners | <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_v1-copy">Copy partner integration settings</Anchor> | No | Copy integration configuration parameters from one app to the other | V2.0 | REST API |
| Integrated partners | <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_v1-integration-params">Set install referrer decryption key</Anchor> | No | Set install referrer decryption key received from Meta ads | V2.0 | REST API |

<div data-zendesk-anchors="h_01HX9638DX6EHR4ETMSH10K68F=advertiser-api-list-and-interfaces h_01HX9638DXNJM3A968A2PSRRKS=interfaces-for-advertisers" />
