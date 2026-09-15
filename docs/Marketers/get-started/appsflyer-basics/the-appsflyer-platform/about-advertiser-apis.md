---
title: "About advertiser APIs"
excerpt: "An overview of the APIs available to advertisers for accessing, reporting, and updating data within AppsFlyer."
---
**At a glance:** APIs available to advertisers to access or update data.

## Advertiser API list and interfaces

Specific information about reports, reporting tools, and reporting APIs:

* [Raw-data reporting tools/APIs](https://support.appsflyer.com/hc/articles/209680773)
* [Aggregate and analytics reporting tools/APIs](https://support.appsflyer.com/hc/articles/360005437257)

#### Interfaces for advertisers

| Arena | API name | Premium feature | Description | Authentication<br>token/key | Interface type |
| --- | --- | --- | --- | --- | --- |
| Mobile attribution | [Server-to-server events](https://support.appsflyer.com/hc/articles/207034486) | No | Record in-app events that occur outside a mobile app | [SDK dev key](https://support.appsflyer.com/hc/articles/211719806-App-settings-#sdk-authentication-dev-key) | REST API |
| People-based Attribution (PBA) | [Server-to-server web](https://support.appsflyer.com/hc/articles/360006997298) | No | Report PBA events that occur in the Backend | [PBA key](/docs/pba-brand-bundles-and-settings#managing-brand-bundles) | REST API |
| Engagement | [OneLink](https://support.appsflyer.com/hc/articles/360001250345-OneLink-API) | Yes | Manage OneLinks: create, update, retrieve, delete | [SDK dev key](https://support.appsflyer.com/hc/articles/211719806-App-settings-#sdk-authentication-dev-key) | REST API |
| Remarketing | [Audiences](/docs/audiences-guide#import-an-audience) | Yes | Upload user lists to Audiences | [Import key](https://support.appsflyer.com/hc/articles/360013291857-Audiences-import-an-audience) | REST API |
| Privacy | [openDSR requests](https://support.appsflyer.com/hc/articles/11332840660625-OpenDSR-API) | No | Data removal requests and status | [V2.0](https://support.appsflyer.com/hc/articles/360004562377-) | REST API |
| Reporting | [Master performance KPIs](https://support.appsflyer.com/hc/articles/213223166) | Yes | Multi-app campaign performance metrics in CSV files | [V2.0](https://support.appsflyer.com/hc/articles/360004562377-) | REST API |
| Reporting | [Pull aggregate reports](https://support.appsflyer.com/hc/articles/207034346) | No | Aggregate reports in CSV files | [V2.0](https://support.appsflyer.com/hc/articles/360004562377-) | REST API |
| Reporting | [Pull raw data](https://support.appsflyer.com/hc/articles/360007530258) | Yes | Raw data reports in CSV files | [V2.0](https://support.appsflyer.com/hc/articles/360004562377-) | REST API |
| Reporting | [Cohort analytics](https://support.appsflyer.com/hc/articles/360004799057-Cohort-analtyics-API) | Yes | Cohort metrics in JSON or CSV files | [V2.0](https://support.appsflyer.com/hc/articles/360004562377-Managing-API-tokens) | REST API |
| Reporting | [Data Locker](https://support.appsflyer.com/hc/articles/360000877538) | Yes | Raw and aggregate data reports | N/A | Cloud storage |
| Mobile attribution | [Push](https://support.appsflyer.com/hc/articles/207034356) | Yes | Real-time installs and in-app events sent to advertisers' servers | N/A | REST API |
| Campaign cost | [Cost Import](https://support.appsflyer.com/hc/articles/360002868097) | No | Report campaign cost | N/A | File upload |
| Account | [Get app list](https://support.appsflyer.com/hc/articles/360011999877) | No | Get a list of apps in your account | [V2.0](https://support.appsflyer.com/hc/articles/360004562377-Managing-API-tokens) | REST API |
| Reporting | [ETL Cost](https://support.appsflyer.com/hc/articles/360008849238-Cost-ETL-granular-campaign-cost-in-a-bucket) | Yes | Cost ETL granular campaign cost | N/A | Cloud storage |
| Reporting | [SKAN reporting](https://support.appsflyer.com/hc/articles/360011420698#reporting-options) | No | SKAN aggregate reporting | V2.0 | REST API |
| Integrated partners | [Copy partner integration settings](https://dev.appsflyer.com/hc/reference/post_v1-copy) | No | Copy integration configuration parameters from one app to the other | V2.0 | REST API |
| Integrated partners | [Set install referrer decryption key](https://dev.appsflyer.com/hc/reference/post_v1-integration-params) | No | Set install referrer decryption key received from Meta ads | V2.0 | REST API |