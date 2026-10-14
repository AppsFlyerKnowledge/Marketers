---
title: "About advertiser APIs"
excerpt: "APIs available to advertisers to access or update data."
x-zendesk:
  id: 360009122638
  url: https://support.appsflyer.com/hc/en-us/articles/360009122638-About-advertiser-APIs
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: The AppsFlyer platform
  section_id: 6551361489297
  position: 1
  owner: Elliot Lachman
  owner_email: elliot.lachman@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-roy-negri, Marketers, Platform essentials]
  labels: [Advertisers, Marketers, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2020-05-24T15:14:53Z'
  edited_at: '2025-05-13T15:23:31Z'
---
## Advertiser API list and interfaces

Specific information about reports, reporting tools, and reporting APIs:

* [Raw-data reporting tools/APIs](/docs/raw-data-reporting-overview)
* [Aggregate and analytics reporting tools/APIs](/docs/aggregated-and-analytics-reporting-overview)

#### Interfaces for advertisers

| Arena | API name | ![af_premium.png](https://files.readme.io/ad0c279c48242ea25529f1bc386ee2c747bcd332f5fb1eb2fc26dd378a257f6e-4403570953105.png)<br /><br />Premium feature | Description | Authentication  <br />token/key | Interface type |
| --- | --- | --- | --- | --- | --- |
| Mobile attribution | [Server-to-server events](/docs/server-to-server-events-api-for-mobile-s2s-mobile) | No | Record in-app events that occur outside a mobile app | [SDK dev key](/docs/app-settings#sdk-authentication-dev-key) | REST API |
| People-based Attribution (PBA) | [Server-to-server web](/docs/web-server-to-server-events-api-for-pba-web-s2s) | No | Report PBA events that occur in the Backend | [PBA key](/docs/pba-brand-bundles-and-settings#managing-brand-bundles) | REST API |
| Engagement | [OneLink](/docs/use-onelink-api-to-create-links-in-large-scale-campaigns) | Yes | Manage OneLinks: create, update, retrieve, delete | [SDK dev key](/docs/app-settings#sdk-authentication-dev-key) | REST API |
| Remarketing | [Audiences](/docs/audiences-guide#import-an-audience) | Yes | Upload user lists to Audiences | [Import key](/docs/audiences-import-audience-segments-from-internal-systems) | REST API |
| Privacy | [openDSR requests](/docs/send-opendsr-api-requests) | No | Data removal requests and status | [V2.0](/docs/managing-appsflyer-tokens) | REST API |
| Reporting | [Master performance KPIs](/docs/master-api-user-acquisition-metrics-via-api) | Yes | Multi-app campaign performance metrics in CSV files | [V2.0](/docs/managing-appsflyer-tokens) | REST API |
| Reporting | [Pull aggregate reports](/docs/pull-api-aggregate-data) | No | Aggregate reports in CSV files | [V2.0](/docs/managing-appsflyer-tokens) | REST API |
| Reporting | [Pull raw data](/docs/pull-api-raw-data) | Yes | Raw data reports in CSV files | [V2.0](/docs/managing-appsflyer-tokens) | REST API |
| Reporting | [Cohort analytics](/docs/cohort-api) | Yes | Cohort metrics in JSON or CSV files | [V2.0](/docs/managing-appsflyer-tokens) | REST API |
| Reporting | [Data Locker](/docs/data-locker-for-marketers) | Yes | Raw and aggregate data reports | N/A | Cloud storage |
| Mobile attribution | [Push](/docs/push-api-streaming-raw-data) | Yes | Real-time installs and in-app events sent to advertisers' servers | N/A | REST API |
| Campaign cost | [Cost Import](/docs/cost-import-for-ad-networks) | No | Report campaign cost | N/A | File upload |
| Account | [Get app list](/docs/app-list-api-for-app-owners) | No | Get a list of apps in your account | [V2.0](/docs/managing-appsflyer-tokens) | REST API |
| Reporting | [ETL Cost](/docs/set-up-and-use-roi360-cost-etl-reports) | Yes | Cost ETL granular campaign cost | N/A | Cloud storage |
| Reporting | [SKAN reporting](/docs/skadnetwork-skan-solution-guide#reporting-options) | No | SKAN aggregate reporting | V2.0 | REST API |
| Integrated partners | [Copy partner integration settings](https://dev.appsflyer.com/hc/reference/post_v1-copy) | No | Copy integration configuration parameters from one app to the other | V2.0 | REST API |
| Integrated partners | [Set install referrer decryption key](https://dev.appsflyer.com/hc/reference/post_v1-integration-params) | No | Set install referrer decryption key received from Meta ads | V2.0 | REST API |